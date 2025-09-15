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

**user_id:** `str` — The identifier for the user
    
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

Parameters:
- servers: Can be 'ALL' to delete all Klavis MCP servers, a list of specific server names, or null to delete no servers
- externalServers: Optional list of external server names to delete

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

**strata_id:** `str` — The strata server ID
    
</dd>
</dl>

<dl>
<dd>

**servers:** `typing.Optional[Servers]` — List of Klavis MCP servers to delete (e.g., 'jira', 'linear'), 'ALL' to delete all Klavis MCP servers, or null to delete no servers.
    
</dd>
</dl>

<dl>
<dd>

**external_servers:** `typing.Optional[typing.Sequence[str]]` — Optional list of external server names to delete. These are the names of previously added external MCP servers.
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_strata_instance</a>()</code></summary>
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
client.mcp_server.get_strata_instance()

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

**user_id:** `str` — The identifier for the user requesting the server URL.
    
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

**user_id:** `str` — The identifier for the user requesting the server URL.
    
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
    auth_data=ApiKeyAuth(
        token="token",
    ),
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

## GitlabOauth
<details><summary><code>client.gitlab_oauth.<a href="src/klavis/gitlab_oauth/client.py">authorize_gitlab</a>(...)</code></summary>
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
client.gitlab_oauth.authorize_gitlab(
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

## AirtableOauth
<details><summary><code>client.airtable_oauth.<a href="src/klavis/airtable_oauth/client.py">authorize_airtable</a>(...)</code></summary>
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
client.airtable_oauth.authorize_airtable(
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

## HubspotOauth
<details><summary><code>client.hubspot_oauth.<a href="src/klavis/hubspot_oauth/client.py">authorize_hubspot</a>(...)</code></summary>
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
client.hubspot_oauth.authorize_hubspot(
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

## LinkedinOauth
<details><summary><code>client.linkedin_oauth.<a href="src/klavis/linkedin_oauth/client.py">authorize_linked_in</a>(...)</code></summary>
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
client.linkedin_oauth.authorize_linked_in(
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

## CanvaOauth
<details><summary><code>client.canva_oauth.<a href="src/klavis/canva_oauth/client.py">authorize_canva</a>(...)</code></summary>
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
client.canva_oauth.authorize_canva(
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

## XeroOauth
<details><summary><code>client.xero_oauth.<a href="src/klavis/xero_oauth/client.py">authorize_xero</a>(...)</code></summary>
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
client.xero_oauth.authorize_xero(
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

## DropboxOauth
<details><summary><code>client.dropbox_oauth.<a href="src/klavis/dropbox_oauth/client.py">authorize_dropbox</a>(...)</code></summary>
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
client.dropbox_oauth.authorize_dropbox(
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

## BoxOauth
<details><summary><code>client.box_oauth.<a href="src/klavis/box_oauth/client.py">authorize_box</a>(...)</code></summary>
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
client.box_oauth.authorize_box(
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

## QuickbooksOauth
<details><summary><code>client.quickbooks_oauth.<a href="src/klavis/quickbooks_oauth/client.py">authorize_quick_books</a>(...)</code></summary>
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
client.quickbooks_oauth.authorize_quick_books(
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

## ZendeskOauth
<details><summary><code>client.zendesk_oauth.<a href="src/klavis/zendesk_oauth/client.py">authorize_zendesk</a>(...)</code></summary>
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
client.zendesk_oauth.authorize_zendesk(
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

## StripeConnectOauth
<details><summary><code>client.stripe_connect_oauth.<a href="src/klavis/stripe_connect_oauth/client.py">authorize_stripe_connect</a>(...)</code></summary>
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
client.stripe_connect_oauth.authorize_stripe_connect(
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

## CalcomOauth
<details><summary><code>client.calcom_oauth.<a href="src/klavis/calcom_oauth/client.py">authorize_calcom</a>(...)</code></summary>
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
client.calcom_oauth.authorize_calcom(
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

<details><summary><code>client.calcom_oauth.<a href="src/klavis/calcom_oauth/client.py">calcom_client_credentials_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Authenticate using Cal.com OAuth client credentials flow for platform-level API access

This endpoint is used for:
- Managing managed users
- Creating OAuth client webhooks
- Refreshing managed user tokens
- Managing organization teams and memberships

Parameters:
- instance_id: Identifier for the instance requesting authentication
- x-cal-client-id: OAuth client ID (header)
- x-cal-secret-key: OAuth client secret (header)
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
client.calcom_oauth.calcom_client_credentials_auth(
    cal_client_id="x-cal-client-id",
    cal_secret_key="x-cal-secret-key",
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

**instance_id:** `str` — Unique identifier for the client instance
    
</dd>
</dl>

<dl>
<dd>

**cal_client_id:** `str` — Cal.com OAuth client ID
    
</dd>
</dl>

<dl>
<dd>

**cal_secret_key:** `str` — Cal.com OAuth client secret
    
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

## VercelOauth
<details><summary><code>client.vercel_oauth.<a href="src/klavis/vercel_oauth/client.py">authorize_vercel</a>(...)</code></summary>
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
client.vercel_oauth.authorize_vercel(
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

## PipedriveOauth
<details><summary><code>client.pipedrive_oauth.<a href="src/klavis/pipedrive_oauth/client.py">authorize_pipedrive</a>(...)</code></summary>
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
client.pipedrive_oauth.authorize_pipedrive(
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

## FigmaOauth
<details><summary><code>client.figma_oauth.<a href="src/klavis/figma_oauth/client.py">authorize_figma</a>(...)</code></summary>
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
client.figma_oauth.authorize_figma(
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

## KlaviyoOauth
<details><summary><code>client.klaviyo_oauth.<a href="src/klavis/klaviyo_oauth/client.py">authorize_klaviyo</a>(...)</code></summary>
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
client.klaviyo_oauth.authorize_klaviyo(
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

## PagerdutyOauth
<details><summary><code>client.pagerduty_oauth.<a href="src/klavis/pagerduty_oauth/client.py">authorize_pager_duty</a>(...)</code></summary>
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
client.pagerduty_oauth.authorize_pager_duty(
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

## DocusignOauth
<details><summary><code>client.docusign_oauth.<a href="src/klavis/docusign_oauth/client.py">authorize_docu_sign</a>(...)</code></summary>
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
client.docusign_oauth.authorize_docu_sign(
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

## DialpadOauth
<details><summary><code>client.dialpad_oauth.<a href="src/klavis/dialpad_oauth/client.py">authorize_dialpad</a>(...)</code></summary>
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
client.dialpad_oauth.authorize_dialpad(
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

