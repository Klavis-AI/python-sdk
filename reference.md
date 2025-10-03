# Reference
## McpServer
<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">call_tools</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Calls a tool on a specific remote MCP server, used for function calling. Eliminates the need for manual MCP code implementation.
Under the hood, Klavis will instantiates an MCP client and establishes a connection with the remote MCP server to call the tool.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.call_tools(
    server_url="serverUrl",
    tool_name="toolName",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**server_url:** `str` — The full URL for connecting to the MCP server
    
</dd>
</dl>

<dl>
<dd>

**tool_name:** `str` — The name of the tool to call
    
</dd>
</dl>

<dl>
<dd>

**tool_args:** `typing.Optional[typing.Dict[str, typing.Optional[typing.Any]]]` — The input parameters for the tool
    
</dd>
</dl>

<dl>
<dd>

**connection_type:** `typing.Optional[ConnectionType]` — The connection type to use for the MCP server. Default is STREAMABLE_HTTP.
    
</dd>
</dl>

<dl>
<dd>

**headers:** `typing.Optional[typing.Dict[str, typing.Optional[str]]]` — Optional HTTP headers to include when connecting to the server
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">list_tools</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Lists all tools available for a specific remote MCP server in various AI model formats.

This eliminates the need for manual MCP code implementation and format conversion.
Under the hood, Klavis instantiates an MCP client and establishes a connection 
with the remote MCP server to retrieve available tools.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.list_tools(
    server_url="serverUrl",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**server_url:** `str` — The full URL for connecting to the MCP server
    
</dd>
</dl>

<dl>
<dd>

**connection_type:** `typing.Optional[ConnectionType]` — The connection type to use for the MCP server. Default is STREAMABLE_HTTP.
    
</dd>
</dl>

<dl>
<dd>

**format:** `typing.Optional[ToolFormat]` — The format to return tools in. Default is MCP Native format for maximum compatibility.
    
</dd>
</dl>

<dl>
<dd>

**headers:** `typing.Optional[typing.Dict[str, typing.Optional[str]]]` — Optional HTTP headers to include when connecting to the server
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">create_strata_server</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a Strata MCP server.

Parameters:
- servers: Can be 'ALL' to add all available Klavis MCP servers, a list of specific server names, or null to add no servers
- externalServers: Optional list of external MCP servers to validate and add
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.create_strata_server(
    user_id="userId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_id:** `str` — The unique identifier for the user. The server instance along with the all the authentication data will belong to that specific user only. It can be a UUID from the database, a unique email address from the user, etc.
    
</dd>
</dl>

<dl>
<dd>

**servers:** `typing.Optional[Servers]` — List of Klavis MCP servers to enable (e.g., 'jira', 'linear'), 'ALL' to add all Klavis MCP servers, or null to add no servers.
    
</dd>
</dl>

<dl>
<dd>

**external_servers:** `typing.Optional[typing.Sequence[ExternalServerRequest]]` — Optional list of external MCP servers to add with their URLs. Each server will be validated before being added.
    
</dd>
</dl>

<dl>
<dd>

**enable_auth_handling:** `typing.Optional[bool]` — Whether to enable authentication handling. Default is True.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">add_servers_to_strata</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add servers to an existing Strata MCP server.

Note: After adding servers, you need to reconnect the MCP server so that list_tool can be updated with the new servers.

Parameters:
- servers: Can be 'ALL' to add all available servers, a list of specific server names, or null to add no servers
- externalServers: Optional list of external MCP servers to validate and add
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.add_servers_to_strata(
    strata_id="strataId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**strata_id:** `str` — The strata server ID
    
</dd>
</dl>

<dl>
<dd>

**servers:** `typing.Optional[Servers]` — List of Klavis MCP servers to add (e.g., 'jira', 'linear'), 'ALL' to add all Klavis MCP servers, or null to add no servers.
    
</dd>
</dl>

<dl>
<dd>

**external_servers:** `typing.Optional[typing.Sequence[ExternalServerRequest]]` — Optional list of external MCP servers to add with their URLs. Each server will be validated before being added.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">delete_servers_from_strata</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete servers from an existing Strata MCP server.

Note: After deleting servers, you need to reconnect the MCP server so that list_tool can be updated to reflect the removed servers.

Parameters:
- strataId: The strata server ID (path parameter)
- servers: Can be 'ALL' to delete all available Klavis MCP servers, a list of specific server names, or null to delete no servers
- externalServers: Query parameter - comma-separated list of external server names to delete

Returns separate lists for deleted Klavis servers and deleted external servers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.delete_servers_from_strata(
    strata_id="strataId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**strata_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**servers:** `typing.Optional[
    typing.Union[
        DeleteServersFromStrataMcpServerStrataStrataIdServersDeleteRequestServersItem,
        typing.Sequence[
            DeleteServersFromStrataMcpServerStrataStrataIdServersDeleteRequestServersItem
        ],
    ]
]` — List of Klavis MCP servers to delete (e.g., 'jira', 'linear'), 'ALL' to delete all Klavis MCP servers, or null to delete no servers.
    
</dd>
</dl>

<dl>
<dd>

**external_servers:** `typing.Optional[str]` — Comma-separated list of external server names to delete
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_strata_instance</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get information about an existing Strata MCP server instance.

Returns the strata URL, connected klavis servers, connected external servers (with URLs), 
and authentication URLs for klavis servers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.get_strata_instance(
    strata_id="strataId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**strata_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">set_strata_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Sets authentication data for a specific integration within a Strata MCP server.

Accepts either API key authentication or general authentication data.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import ApiKeyAuth, Klavis, McpServerName

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.set_strata_auth(
    strata_id="strataId",
    server_name=McpServerName.AFFINITY,
    auth_data=ApiKeyAuth(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**strata_id:** `str` — The strata server ID
    
</dd>
</dl>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the Klavis MCP server to set authentication for (e.g., 'GitHub', 'Jira')
    
</dd>
</dl>

<dl>
<dd>

**auth_data:** `Authdata` — Authentication data
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">create_server_instance</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a URL for a specified MCP server,
validating the request with an API key and user details.
Returns the existing server URL if it already exists for the user.
If OAuth is configured for the server, also returns the base OAuth authorization URL.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis, McpServerName

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.create_server_instance(
    server_name=McpServerName.AFFINITY,
    user_id="userId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the target MCP server. Case-insensitive (e.g., 'google calendar', 'GOOGLE_CALENDAR', 'Google Calendar' are all valid).
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `str` — The unique identifier for the user. The server instance along with the all the authentication data will belong to that specific user only. It can be a UUID from the database, a unique email address from the user, etc.
    
</dd>
</dl>

<dl>
<dd>

**platform_name:** `typing.Optional[str]` — The name of the platform associated with the user. Optional.
    
</dd>
</dl>

<dl>
<dd>

**connection_type:** `typing.Optional[ConnectionType]` — The connection type to use for the MCP server. Default is STREAMABLE_HTTP.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">create_self_hosted_server_instance</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates an instance id for a self-hosted MCP server,
validating the request with an API key and user details.
The main purpose of this endpoint is to create an instance id for a self-hosted MCP server.
The instance id is used to identify and store the auth metadata in the database.
Returns the existing instance id if it already exists for the user.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis, McpServerName

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.create_self_hosted_server_instance(
    server_name=McpServerName.AFFINITY,
    user_id="userId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the target MCP server. Case-insensitive (e.g., 'google calendar', 'GOOGLE_CALENDAR', 'Google Calendar' are all valid).
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `str` — The unique identifier for the user. The server instance along with the all the authentication data will belong to that specific user only. It can be a UUID from the database, a unique email address from the user, etc.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_server_instance</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Checks the details of a specific server connection instance using its unique ID and API key,
returning server details like authentication status and associated server/platform info.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.get_server_instance(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — The ID of the connection instance whose status is being checked. This is returned by the Create API.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">delete_instance_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes authentication data for a specific server connection instance.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.delete_instance_auth(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — The ID of the connection instance to delete auth for.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">delete_server_instance</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Completely removes a server connection instance using its unique ID,
deleting all associated data from the system.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.delete_server_instance(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — The ID of the connection instance to delete.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_tools</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get tools information for any MCP server.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis, McpServerName

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.get_tools(
    server_name=McpServerName.AFFINITY,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the target MCP server. Case-insensitive (e.g., 'google calendar', 'GOOGLE_CALENDAR', 'Google Calendar' are all valid).
    
</dd>
</dl>

<dl>
<dd>

**format:** `typing.Optional[ToolFormat]` — The format to return tools in. Default is MCP Native format for maximum compatibility.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_all_mcp_servers</a>()</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get all MCP servers with their basic information including id, name, description, and tools.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.get_all_mcp_servers()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">set_instance_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Sets authentication data for a specific instance.
Accepts either API key authentication or general authentication data.
This updates the auth_metadata for the specified instance.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import ApiKeyAuth, Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.set_instance_auth(
    instance_id="instanceId",
    auth_data=ApiKeyAuth(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — The unique identifier for the connection instance
    
</dd>
</dl>

<dl>
<dd>

**auth_data:** `Authdata` — Authentication data
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_instance_auth_data</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieves the auth data for a specific instance that the API key owner controls.
Includes access token, refresh token, and other authentication data.

This endpoint includes proper ownership verification to ensure users can only access
authentication data for instances they own. It also handles token refresh if needed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.get_instance_auth_data(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — The ID of the connection instance to get auth data for.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_oauth_url</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Gets the OAuth authorization URL for a specific MCP server and instance.
Returns the complete OAuth URL with the instance ID as a query parameter.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis, McpServerName

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.get_oauth_url(
    server_name=McpServerName.AFFINITY,
    instance_id="instanceId",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the target MCP server. Case-insensitive (e.g., 'google calendar', 'GOOGLE_CALENDAR', 'Google Calendar' are all valid).
    
</dd>
</dl>

<dl>
<dd>

**instance_id:** `str` — The unique identifier for the connection instance.
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Optional client ID for white labeling. If not provided, will use default credentials.
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string).
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## WhiteLabeling
<details><summary><code>client.white_labeling.<a href="src/klavis/white_labeling/client.py">create_white_labeling</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Saves OAuth white labeling information, or updates existing information if the `client_id` matches.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis, OAuthServerName

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.white_labeling.create_white_labeling(
    client_id="client_id",
    client_secret="client_secret",
    server_name=OAuthServerName.AIRTABLE,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**client_id:** `str` — OAuth client ID
    
</dd>
</dl>

<dl>
<dd>

**client_secret:** `str` — OAuth client secret
    
</dd>
</dl>

<dl>
<dd>

**server_name:** `OAuthServerName` — Optional. The name of the server
    
</dd>
</dl>

<dl>
<dd>

**callback_url:** `typing.Optional[str]` — Optional. OAuth callback URL
    
</dd>
</dl>

<dl>
<dd>

**account_id:** `typing.Optional[str]` — Optional. The UUID of the account
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.white_labeling.<a href="src/klavis/white_labeling/client.py">get_white_labeling_by_client_id</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieves white labeling information for a specific OAuth client ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.white_labeling.get_white_labeling_by_client_id(
    client_id="client_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**client_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## User
<details><summary><code>client.user.<a href="src/klavis/user/client.py">get_server_instances_by_user</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get all MCP server instances information by user ID and platform name.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.user.get_server_instances_by_user(
    user_id="user_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_id:** `str` — The external user ID
    
</dd>
</dl>

<dl>
<dd>

**platform_name:** `typing.Optional[str]` — The platform name (optional)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.user.<a href="src/klavis/user/client.py">delete_user_by_user_id</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a user and all associated data by user_id.
Users cannot delete their own accounts.
This operation will permanently remove all user data.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.user.delete_user_by_user_id(
    user_id="user_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**user_id:** `str` — The identifier for the user to delete.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Oauth
<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_slack</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Slack OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- user_scope: Optional user-specific scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_slack(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**user_scope:** `typing.Optional[str]` — Optional user-specific OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_github</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start GitHub OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_github(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_gitlab</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start GitLab OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_gitlab(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_supabase</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Supabase OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_supabase(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_notion</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Notion OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_notion(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_jira</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Jira OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_jira(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_confluence</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Confluence OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_confluence(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_wordpress</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start WordPress OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_wordpress(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_gmail</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Gmail OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_gmail(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_gdrive</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Google Drive OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_gdrive(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_gcalendar</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Google Calendar OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_gcalendar(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_gsheets</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Google Sheets OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_gsheets(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_gdocs</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Google Docs OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_gdocs(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_attio</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Attio OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_attio(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_salesforce</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Salesforce OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
- instance_url: Optional Salesforce instance URL for sandbox or custom domains
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_salesforce(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**instance_url:** `typing.Optional[str]` — Salesforce instance URL (e.g., https://mycompany.salesforce.com). If not provided, will use default login.salesforce.com
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_asana</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Asana OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_asana(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_linear</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Linear OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_linear(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_close</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Close OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_close(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_clickup</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start ClickUp OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_clickup(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_airtable</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Airtable OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_airtable(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_hubspot</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start HubSpot OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_hubspot(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_linkedin</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start LinkedIn OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_linkedin(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_canva</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Canva OAuth flow with PKCE

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated, e.g., "design:meta:read profile:read")
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_canva(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_xero</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Xero OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_xero(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_dropbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Dropbox OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_dropbox(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_box</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Box OAuth 2.0 flow
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_box(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_quickbooks</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start QuickBooks OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- environment: QuickBooks environment to authorize ('sandbox' default)
- scope: Optional scopes to request (space-separated). Default is 'com.intuit.quickbooks.accounting'
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_quickbooks(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**environment:** `typing.Optional[Environment]` — QuickBooks environment to authorize ('sandbox' or 'production')
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_zendesk</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Zendesk OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
- subdomain: Zendesk subdomain for the account being connected
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_zendesk(
    instance_id="instance_id",
    subdomain="subdomain",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**subdomain:** `str` — Zendesk subdomain for the account being connected (e.g., 'mycompany' for mycompany.zendesk.com)
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_stripe</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Stripe Connect OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_stripe(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_calcom</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Cal.com OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_calcom(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_vercel</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Vercel OAuth flow using integration pattern

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- client_slug: Vercel integration slug (required for integration-based OAuth)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_vercel(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**client_slug:** `typing.Optional[str]` — Vercel integration slug (required for integration-based OAuth)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_pipedrive</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Pipedrive OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_pipedrive(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_figma</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Figma OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_figma(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_klaviyo</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_klaviyo(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_pagerduty</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start PagerDuty OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_pagerduty(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_docusign</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start DocuSign OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_docusign(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_dialpad</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Dialpad OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (space-separated)
- redirect_url: Optional URL to redirect to after authorization completes
- code_challenge: PKCE code challenge for enhanced security
- code_challenge_method: PKCE code challenge method
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_dialpad(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**code_challenge:** `typing.Optional[str]` — PKCE code challenge for enhanced security
    
</dd>
</dl>

<dl>
<dd>

**code_challenge_method:** `typing.Optional[str]` — PKCE code challenge method (default: S256)
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_shopify</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Shopify OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- shop: Shopify shop domain (e.g., mystore.myshopify.com)
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request (comma-separated)
- redirect_url: Optional URL to redirect to after authorization completes
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_shopify(
    instance_id="instance_id",
    shop="shop",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**shop:** `str` — Shopify shop domain (e.g., mystore.myshopify.com)
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (comma-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_onedrive</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_onedrive(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_outlook</a>(...)</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_outlook(
    instance_id="instance_id",
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**instance_id:** `str` — Unique identifier for the client instance requesting authorization
    
</dd>
</dl>

<dl>
<dd>

**client_id:** `typing.Optional[str]` — Client ID for white labeling, if not provided will use default credentials
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Optional OAuth scopes to request (space-separated string)
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization completes
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

