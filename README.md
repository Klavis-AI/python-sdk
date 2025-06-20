# Klavis Python Library

[![fern shield](https://img.shields.io/badge/%F0%9F%8C%BF-Built%20with%20Fern-brightgreen)](https://buildwithfern.com?utm_source=github&utm_medium=github&utm_campaign=readme&utm_source=https%3A%2F%2Fgithub.com%2FKlavis-AI%2Fpython-sdk)
[![pypi](https://img.shields.io/pypi/v/klavis)](https://pypi.python.org/pypi/klavis)

The Klavis Python library provides convenient access to the Klavis API from Python.

## Documentation

The full API of this library can be found in [api.md](api.md).

## Installation

```sh
pip install klavis
```

## Reference

A full reference for this library is available [here](https://github.com/Klavis-AI/python-sdk/blob/HEAD/./reference.md).

## Usage

Instantiate and use the client with the following:

```python
from klavis import Klavis

client = Klavis(
    token="YOUR_TOKEN",
)
client.mcp_server.call_server_tool(
    server_url="serverUrl",
    tool_name="toolName",
)
```

## Async Client

The SDK also exports an `async` client so that you can make non-blocking calls to our API.

```python
import asyncio

from klavis import AsyncKlavis

client = AsyncKlavis(
    token="YOUR_TOKEN",
)


async def main() -> None:
    await client.mcp_server.call_server_tool(
        server_url="serverUrl",
        tool_name="toolName",
    )


asyncio.run(main())
```

## Async usage

Simply import `AsyncKlavis` instead of `Klavis` and use `await` with each API call:

```python
import os
import asyncio
from klavis import AsyncKlavis

client = AsyncKlavis(
    api_key=os.environ.get("KLAVIS_API_KEY"),  # This is the default and can be omitted
)


async def main() -> None:
    instance = await client.mcp_server.instance.create(
        platform_name="x",
        server_name="Markdown2doc",
        user_id="x",
    )
    print(instance.instance_id)


asyncio.run(main())
```

Functionality between the synchronous and asynchronous clients is otherwise identical.

## Using types

Nested request parameters are [TypedDicts](https://docs.python.org/3/library/typing.html#typing.TypedDict). Responses are [Pydantic models](https://docs.pydantic.dev) which also provide helper methods for things like:

- Serializing back into JSON, `model.to_json()`
- Converting to a dictionary, `model.to_dict()`

Typed requests and responses provide autocomplete and documentation within your editor. If you would like to see type errors in VS Code to help catch bugs earlier, set `python.analysis.typeCheckingMode` to `basic`.

## Handling errors

When the library is unable to connect to the API (for example, due to network connection problems or a timeout), a subclass of `klavis.APIConnectionError` is raised.

When the API returns a non-success status code (that is, 4xx or 5xx
response), a subclass of `klavis.APIStatusError` is raised, containing `status_code` and `response` properties.

All errors inherit from `klavis.APIError`.

```python
import klavis
from klavis import Klavis

client = Klavis()

try:
    client.mcp_server.instance.create(
        platform_name="x",
        server_name="Markdown2doc",
        user_id="x",
    )
except klavis.APIConnectionError as e:
    print("The server could not be reached")
    print(e.__cause__)  # an underlying Exception, likely raised within httpx.
except klavis.RateLimitError as e:
    print("A 429 status code was received; we should back off a bit.")
except klavis.APIStatusError as e:
    print("Another non-200-range status code was received")
    print(e.status_code)
    print(e.response)
```

Error codes are as follows:

| Status Code | Error Type                 |
| ----------- | -------------------------- |
| 400         | `BadRequestError`          |
| 401         | `AuthenticationError`      |
| 403         | `PermissionDeniedError`    |
| 404         | `NotFoundError`            |
| 422         | `UnprocessableEntityError` |
| 429         | `RateLimitError`           |
| >=500       | `InternalServerError`      |
| N/A         | `APIConnectionError`       |

### Retries

Certain errors are automatically retried 2 times by default, with a short exponential backoff.
Connection errors (for example, due to a network connectivity problem), 408 Request Timeout, 409 Conflict,
429 Rate Limit, and >=500 Internal errors are all retried by default.

You can use the `max_retries` option to configure or disable retry settings:

```python
from klavis import Klavis

# Configure the default for all requests:
client = Klavis(
    # default is 2
    max_retries=0,
)

# Or, configure per-request:
client.with_options(max_retries=5).mcp_server.instance.create(
    platform_name="x",
    server_name="Markdown2doc",
    user_id="x",
)
```

### Timeouts

By default requests time out after 1 minute. You can configure this with a `timeout` option,
which accepts a float or an [`httpx.Timeout`](https://www.python-httpx.org/advanced/#fine-tuning-the-configuration) object:

```python
from klavis import Klavis

# Configure the default for all requests:
client = Klavis(
    # 20 seconds (default is 1 minute)
    timeout=20.0,
)

# More granular control:
client = Klavis(
    timeout=httpx.Timeout(60.0, read=5.0, write=10.0, connect=2.0),
)

# Override per-request:
client.with_options(timeout=5.0).mcp_server.instance.create(
    platform_name="x",
    server_name="Markdown2doc",
    user_id="x",
)
```

On timeout, an `APITimeoutError` is thrown.

Note that requests that time out are [retried twice by default](#retries).

## Exception Handling

When the API returns a non-success status code (4xx or 5xx response), a subclass of the following error
will be thrown.

```python
from klavis.core.api_error import ApiError

try:
    client.mcp_server.call_server_tool(...)
except ApiError as e:
    print(e.status_code)
    print(e.body)
```

## Advanced

### Access Raw Response Data

The SDK provides access to raw response data, including headers, through the `.with_raw_response` property.
The `.with_raw_response` property returns a "raw" client that can be used to access the `.headers` and `.data` attributes.

```python
from klavis import Klavis

client = Klavis(
    ...,
)
response = client.mcp_server.with_raw_response.call_server_tool(...)
print(response.headers)  # access the response headers
print(response.data)  # access the underlying object
```

### Retries

The SDK is instrumented with automatic retries with exponential backoff. A request will be retried as long
as the request is deemed retryable and the number of retry attempts has not grown larger than the configured
retry limit (default: 2).

A request is deemed retryable when any of the following HTTP status codes is returned:

- [408](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/408) (Timeout)
- [429](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429) (Too Many Requests)
- [5XX](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500) (Internal Server Errors)

Use the `max_retries` request option to configure this behavior.

```python
client.mcp_server.call_server_tool(..., request_options={
    "max_retries": 1
})
```

### Timeouts

The SDK defaults to a 60 second timeout. You can configure this with a timeout option at the client or request level.

```python

from klavis import Klavis

client = Klavis(
    ...,
    timeout=20.0,
)


# Override timeout for a specific method
client.mcp_server.call_server_tool(..., request_options={
    "timeout_in_seconds": 1
})
```

### Custom Client

You can override the `httpx` client to customize it for your use-case. Some common use-cases include support for proxies
and transports.

```python
import httpx
from klavis import Klavis

client = Klavis(
    ...,
    httpx_client=httpx.Client(
        proxies="http://my.test.proxy.example.com",
        transport=httpx.HTTPTransport(local_address="0.0.0.0"),
    ),
)
```

## Contributing

While we value open-source contributions to this SDK, this library is generated programmatically.
Additions made directly to this library would have to be moved over to our generation code,
otherwise they would be overwritten upon the next generated release. Feel free to open a PR as
a proof of concept, but know that we will not be able to merge it as-is. We suggest opening
an issue first to discuss with us!

On the other hand, contributions to the README are always very welcome!
## Contributing

While we value open-source contributions to this SDK, this library is generated programmatically.
Additions made directly to this library would have to be moved over to our generation code,
otherwise they would be overwritten upon the next generated release. Feel free to open a PR as
a proof of concept, but know that we will not be able to merge it as-is. We suggest opening
an issue first to discuss with us!

On the other hand, contributions to the README are always very welcome!
## Versioning

This package generally follows [SemVer](https://semver.org/spec/v2.0.0.html) conventions, though certain backwards-incompatible changes may be released as minor versions:

1. Changes that only affect static types, without breaking runtime behavior.
2. Changes to library internals which are technically public but not intended or documented for external use. _(Please open a GitHub issue to let us know if you are relying on such internals.)_
3. Changes that we do not expect to impact the vast majority of users in practice.

We take backwards-compatibility seriously and work hard to ensure you can rely on a smooth upgrade experience.

We are keen for your feedback; please open an [issue](https://www.github.com/Klavis-AI/python-sdk/issues) with questions, bugs, or suggestions.

### Determining the installed version

If you've upgraded to the latest version but aren't seeing any new features you were expecting then your python environment is likely still using an older version.

You can determine the version that is being used at runtime with:

```py
import klavis
print(klavis.__version__)
```

