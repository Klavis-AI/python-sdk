# Reference
<details><summary><code>client.<a href="src/klavis/client.py">redirect_to_jira_callback_redirect_get</a>()</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Simple redirect endpoint that forwards to the Jira OAuth callback URL
while preserving all original query parameters
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
client.redirect_to_jira_callback_redirect_get()

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

## McpServer
<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">call_server_tool</a>(...)</code></summary>
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
client.mcp_server.call_server_tool(
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

**connection_type:** `typing.Optional[ConnectionType]` — The connection type to use for the MCP server. Default is SSE.
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">list_server_tools</a>(...)</code></summary>
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
client.mcp_server.list_server_tools(
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

**connection_type:** `typing.Optional[ConnectionType]` — The connection type to use for the MCP server. Default is SSE.
    
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
    server_name=McpServerName.MARKDOWN2DOC,
    user_id="userId",
    platform_name="platformName",
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

**server_name:** `McpServerName` — The name of the target MCP server.
    
</dd>
</dl>

<dl>
<dd>

**user_id:** `str` — The identifier for the user requesting the server URL.
    
</dd>
</dl>

<dl>
<dd>

**platform_name:** `str` — The name of the platform associated with the user.
    
</dd>
</dl>

<dl>
<dd>

**connection_type:** `typing.Optional[ConnectionType]` — The connection type to use for the MCP server. Default is SSE.
    
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

Deletes authentication metadata for a specific server connection instance.
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_server_tools</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get list of tool names for a specific MCP server.
Mainly used for querying metadata about the MCP server.
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
client.mcp_server.get_server_tools(
    server_name=McpServerName.MARKDOWN2DOC,
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

**server_name:** `McpServerName` — The name of the target MCP server.
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">set_instance_auth_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Sets an authentication token for a specific instance.
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
from klavis import Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.set_instance_auth_token(
    instance_id="instanceId",
    auth_token="authToken",
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

**auth_token:** `str` — The authentication token to save
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_o_auth_url</a>(...)</code></summary>
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
client.mcp_server.get_o_auth_url(
    server_name=McpServerName.MARKDOWN2DOC,
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

**server_name:** `McpServerName` — The name of the target MCP server.
    
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
    server_name=OAuthServerName.SLACK,
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
    platform_name="platform_name",
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

**platform_name:** `str` — The platform name
    
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

## SlackOauth
<details><summary><code>client.slack_oauth.<a href="src/klavis/slack_oauth/client.py">authorize_slack</a>(...)</code></summary>
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
client.slack_oauth.authorize_slack(
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

<details><summary><code>client.slack_oauth.<a href="src/klavis/slack_oauth/client.py">slack_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Slack OAuth authorization.
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
client.slack_oauth.slack_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Slack
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Slack, if any
    
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

## GithubOauth
<details><summary><code>client.github_oauth.<a href="src/klavis/github_oauth/client.py">authorize_github</a>(...)</code></summary>
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
client.github_oauth.authorize_github(
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

<details><summary><code>client.github_oauth.<a href="src/klavis/github_oauth/client.py">github_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from GitHub OAuth authorization.
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
client.github_oauth.github_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by GitHub
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by GitHub, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from GitHub, if any
    
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

## SupabaseOauth
<details><summary><code>client.supabase_oauth.<a href="src/klavis/supabase_oauth/client.py">authorize_supabase</a>(...)</code></summary>
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
client.supabase_oauth.authorize_supabase(
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

<details><summary><code>client.supabase_oauth.<a href="src/klavis/supabase_oauth/client.py">supabase_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Supabase OAuth authorization.
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
client.supabase_oauth.supabase_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Supabase
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Supabase, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Supabase, if any
    
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

<details><summary><code>client.supabase_oauth.<a href="src/klavis/supabase_oauth/client.py">refresh_supabase_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Supabase access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.supabase_oauth.refresh_supabase_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## NotionOauth
<details><summary><code>client.notion_oauth.<a href="src/klavis/notion_oauth/client.py">authorize_notion</a>(...)</code></summary>
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
client.notion_oauth.authorize_notion(
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

<details><summary><code>client.notion_oauth.<a href="src/klavis/notion_oauth/client.py">notion_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Notion OAuth authorization.
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
client.notion_oauth.notion_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Notion
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Notion, if any
    
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

## JiraOauth
<details><summary><code>client.jira_oauth.<a href="src/klavis/jira_oauth/client.py">authorize_jira</a>(...)</code></summary>
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
client.jira_oauth.authorize_jira(
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

<details><summary><code>client.jira_oauth.<a href="src/klavis/jira_oauth/client.py">jira_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Jira OAuth authorization.
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
client.jira_oauth.jira_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Jira
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Jira, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Jira, if any
    
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

<details><summary><code>client.jira_oauth.<a href="src/klavis/jira_oauth/client.py">refresh_jira_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Jira access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.jira_oauth.refresh_jira_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## ConfluenceOauth
<details><summary><code>client.confluence_oauth.<a href="src/klavis/confluence_oauth/client.py">authorize_confluence</a>(...)</code></summary>
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
client.confluence_oauth.authorize_confluence(
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

<details><summary><code>client.confluence_oauth.<a href="src/klavis/confluence_oauth/client.py">confluence_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Confluence OAuth authorization.
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
client.confluence_oauth.confluence_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Confluence
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Confluence, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Confluence, if any
    
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

<details><summary><code>client.confluence_oauth.<a href="src/klavis/confluence_oauth/client.py">refresh_confluence_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Confluence access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.confluence_oauth.refresh_confluence_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## WordpressOauth
<details><summary><code>client.wordpress_oauth.<a href="src/klavis/wordpress_oauth/client.py">authorize_wordpress</a>(...)</code></summary>
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
client.wordpress_oauth.authorize_wordpress(
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

<details><summary><code>client.wordpress_oauth.<a href="src/klavis/wordpress_oauth/client.py">wordpress_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from WordPress OAuth authorization.
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
client.wordpress_oauth.wordpress_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by WordPress
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by WordPress, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from WordPress, if any
    
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

## GmailOauth
<details><summary><code>client.gmail_oauth.<a href="src/klavis/gmail_oauth/client.py">authorize_gmail</a>(...)</code></summary>
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
client.gmail_oauth.authorize_gmail(
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

<details><summary><code>client.gmail_oauth.<a href="src/klavis/gmail_oauth/client.py">gmail_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Gmail OAuth authorization.
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
client.gmail_oauth.gmail_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Gmail
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Gmail, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Gmail, if any
    
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

<details><summary><code>client.gmail_oauth.<a href="src/klavis/gmail_oauth/client.py">refresh_gmail_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Gmail access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.gmail_oauth.refresh_gmail_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## GdriveOauth
<details><summary><code>client.gdrive_oauth.<a href="src/klavis/gdrive_oauth/client.py">authorize_g_drive</a>(...)</code></summary>
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
client.gdrive_oauth.authorize_g_drive(
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

<details><summary><code>client.gdrive_oauth.<a href="src/klavis/gdrive_oauth/client.py">gdrive_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Google Drive OAuth authorization.
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
client.gdrive_oauth.gdrive_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Google Drive
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Google Drive, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Google Drive, if any
    
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

<details><summary><code>client.gdrive_oauth.<a href="src/klavis/gdrive_oauth/client.py">refresh_gdrive_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Google Drive access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.gdrive_oauth.refresh_gdrive_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

<details><summary><code>client.gdrive_oauth.<a href="src/klavis/gdrive_oauth/client.py">gdrive_picker_page</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Serve the Google Drive picker page with the appropriate credentials
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
client.gdrive_oauth.gdrive_picker_page()

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

**client_id:** `typing.Optional[str]` — Client ID to use for the picker
    
</dd>
</dl>

<dl>
<dd>

**api_key:** `typing.Optional[str]` — API key to use for the picker
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — OAuth scopes for the picker
    
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

## GcalendarOauth
<details><summary><code>client.gcalendar_oauth.<a href="src/klavis/gcalendar_oauth/client.py">authorize_g_calendar</a>(...)</code></summary>
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
client.gcalendar_oauth.authorize_g_calendar(
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

<details><summary><code>client.gcalendar_oauth.<a href="src/klavis/gcalendar_oauth/client.py">gcalendar_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Google Calendar OAuth authorization.
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
client.gcalendar_oauth.gcalendar_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Google Calendar
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Google Calendar, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Google Calendar, if any
    
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

<details><summary><code>client.gcalendar_oauth.<a href="src/klavis/gcalendar_oauth/client.py">refresh_gcalendar_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Google Calendar access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.gcalendar_oauth.refresh_gcalendar_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## GsheetsOauth
<details><summary><code>client.gsheets_oauth.<a href="src/klavis/gsheets_oauth/client.py">authorize_g_sheets</a>(...)</code></summary>
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
client.gsheets_oauth.authorize_g_sheets(
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

<details><summary><code>client.gsheets_oauth.<a href="src/klavis/gsheets_oauth/client.py">gsheets_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Google Sheets OAuth authorization.
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
client.gsheets_oauth.gsheets_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Google Sheets
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Google Sheets, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Google Sheets, if any
    
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

<details><summary><code>client.gsheets_oauth.<a href="src/klavis/gsheets_oauth/client.py">refresh_gsheets_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Google Sheets access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.gsheets_oauth.refresh_gsheets_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## GdocsOauth
<details><summary><code>client.gdocs_oauth.<a href="src/klavis/gdocs_oauth/client.py">authorize_g_docs</a>(...)</code></summary>
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
client.gdocs_oauth.authorize_g_docs(
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

<details><summary><code>client.gdocs_oauth.<a href="src/klavis/gdocs_oauth/client.py">gdocs_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Google Docs OAuth authorization.
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
client.gdocs_oauth.gdocs_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Google Docs
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Google Docs, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Google Docs, if any
    
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

<details><summary><code>client.gdocs_oauth.<a href="src/klavis/gdocs_oauth/client.py">refresh_gdocs_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Google Docs access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.gdocs_oauth.refresh_gdocs_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## AttioOauth
<details><summary><code>client.attio_oauth.<a href="src/klavis/attio_oauth/client.py">authorize_attio</a>(...)</code></summary>
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
client.attio_oauth.authorize_attio(
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

<details><summary><code>client.attio_oauth.<a href="src/klavis/attio_oauth/client.py">attio_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Attio OAuth authorization.
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
client.attio_oauth.attio_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Attio
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Attio, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Attio, if any
    
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

## SalesforceOauth
<details><summary><code>client.salesforce_oauth.<a href="src/klavis/salesforce_oauth/client.py">authorize_salesforce</a>(...)</code></summary>
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
client.salesforce_oauth.authorize_salesforce(
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

<details><summary><code>client.salesforce_oauth.<a href="src/klavis/salesforce_oauth/client.py">salesforce_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Salesforce OAuth authorization.
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
client.salesforce_oauth.salesforce_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Salesforce
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Salesforce, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Salesforce, if any
    
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

<details><summary><code>client.salesforce_oauth.<a href="src/klavis/salesforce_oauth/client.py">refresh_salesforce_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Salesforce access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.salesforce_oauth.refresh_salesforce_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## AsanaOauth
<details><summary><code>client.asana_oauth.<a href="src/klavis/asana_oauth/client.py">authorize_asana</a>(...)</code></summary>
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
client.asana_oauth.authorize_asana(
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

<details><summary><code>client.asana_oauth.<a href="src/klavis/asana_oauth/client.py">asana_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Asana OAuth authorization.
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
client.asana_oauth.asana_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Asana
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Asana, if any
    
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

<details><summary><code>client.asana_oauth.<a href="src/klavis/asana_oauth/client.py">refresh_asana_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Asana access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.asana_oauth.refresh_asana_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

## LinearOauth
<details><summary><code>client.linear_oauth.<a href="src/klavis/linear_oauth/client.py">authorize_linear</a>(...)</code></summary>
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
client.linear_oauth.authorize_linear(
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

<details><summary><code>client.linear_oauth.<a href="src/klavis/linear_oauth/client.py">linear_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Linear OAuth authorization.
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
client.linear_oauth.linear_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Linear
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Linear, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from Linear, if any
    
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

## CloseOauth
<details><summary><code>client.close_oauth.<a href="src/klavis/close_oauth/client.py">authorize_close</a>(...)</code></summary>
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
client.close_oauth.authorize_close(
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

<details><summary><code>client.close_oauth.<a href="src/klavis/close_oauth/client.py">close_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from Close OAuth authorization.
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
client.close_oauth.close_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by Close
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by Close, if any
    
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

<details><summary><code>client.close_oauth.<a href="src/klavis/close_oauth/client.py">refresh_close_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refresh an expired Close access token using the stored refresh token

Parameters:
- instance_id: Identifier for the instance requesting token refresh

Returns:
- Success response if token was refreshed successfully, error response otherwise
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
client.close_oauth.refresh_close_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token refresh
    
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

<details><summary><code>client.close_oauth.<a href="src/klavis/close_oauth/client.py">revoke_close_token</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Revoke Close access and refresh tokens

Parameters:
- instance_id: Identifier for the instance requesting token revocation

Returns:
- Success response if token was revoked successfully, error response otherwise
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
client.close_oauth.revoke_close_token(
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

**instance_id:** `str` — Unique identifier for the client instance requesting token revocation
    
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

## ClickupOauth
<details><summary><code>client.clickup_oauth.<a href="src/klavis/clickup_oauth/client.py">authorize_click_up</a>(...)</code></summary>
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
client.clickup_oauth.authorize_click_up(
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

<details><summary><code>client.clickup_oauth.<a href="src/klavis/clickup_oauth/client.py">click_up_o_auth_callback</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Handles the callback from ClickUp OAuth authorization.
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
client.clickup_oauth.click_up_o_auth_callback()

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

**code:** `typing.Optional[str]` — Authorization code returned by ClickUp
    
</dd>
</dl>

<dl>
<dd>

**state:** `typing.Optional[str]` — State parameter containing encoded authorization data
    
</dd>
</dl>

<dl>
<dd>

**error:** `typing.Optional[str]` — Error code returned by ClickUp, if any
    
</dd>
</dl>

<dl>
<dd>

**error_description:** `typing.Optional[str]` — Detailed error description from ClickUp, if any
    
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

