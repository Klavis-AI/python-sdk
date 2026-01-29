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
- servers: Can be 'ALL' to add all available Klavis integration, a list of specific server names, or null to add no servers
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

**servers:** `typing.Optional[Servers]` — List of Klavis integration to add (e.g., 'jira', 'linear'), 'ALL' to add all Klavis integration, or null to add no servers.
    
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
- servers: Can be 'ALL' to delete all available Klavis integration, a list of specific server names, or null to delete no servers
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
    external_servers="externalServers",
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
]` — List of Klavis integration to delete (e.g., 'jira', 'linear'), 'ALL' to delete all Klavis integration, or null to delete no servers.
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_strata_server</a>(...)</code></summary>
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
client.mcp_server.get_strata_server(
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">list_strata_raw_actions</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Fetch raw actions (all underlying actions) for a specific integration within a Strata MCP instance.
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
client.mcp_server.list_strata_raw_actions(
    strata_id="strataId",
    server=McpServerName.AFFINITY,
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

**server:** `McpServerName` — The name of the server to fetch raw actions for
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_strata_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieves authentication data for a specific integration within a Strata MCP server.

Returns the authentication data if available, along with authentication status.
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
client.mcp_server.get_strata_auth(
    strata_id="strataId",
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

**strata_id:** `str` — The strata server ID
    
</dd>
</dl>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the Klavis MCP server to get authentication for (e.g., 'GitHub', 'Jira')
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">delete_strata_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes authentication data for a specific integration within a Strata MCP server.

This will clear the stored authentication credentials, effectively unauthenticating the server.
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
client.mcp_server.delete_strata_auth(
    strata_id="strataId",
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

**strata_id:** `str` — The strata server ID
    
</dd>
</dl>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the Klavis MCP server to delete authentication for (e.g., 'github', 'jira')
    
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
Note that some servers have hundreds of tools and therefore only expose the Strata tools.
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

**legacy:** `typing.Optional[bool]` — Whether to use the legacy server. Default is False.
    
</dd>
</dl>

<dl>
<dd>

**is_read_only:** `typing.Optional[bool]` — Whether the MCP server connection is read-only. When true, write operations will be restricted. Default is False.
    
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

**instance_id:** `str` — The ID of the connection integration instance whose status is being checked. This is returned by the Create API.
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">update_server_instance</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the settings of a specific server connection instance.
Currently supports updating the read-only status of the connection.
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
client.mcp_server.update_server_instance(
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

**instance_id:** `str` — The ID of the connection integration instance to update.
    
</dd>
</dl>

<dl>
<dd>

**is_read_only:** `typing.Optional[bool]` — Whether the MCP server connection is read-only. When true, write operations will be restricted.
    
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

Retrieves the auth data for a specific integration instance that the API key owner controls.
Includes access token, refresh token, and other authentication data.

This endpoint includes proper ownership verification to ensure users can only access
authentication data for integration instances they own. It also handles token refresh if needed.
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

**instance_id:** `str` — The ID of the connection integration instance to get auth data for.
    
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
from klavis import Klavis, McpServerName, ToolFormat

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.mcp_server.get_tools(
    server_name=McpServerName.AFFINITY,
    format=ToolFormat.OPENAI,
    legacy=True,
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

**legacy:** `typing.Optional[bool]` — Whether to use the legacy server. Default is False.
    
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

Sets authentication data for a specific integration instance.
Accepts either API key authentication or general authentication data.
This updates the auth_metadata for the specified integration instance.
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

**auth_data:** `SetAuthRequestAuthData` — Authentication data
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">list_raw_actions</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Fetch raw actions (all underlying actions) for a specific integration instance.

This endpoint takes an instance ID, and then fetches the raw actions with categories.
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
client.mcp_server.list_raw_actions(
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

**instance_id:** `str` — The instance ID for the server connection
    
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

<details><summary><code>client.mcp_server.<a href="src/klavis/mcp_server/client.py">get_oauth_url</a>()</code></summary>
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
client.mcp_server.get_oauth_url()

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
<details><summary><code>client.user.<a href="src/klavis/user/client.py">get_user_integrations</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get all available integrations (MCP server names) by user ID.
Returns a list of integration names and their authentication status.
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
client.user.get_user_integrations(
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

**user_id:** `str` — The external user ID
    
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

<details><summary><code>client.user.<a href="src/klavis/user/client.py">get_user_by_user_id</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get user information by user_id.
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
client.user.get_user_by_user_id(
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

**user_id:** `str` — The identifier for the user to fetch.
    
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

<details><summary><code>client.user.<a href="src/klavis/user/client.py">get_all_users</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all users that have been created under your account, with support for pagination.
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
client.user.get_all_users(
    page_size=1,
    page_number=1,
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

**page_size:** `typing.Optional[int]` — Number of results per page (max 1000)
    
</dd>
</dl>

<dl>
<dd>

**page_number:** `typing.Optional[int]` — Page number to retrieve (starting from 1)
    
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

<details><summary><code>client.user.<a href="src/klavis/user/client.py">set_user_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Sets authentication data for a specific integration for a user.

Accepts either API key authentication or general authentication data.
This updates the auth_metadata for the specified user's integration instance.
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
client.user.set_user_auth(
    user_id="userId",
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

**user_id:** `str` — The unique identifier for the user
    
</dd>
</dl>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the MCP server to set authentication for (e.g., 'GitHub', 'Jira')
    
</dd>
</dl>

<dl>
<dd>

**auth_data:** `SetUserAuthRequestAuthData` — Authentication data
    
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

<details><summary><code>client.user.<a href="src/klavis/user/client.py">get_user_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieves authentication data for a specific integration for a user.

Returns the authentication data if available, along with authentication status.
Includes token refresh handling if needed.
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
client.user.get_user_auth(
    user_id="userId",
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

**user_id:** `str` — The identifier for the user
    
</dd>
</dl>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the MCP server (e.g., 'GitHub', 'Jira')
    
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

<details><summary><code>client.user.<a href="src/klavis/user/client.py">delete_user_auth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deletes authentication data for a specific integration for a user.

This will clear the stored authentication credentials, effectively unauthenticating the integration.
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
client.user.delete_user_auth(
    user_id="userId",
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

**user_id:** `str` — The unique identifier for the user
    
</dd>
</dl>

<dl>
<dd>

**server_name:** `McpServerName` — The name of the MCP server to delete authentication for (e.g., 'github', 'jira')
    
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
    client_id="client_id",
    scope="scope",
    user_scope="user_scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
    instance_url="instance_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
from klavis.oauth import Environment

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.oauth.authorize_quickbooks(
    instance_id="instance_id",
    client_id="client_id",
    environment=Environment.SANDBOX,
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    redirect_url="redirect_url",
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
    client_id="client_id",
    client_slug="client_slug",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
    code_challenge="code_challenge",
    code_challenge_method="code_challenge_method",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_teams</a>(...)</code></summary>
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
client.oauth.authorize_teams(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_fathom</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Fathom OAuth flow

Parameters:
- instance_id: Identifier for the instance requesting authorization
- client_id: Optional client ID for white labeling
- scope: Optional scopes to request
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
client.oauth.authorize_fathom(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_monday</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Monday OAuth flow

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
client.oauth.authorize_monday(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

<details><summary><code>client.oauth.<a href="src/klavis/oauth/client.py">authorize_shopify</a>()</code></summary>
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
client.oauth.authorize_shopify()

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

## GoogleCloudOauth
<details><summary><code>client.google_cloud_oauth.<a href="src/klavis/google_cloud_oauth/client.py">authorize_google_cloud</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Google Cloud OAuth flow

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
client.google_cloud_oauth.authorize_google_cloud(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

## GoogleFormsOauth
<details><summary><code>client.google_forms_oauth.<a href="src/klavis/google_forms_oauth/client.py">authorize_google_forms</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Google Forms OAuth flow

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
client.google_forms_oauth.authorize_google_forms(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

## OnedriveOauth
<details><summary><code>client.onedrive_oauth.<a href="src/klavis/onedrive_oauth/client.py">refresh_token</a>(...)</code></summary>
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
client.onedrive_oauth.refresh_token(
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

**instance_id:** `str` — Instance ID for which to refresh the token
    
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

## OutlookOauth
<details><summary><code>client.outlook_oauth.<a href="src/klavis/outlook_oauth/client.py">refresh_token</a>(...)</code></summary>
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
client.outlook_oauth.refresh_token(
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

**instance_id:** `str` — Instance ID for which to refresh the token
    
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

## MscalendarOauth
<details><summary><code>client.mscalendar_oauth.<a href="src/klavis/mscalendar_oauth/client.py">authorize_ms_calendar</a>(...)</code></summary>
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
client.mscalendar_oauth.authorize_ms_calendar(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

<details><summary><code>client.mscalendar_oauth.<a href="src/klavis/mscalendar_oauth/client.py">refresh_token</a>(...)</code></summary>
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
client.mscalendar_oauth.refresh_token(
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

**instance_id:** `str` — Instance ID for which to refresh the token
    
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

## TeamsOauth
<details><summary><code>client.teams_oauth.<a href="src/klavis/teams_oauth/client.py">refresh_token</a>(...)</code></summary>
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
client.teams_oauth.refresh_token(
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

**instance_id:** `str` — Instance ID for which to refresh the token
    
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

## ZoomOauth
<details><summary><code>client.zoom_oauth.<a href="src/klavis/zoom_oauth/client.py">authorize_zoom</a>(...)</code></summary>
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
client.zoom_oauth.authorize_zoom(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

## ZohoMailOauth
<details><summary><code>client.zoho_mail_oauth.<a href="src/klavis/zoho_mail_oauth/client.py">authorize_zoho_mail</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start Zoho Mail OAuth flow

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
client.zoho_mail_oauth.authorize_zoho_mail(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

## SharesightOauth
<details><summary><code>client.sharesight_oauth.<a href="src/klavis/sharesight_oauth/client.py">authorize_sharesight</a>(...)</code></summary>
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
client.sharesight_oauth.authorize_sharesight(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

## InstagramOauth
<details><summary><code>client.instagram_oauth.<a href="src/klavis/instagram_oauth/client.py">authorize_instagram</a>(...)</code></summary>
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
client.instagram_oauth.authorize_instagram(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

## YoutubeOauth
<details><summary><code>client.youtube_oauth.<a href="src/klavis/youtube_oauth/client.py">authorize_you_tube</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start YouTube OAuth flow

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
client.youtube_oauth.authorize_you_tube(
    instance_id="instance_id",
    client_id="client_id",
    scope="scope",
    redirect_url="redirect_url",
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

## IntercomOauth
<details><summary><code>client.intercom_oauth.<a href="src/klavis/intercom_oauth/client.py">authorizeintercom_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.intercom_oauth.authorizeintercom_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## PaypalOauth
<details><summary><code>client.paypal_oauth.<a href="src/klavis/paypal_oauth/client.py">authorizepaypal_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.paypal_oauth.authorizepaypal_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## SentryOauth
<details><summary><code>client.sentry_oauth.<a href="src/klavis/sentry_oauth/client.py">authorizesentry_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.sentry_oauth.authorizesentry_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## NetlifyOauth
<details><summary><code>client.netlify_oauth.<a href="src/klavis/netlify_oauth/client.py">authorizenetlify_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.netlify_oauth.authorizenetlify_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## HuggingfaceOauth
<details><summary><code>client.huggingface_oauth.<a href="src/klavis/huggingface_oauth/client.py">authorizehuggingface_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.huggingface_oauth.authorizehuggingface_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## SquareOauth
<details><summary><code>client.square_oauth.<a href="src/klavis/square_oauth/client.py">authorizesquare_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.square_oauth.authorizesquare_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## ClockwiseOauth
<details><summary><code>client.clockwise_oauth.<a href="src/klavis/clockwise_oauth/client.py">authorizeclockwise_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.clockwise_oauth.authorizeclockwise_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## JotformOauth
<details><summary><code>client.jotform_oauth.<a href="src/klavis/jotform_oauth/client.py">authorizejotform_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.jotform_oauth.authorizejotform_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## HoneycombOauth
<details><summary><code>client.honeycomb_oauth.<a href="src/klavis/honeycomb_oauth/client.py">authorizehoneycomb_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.honeycomb_oauth.authorizehoneycomb_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## AmplitudeOauth
<details><summary><code>client.amplitude_oauth.<a href="src/klavis/amplitude_oauth/client.py">authorizeamplitude_oauth</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Start OAuth flow and redirect to authorization page.
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
client.amplitude_oauth.authorizeamplitude_oauth(
    instance_id="instance_id",
    redirect_url="redirect_url",
    force_refresh=True,
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

**instance_id:** `str` — Unique identifier for the MCP connection
    
</dd>
</dl>

<dl>
<dd>

**redirect_url:** `typing.Optional[str]` — Optional URL to redirect to after authorization
    
</dd>
</dl>

<dl>
<dd>

**force_refresh:** `typing.Optional[bool]` — Force re-authorization even if valid tokens exist
    
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

## Sandbox
<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">create_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Acquire an idle sandbox instance for a specific MCP server. The sandbox will be marked as 'occupied'. Optionally specify a test_account_email to acquire a specific test account.
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
from klavis import Klavis, SandboxMcpServer

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.create_sandbox(
    server_name=SandboxMcpServer.JIRA,
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

**server_name:** `SandboxMcpServer` — The MCP server name
    
</dd>
</dl>

<dl>
<dd>

**test_account_email:** `typing.Optional[str]` — Optional email of a specific test account to acquire. If provided, the system will attempt to acquire the sandbox associated with this test account email instead of a random idle sandbox.
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">get_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve detailed information about a specific sandbox instance.
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
from klavis import Klavis, SandboxMcpServer

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.get_sandbox(
    server_name=SandboxMcpServer.JIRA,
    sandbox_id="sandbox_id",
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

**server_name:** `SandboxMcpServer` — The MCP server name
    
</dd>
</dl>

<dl>
<dd>

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">delete_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Release an occupied sandbox back to idle state and marks the sandbox as available for reuse.
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
from klavis import Klavis, SandboxMcpServer

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.delete_sandbox(
    server_name=SandboxMcpServer.JIRA,
    sandbox_id="sandbox_id",
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

**server_name:** `SandboxMcpServer` — The MCP server name
    
</dd>
</dl>

<dl>
<dd>

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">reset_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reset the sandbox to its initial empty state, clearing all data while maintaining the sandbox instance.
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
from klavis import Klavis, SandboxMcpServer

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.reset_sandbox(
    server_name=SandboxMcpServer.JIRA,
    sandbox_id="sandbox_id",
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

**server_name:** `SandboxMcpServer` — The MCP server name
    
</dd>
</dl>

<dl>
<dd>

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_local_dev</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upload files to the local dev workspace at /workspace.
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
client.sandbox.initialize_local_dev(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**files:** `from __future__ import annotations

typing.List[core.File]` — See core.File for more documentation
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_local_dev</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Download all files from local dev as a tar archive.
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
client.sandbox.dump_local_dev(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_jira_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with jira-specific data following the defined schema.
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
from klavis import (
    JiraBoard,
    JiraComment,
    JiraDataInput,
    JiraIssue,
    JiraProject,
    JiraSprint,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_jira_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=JiraDataInput(
        projects=[
            JiraProject(
                key="SAND",
                name="Sandbox Project Alpha",
                description="Main sandbox project for testing and development",
                project_type="software",
                issues=[
                    JiraIssue(
                        summary="Set up project infrastructure",
                        description="Initialize project repository, CI/CD pipeline, and development environment",
                        issue_type="Task",
                        priority="High",
                        sprint_name="Sprint 1 - Foundation",
                        comments=[
                            JiraComment(
                                body="Repository created and initial structure set up",
                            ),
                            JiraComment(
                                body="CI/CD pipeline configured with GitHub Actions",
                            ),
                        ],
                    ),
                    JiraIssue(
                        summary="Implement user authentication",
                        description="Create authentication system with JWT tokens",
                        issue_type="Story",
                        priority="Highest",
                        sprint_name="Sprint 1 - Foundation",
                        comments=[
                            JiraComment(
                                body="Should we use OAuth2 or custom JWT implementation?",
                            ),
                            JiraComment(
                                body="Let's go with OAuth2 for better security and flexibility",
                            ),
                            JiraComment(
                                body="OAuth2 implementation completed and tested",
                            ),
                        ],
                    ),
                    JiraIssue(
                        summary="Design database schema",
                        description="Create entity-relationship diagrams and database migrations",
                        issue_type="Task",
                        priority="High",
                        sprint_name="Sprint 1 - Foundation",
                        comments=[
                            JiraComment(
                                body="ER diagram draft completed, ready for review",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Build REST API endpoints",
                        description="Implement CRUD operations for core entities",
                        issue_type="Story",
                        priority="High",
                        sprint_name="Sprint 2 - Core Features",
                        comments=[
                            JiraComment(
                                body="API specification documented using OpenAPI 3.0",
                            ),
                            JiraComment(
                                body="Endpoints for user management completed",
                            ),
                        ],
                    ),
                    JiraIssue(
                        summary="Implement data validation",
                        description="Add input validation and error handling",
                        issue_type="Task",
                        priority="Medium",
                        sprint_name="Sprint 2 - Core Features",
                        comments=[
                            JiraComment(
                                body="body",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Create frontend components",
                        description="Build reusable React components for the UI",
                        issue_type="Story",
                        priority="Medium",
                        sprint_name="Sprint 2 - Core Features",
                        comments=[
                            JiraComment(
                                body="Using shadcn/ui for component library",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Write unit tests",
                        description="Achieve 80% code coverage with unit tests",
                        issue_type="Task",
                        priority="High",
                        sprint_name="Sprint 3 - Testing & Polish",
                        comments=[
                            JiraComment(
                                body="Using pytest for backend tests",
                            ),
                            JiraComment(
                                body="Jest configured for frontend testing",
                            ),
                        ],
                    ),
                    JiraIssue(
                        summary="Fix login bug on mobile",
                        description="Users cannot log in on iOS devices",
                        issue_type="Bug",
                        priority="Highest",
                        sprint_name="Sprint 3 - Testing & Polish",
                        comments=[
                            JiraComment(
                                body="Bug confirmed on iPhone 14 and 15",
                            ),
                            JiraComment(
                                body="Issue was related to viewport height calculation",
                            ),
                            JiraComment(
                                body="Fix deployed and verified",
                            ),
                        ],
                    ),
                    JiraIssue(
                        summary="Research new technology stack",
                        description="Evaluate alternatives for current tech stack",
                        issue_type="Task",
                        priority="Low",
                        comments=[
                            JiraComment(
                                body="Considering FastAPI vs Flask for backend",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Update documentation",
                        description="Keep API documentation up to date",
                        issue_type="Task",
                        priority="Medium",
                        comments=[
                            JiraComment(
                                body="body",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Performance optimization backlog",
                        description="List of performance improvements to consider",
                        issue_type="Epic",
                        priority="Low",
                        comments=[
                            JiraComment(
                                body="Database query optimization should be prioritized",
                            ),
                            JiraComment(
                                body="Consider implementing Redis caching",
                            ),
                        ],
                    ),
                ],
            ),
            JiraProject(
                key="TEST",
                name="Testing Project Beta",
                description="Secondary project for QA and integration testing",
                project_type="software",
                issues=[
                    JiraIssue(
                        summary="Conduct integration testing",
                        description="Test integration between frontend and backend",
                        issue_type="Task",
                        priority="High",
                        sprint_name="QA Sprint 1",
                        comments=[
                            JiraComment(
                                body="All critical paths tested successfully",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Perform security audit",
                        description="Run security scans and penetration testing",
                        issue_type="Task",
                        priority="Highest",
                        sprint_name="QA Sprint 1",
                        comments=[
                            JiraComment(
                                body="Using OWASP ZAP for security testing",
                            ),
                            JiraComment(
                                body="Two medium severity issues found",
                            ),
                        ],
                    ),
                    JiraIssue(
                        summary="Set up test data generators",
                        description="Create utilities to generate test data",
                        issue_type="Task",
                        priority="Medium",
                        comments=[
                            JiraComment(
                                body="Using Faker library for test data generation",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Document test scenarios",
                        description="Create comprehensive test case documentation",
                        issue_type="Task",
                        priority="Medium",
                        comments=[
                            JiraComment(
                                body="body",
                            )
                        ],
                    ),
                ],
            ),
            JiraProject(
                key="DOCS",
                name="Documentation Project",
                description="Project for managing documentation and knowledge base",
                project_type="business",
                issues=[
                    JiraIssue(
                        summary="Write getting started guide",
                        description="Create beginner-friendly onboarding documentation",
                        issue_type="Task",
                        priority="High",
                        comments=[
                            JiraComment(
                                body="Draft completed and ready for review",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Create API reference documentation",
                        description="Auto-generate API docs from OpenAPI spec",
                        issue_type="Task",
                        priority="High",
                        comments=[
                            JiraComment(
                                body="body",
                            )
                        ],
                    ),
                    JiraIssue(
                        summary="Record tutorial videos",
                        description="Create video tutorials for common workflows",
                        issue_type="Task",
                        priority="Low",
                        comments=[
                            JiraComment(
                                body="Script written for first video",
                            ),
                            JiraComment(
                                body="Need to set up recording equipment",
                            ),
                        ],
                    ),
                ],
            ),
        ],
        boards=[
            JiraBoard(
                name="Alpha Development Board",
                type="scrum",
                project_key="SAND",
            ),
            JiraBoard(
                name="Alpha Kanban Board",
                type="kanban",
                project_key="SAND",
            ),
            JiraBoard(
                name="Beta Testing Board",
                type="scrum",
                project_key="TEST",
            ),
        ],
        sprints=[
            JiraSprint(
                name="Sprint 1 - Foundation",
                start_date="2024-01-01T00:00:00.000Z",
                end_date="2024-01-14T23:59:59.999Z",
                origin_board_name="Alpha Development Board",
            ),
            JiraSprint(
                name="Sprint 2 - Core Features",
                start_date="2024-01-15T00:00:00.000Z",
                end_date="2024-01-28T23:59:59.999Z",
                origin_board_name="Alpha Development Board",
            ),
            JiraSprint(
                name="Sprint 3 - Testing & Polish",
                start_date="2024-01-29T00:00:00.000Z",
                end_date="2024-02-11T23:59:59.999Z",
                origin_board_name="Alpha Development Board",
            ),
            JiraSprint(
                name="QA Sprint 1",
                start_date="2024-02-01T00:00:00.000Z",
                end_date="2024-02-14T23:59:59.999Z",
                origin_board_name="Beta Testing Board",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[JiraDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_jira_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_jira_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_google_calendar_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with google_calendar-specific data following the defined schema.
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
from klavis import (
    GoogleCalendarAttendee,
    GoogleCalendarDataInput,
    GoogleCalendarEvent,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_google_calendar_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GoogleCalendarDataInput(
        events=[
            GoogleCalendarEvent(
                title="Team Standup",
                start_time="2025-12-01T09:00:00-08:00",
                end_time="2025-12-01T09:30:00-08:00",
                timezone="America/Los_Angeles",
                description="Daily team standup meeting to discuss progress and blockers",
                attendees=[
                    GoogleCalendarAttendee(
                        email="team@example.com",
                    )
                ],
            ),
            GoogleCalendarEvent(
                title="Client Meeting - Q4 Review",
                start_time="2025-12-02T14:00:00-08:00",
                end_time="2025-12-02T15:30:00-08:00",
                timezone="America/Los_Angeles",
                description="Quarterly business review with key client stakeholders",
                location="Conference Room A",
                visibility="private",
                attendees=[
                    GoogleCalendarAttendee(
                        email="client@example.com",
                    ),
                    GoogleCalendarAttendee(
                        email="sales@example.com",
                    ),
                ],
            ),
            GoogleCalendarEvent(
                title="Project Planning Session",
                start_time="2025-12-03T10:00:00-08:00",
                end_time="2025-12-03T12:00:00-08:00",
                timezone="America/Los_Angeles",
                description="Q1 2026 project planning and resource allocation",
                location="Main Office - Building 2",
                attendees=[
                    GoogleCalendarAttendee(
                        email="team@example.com",
                    ),
                    GoogleCalendarAttendee(
                        email="manager@example.com",
                    ),
                    GoogleCalendarAttendee(
                        email="product@example.com",
                        is_optional=True,
                    ),
                ],
            ),
            GoogleCalendarEvent(
                title="One-on-One with Manager",
                start_time="2025-12-05T15:00:00-08:00",
                end_time="2025-12-05T15:30:00-08:00",
                timezone="America/Los_Angeles",
                description="Monthly check-in and career development discussion",
                visibility="private",
                attendees=[
                    GoogleCalendarAttendee(
                        email="manager@example.com",
                    )
                ],
            ),
            GoogleCalendarEvent(
                title="Team Lunch",
                start_time="2025-12-07T12:00:00-08:00",
                end_time="2025-12-07T13:30:00-08:00",
                timezone="America/Los_Angeles",
                description="Team building lunch and informal catch-up",
                location="Restaurant Downtown",
                attendees=[
                    GoogleCalendarAttendee(
                        email="team@example.com",
                    )
                ],
            ),
            GoogleCalendarEvent(
                title="All-Day Company Offsite",
                start_date="2025-12-10",
                end_date="2025-12-11",
                description="Annual company offsite for strategic planning",
                location="Retreat Center",
                attendees=[
                    GoogleCalendarAttendee(
                        email="everyone@example.com",
                    )
                ],
            ),
            GoogleCalendarEvent(
                title="Product Demo Webinar",
                start_time="2025-12-12T11:00:00-08:00",
                end_time="2025-12-12T12:00:00-08:00",
                timezone="America/Los_Angeles",
                description="Public webinar showcasing new product features",
                visibility="public",
                attendees=[
                    GoogleCalendarAttendee(
                        email="marketing@example.com",
                    ),
                    GoogleCalendarAttendee(
                        email="product@example.com",
                    ),
                ],
            ),
            GoogleCalendarEvent(
                title="Sprint Retrospective",
                start_time="2025-12-13T16:00:00-08:00",
                end_time="2025-12-13T17:00:00-08:00",
                timezone="America/Los_Angeles",
                description="Reflect on the sprint and identify improvements",
                attendees=[
                    GoogleCalendarAttendee(
                        email="team@example.com",
                    ),
                    GoogleCalendarAttendee(
                        email="scrum-master@example.com",
                    ),
                ],
            ),
            GoogleCalendarEvent(
                title="Budget Review - Finance",
                start_time="2025-12-15T13:00:00-08:00",
                end_time="2025-12-15T14:30:00-08:00",
                timezone="America/Los_Angeles",
                description="Q4 budget review and variance analysis",
                location="Finance Conference Room",
                visibility="confidential",
                attendees=[
                    GoogleCalendarAttendee(
                        email="finance@example.com",
                    ),
                    GoogleCalendarAttendee(
                        email="manager@example.com",
                    ),
                ],
            ),
            GoogleCalendarEvent(
                title="Holiday Party Planning",
                start_time="2025-12-18T14:00:00-08:00",
                end_time="2025-12-18T15:00:00-08:00",
                timezone="America/Los_Angeles",
                description="Planning meeting for the annual holiday celebration",
                attendees=[
                    GoogleCalendarAttendee(
                        email="events@example.com",
                    ),
                    GoogleCalendarAttendee(
                        email="hr@example.com",
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GoogleCalendarDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_google_calendar_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_google_calendar_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_gmail_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with gmail-specific data following the defined schema.
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
from klavis import GmailData, GmailDraft, GmailMessage, Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_gmail_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GmailData(
        messages=[
            GmailMessage(
                subject="Weekly Team Update",
                to="johndoe@klavis.ai",
                cc="johndoe@klavis.ai",
                body="Hi Team,\n\nHere's our weekly update:\n\n1. Project A is on track\n2. Sprint planning next week\n3. New hire starting Monday\n\nBest regards",
                labels=["INBOX", "IMPORTANT"],
            ),
            GmailMessage(
                subject="Project Status Report",
                to="johndoe@klavis.ai",
                body="Dear Client,\n\nI'm writing to update you on the project status. All milestones are being met on schedule.\n\nKey accomplishments this week:\n- Completed Phase 1\n- Initiated Phase 2\n- Stakeholder review meeting scheduled\n\nLooking forward to our next meeting.\n\nBest regards",
                labels=["INBOX"],
            ),
            GmailMessage(
                subject="Follow-up on Support Ticket #12345",
                to="johndoe@klavis.ai",
                body="Hello Support Team,\n\nI wanted to follow up on ticket #12345. Has there been any progress on this issue?\n\nThank you for your assistance.\n\nBest regards",
                labels=["INBOX"],
            ),
            GmailMessage(
                subject="Meeting Notes - Q4 Planning",
                to="johndoe@klavis.ai",
                cc="johndoe@klavis.ai",
                body="Hi everyone,\n\nAttached are the notes from our Q4 planning session:\n\n- Budget allocation approved\n- New initiatives prioritized\n- Timeline established\n\nPlease review and provide feedback by EOW.\n\nThanks",
                labels=["INBOX", "CATEGORY_UPDATES"],
            ),
            GmailMessage(
                subject="Quarterly Review Reminder",
                to="johndoe@klavis.ai",
                body="Team,\n\nFriendly reminder that quarterly reviews are due next Friday.\n\nPlease complete your self-assessment and submit to your manager.\n\nThank you!",
                labels=["INBOX"],
            ),
        ],
        drafts=[
            GmailDraft(
                subject="Re: Partnership Proposal",
                to="partner@example.com",
                body="Hi there,\n\nThank you for reaching out regarding the partnership opportunity. I'm very interested in learning more.\n\nCould we schedule a call next week to discuss further?\n\nBest regards",
            ),
            GmailDraft(
                subject="Vacation Request - December",
                to="hr@example.com",
                cc="manager@example.com",
                body="Dear HR,\n\nI would like to request vacation time from December 20-30, 2024.\n\nPlease let me know if you need any additional information.\n\nThank you",
            ),
            GmailDraft(
                subject="Product Feedback",
                to="product@example.com",
                body="Hi Product Team,\n\nI wanted to share some feedback on the recent update:\n\n1. The new dashboard is much more intuitive\n2. Performance has improved significantly\n3. One suggestion: add keyboard shortcuts\n\nOverall, great work!\n\nBest",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GmailData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_gmail_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_gmail_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_google_docs_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with google_docs-specific data following the defined schema.
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
from klavis import GoogleDocsData, GoogleDocsDocument, Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_google_docs_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GoogleDocsData(
        documents=[
            GoogleDocsDocument(
                title="Team Meeting Agenda",
                content="# Team Meeting Agenda\n\n## Date: January 15, 2025\n\n### Topics:\n1. Q1 Goals Review\n2. Project Updates\n3. Resource Allocation\n4. Action Items\n\n### Attendees:\n- John Doe (Project Manager)\n- Jane Smith (Tech Lead)\n- Bob Johnson (Designer)\n- Alice Williams (QA Lead)\n\n### Notes:\nDiscuss upcoming product launch and timeline adjustments.",
            ),
            GoogleDocsDocument(
                title="Product Roadmap 2025",
                content="# Product Roadmap 2025\n\n## Q1 (January - March)\n- Feature A development and testing\n- Beta program launch\n- User feedback collection\n\n## Q2 (April - June)\n- Feature B public launch\n- Mobile app development begins\n- Integration with third-party services\n\n## Q3 (July - September)\n- Performance optimization sprint\n- Mobile app beta release\n- Advanced analytics implementation\n\n## Q4 (October - December)\n- Year-end feature freeze\n- Comprehensive security audit\n- Planning for 2026 initiatives",
            ),
            GoogleDocsDocument(
                title="Project Proposal - Customer Portal",
                content="# Project Proposal: Customer Portal\n\n## Executive Summary\nThis proposal outlines the development of a new customer self-service portal designed to improve user experience and reduce support ticket volume.\n\n## Business Objectives\n1. Enhance customer self-service capabilities\n2. Reduce support workload by 30%\n3. Improve customer satisfaction scores by 25%\n4. Enable 24/7 account management access\n\n## Technical Requirements\n- Responsive web design\n- Mobile-first approach\n- Integration with existing CRM\n- Real-time data synchronization\n\n## Project Timeline\n- Planning Phase: 2 weeks\n- Design Phase: 3 weeks\n- Development Phase: 8 weeks\n- Testing Phase: 2 weeks\n- Deployment: Week 16\n\n## Budget Estimate\nTotal Project Cost: $150,000\n- Development: $100,000\n- Design: $25,000\n- Testing & QA: $15,000\n- Deployment & Training: $10,000",
            ),
            GoogleDocsDocument(
                title="Employee Handbook 2025",
                content="# Employee Handbook\n\n## Welcome\nWelcome to our company! This handbook provides essential information about company policies, benefits, and expectations.\n\n## Core Values\n1. Innovation\n2. Integrity\n3. Collaboration\n4. Customer Focus\n\n## Working Hours\nStandard working hours are 9:00 AM - 5:00 PM, Monday through Friday. Flexible arrangements available.\n\n## Benefits\n- Health insurance\n- 401(k) matching\n- Paid time off\n- Professional development budget\n\n## Code of Conduct\nAll employees are expected to maintain professional behavior and respect for colleagues.",
            ),
            GoogleDocsDocument(
                title="Marketing Campaign Strategy",
                content="# Q2 Marketing Campaign Strategy\n\n## Campaign Overview\nLaunch integrated marketing campaign for new product line targeting small business owners.\n\n## Target Audience\n- Small business owners (1-50 employees)\n- Age range: 30-55\n- Tech-savvy professionals\n\n## Channels\n1. Social Media (LinkedIn, Twitter)\n2. Email Marketing\n3. Content Marketing (Blog, Webinars)\n4. Paid Search (Google Ads)\n\n## Budget Allocation\n- Social Media: $30,000\n- Email: $10,000\n- Content: $20,000\n- Paid Search: $40,000\n\n## Success Metrics\n- Lead generation: 500+ qualified leads\n- Conversion rate: 15%\n- ROI: 3x investment",
            ),
            GoogleDocsDocument(
                title="Technical Architecture Document",
                content="# System Architecture Documentation\n\n## Overview\nThis document describes the technical architecture of our core platform.\n\n## System Components\n\n### Frontend Layer\n- React-based SPA\n- Material-UI component library\n- Redux state management\n\n### Backend Layer\n- Node.js microservices\n- RESTful API architecture\n- PostgreSQL database\n- Redis caching layer\n\n### Infrastructure\n- AWS cloud hosting\n- Docker containerization\n- Kubernetes orchestration\n- CI/CD with GitHub Actions\n\n## Security Considerations\n- OAuth 2.0 authentication\n- End-to-end encryption\n- Regular security audits\n- GDPR compliance\n\n## Scalability\nSystem designed to handle 100,000 concurrent users with auto-scaling capabilities.",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GoogleDocsData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_google_docs_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_google_docs_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_google_drive_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with google_drive-specific data following the defined schema.
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
from klavis import GoogleDriveData, GoogleDriveFile, Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_google_drive_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GoogleDriveData(
        files=[
            GoogleDriveFile(
                name="Project Documents",
                mime_type="application/vnd.google-apps.folder",
                description="Main folder for project documentation",
            ),
            GoogleDriveFile(
                name="Reports",
                mime_type="application/vnd.google-apps.folder",
                description="Quarterly and annual reports",
            ),
            GoogleDriveFile(
                name="Project Plan",
                mime_type="application/vnd.google-apps.document",
                description="Main project planning document",
                content="# Project Plan\n\nThis is a comprehensive project plan document outlining goals, milestones, and deliverables.",
            ),
            GoogleDriveFile(
                name="Meeting Notes",
                mime_type="application/vnd.google-apps.document",
                description="Team meeting notes and action items",
                content="# Meeting Notes\n\n## 2025-01-15 - Kickoff Meeting\n- Discussed project scope\n- Assigned team roles\n- Set initial deadlines\n\n## 2025-02-01 - Progress Review\n- Reviewed Q1 deliverables\n- Adjusted timeline\n- Budget discussion",
            ),
            GoogleDriveFile(
                name="Q1 Budget Report",
                mime_type="application/vnd.google-apps.document",
                description="First quarter budget analysis",
                content="# Q1 Budget Report\n\n## Summary\nTotal Budget: $250,000\nSpent: $180,000\nRemaining: $70,000\n\n## Breakdown\n- Personnel: $120,000\n- Infrastructure: $40,000\n- Marketing: $20,000",
            ),
            GoogleDriveFile(
                name="Team Roster",
                mime_type="application/vnd.google-apps.spreadsheet",
                description="Complete team member directory",
            ),
            GoogleDriveFile(
                name="Sales Dashboard 2025",
                mime_type="application/vnd.google-apps.spreadsheet",
                description="Real-time sales tracking and analytics",
            ),
            GoogleDriveFile(
                name="Product Presentation",
                mime_type="application/vnd.google-apps.presentation",
                description="Quarterly product showcase slides",
            ),
            GoogleDriveFile(
                name="README",
                mime_type="application/vnd.google-apps.document",
                content="# Welcome to the Project Workspace\n\nThis Drive contains all project-related documents, spreadsheets, and presentations.\n\n## Folder Structure\n- Project Documents: Planning and documentation\n- Reports: Quarterly reports and analytics\n\n## Getting Started\n1. Review the Project Plan\n2. Check Meeting Notes for latest updates\n3. Access shared resources in respective folders",
            ),
            GoogleDriveFile(
                name="Company Logo.png",
                mime_type="image/png",
                description="Official company logo file",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GoogleDriveData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_google_drive_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_google_drive_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_google_forms_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with google_forms-specific data following the defined schema.
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
from klavis import (
    GoogleFormsChoiceOption,
    GoogleFormsDataInput,
    GoogleFormsForm,
    GoogleFormsItem,
    GoogleFormsItemOutputItemType,
    GoogleFormsQuestion,
    GoogleFormsQuestionQuestionType,
    GoogleFormsSectionHeader,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_google_forms_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GoogleFormsDataInput(
        forms=[
            GoogleFormsForm(
                title="Customer Satisfaction Survey",
                description="Please take a moment to share your feedback about our services. Your responses help us improve!",
                is_quiz=False,
                items=[
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Overall Experience",
                            description="Please rate your overall experience with our service",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SCALE,
                            scale_low=1,
                            scale_high=5,
                            scale_low_label="Very Dissatisfied",
                            scale_high_label="Very Satisfied",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="How did you hear about us?",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.MULTIPLE_CHOICE,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Search Engine",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Social Media",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Friend or Family",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Advertisement",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Other",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Which features do you use most?",
                            description="Select all that apply",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.CHECKBOX,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Dashboard",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Reports",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Analytics",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Integrations",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Mobile App",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Additional Comments",
                            description="Please share any additional feedback or suggestions",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.PARAGRAPH,
                        ),
                    ),
                ],
            ),
            GoogleFormsForm(
                title="Event Registration Form",
                description="Register for our upcoming annual conference. Limited seats available!",
                is_quiz=False,
                items=[
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.SECTION_HEADER,
                        section_header=GoogleFormsSectionHeader(
                            title="Personal Information",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Full Name",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SHORT_TEXT,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Email Address",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SHORT_TEXT,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Company/Organization",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.SHORT_TEXT,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.SECTION_HEADER,
                        section_header=GoogleFormsSectionHeader(
                            title="Event Details",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Which sessions are you interested in?",
                            description="Select all sessions you plan to attend",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.CHECKBOX,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Opening Keynote",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Technical Workshop A",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Technical Workshop B",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Panel Discussion",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Networking Lunch",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Closing Ceremony",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Dietary Restrictions",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.DROPDOWN,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="None",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Vegetarian",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Vegan",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Gluten-Free",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Other (specify in comments)",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Preferred Conference Date",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.DATE,
                            include_year=True,
                        ),
                    ),
                ],
            ),
            GoogleFormsForm(
                title="Employee Performance Review",
                description="Quarterly performance evaluation form for team members",
                is_quiz=False,
                items=[
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.SECTION_HEADER,
                        section_header=GoogleFormsSectionHeader(
                            title="Employee Information",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Employee Name",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SHORT_TEXT,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Department",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.DROPDOWN,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Engineering",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Product",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Design",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Marketing",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Sales",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Human Resources",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Finance",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Operations",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Review Period",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.MULTIPLE_CHOICE,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Q1 2025",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Q2 2025",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Q3 2025",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Q4 2025",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.SECTION_HEADER,
                        section_header=GoogleFormsSectionHeader(
                            title="Performance Metrics",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Quality of Work",
                            description="Rate the quality and accuracy of work produced",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SCALE,
                            scale_low=1,
                            scale_high=5,
                            scale_low_label="Needs Improvement",
                            scale_high_label="Exceptional",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Productivity",
                            description="Rate the quantity of work and ability to meet deadlines",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SCALE,
                            scale_low=1,
                            scale_high=5,
                            scale_low_label="Needs Improvement",
                            scale_high_label="Exceptional",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Communication",
                            description="Rate effectiveness in verbal and written communication",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SCALE,
                            scale_low=1,
                            scale_high=5,
                            scale_low_label="Needs Improvement",
                            scale_high_label="Exceptional",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Teamwork",
                            description="Rate collaboration and contribution to team success",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SCALE,
                            scale_low=1,
                            scale_high=5,
                            scale_low_label="Needs Improvement",
                            scale_high_label="Exceptional",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Key Achievements",
                            description="List major accomplishments during this review period",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.PARAGRAPH,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Areas for Improvement",
                            description="Identify areas where the employee could grow",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.PARAGRAPH,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Goals for Next Quarter",
                            description="Set objectives for the upcoming review period",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.PARAGRAPH,
                        ),
                    ),
                ],
            ),
            GoogleFormsForm(
                title="Product Feedback Form",
                description="Help us improve our product by sharing your experience",
                is_quiz=False,
                items=[
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Product Version",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.DROPDOWN,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="v1.0",
                                ),
                                GoogleFormsChoiceOption(
                                    value="v2.0",
                                ),
                                GoogleFormsChoiceOption(
                                    value="v3.0 (Latest)",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Beta",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="How long have you been using our product?",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.MULTIPLE_CHOICE,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Less than 1 month",
                                ),
                                GoogleFormsChoiceOption(
                                    value="1-6 months",
                                ),
                                GoogleFormsChoiceOption(
                                    value="6-12 months",
                                ),
                                GoogleFormsChoiceOption(
                                    value="More than 1 year",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="How likely are you to recommend our product?",
                            description="Net Promoter Score",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SCALE,
                            scale_low=1,
                            scale_high=10,
                            scale_low_label="Not at all likely",
                            scale_high_label="Extremely likely",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="What do you like most about our product?",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.PARAGRAPH,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="What features would you like to see added?",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.PARAGRAPH,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Would you be interested in participating in user research?",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.MULTIPLE_CHOICE,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Yes, contact me",
                                ),
                                GoogleFormsChoiceOption(
                                    value="No, thank you",
                                ),
                            ],
                        ),
                    ),
                ],
            ),
            GoogleFormsForm(
                title="Job Application Form",
                description="Apply for open positions at our company",
                is_quiz=False,
                items=[
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.SECTION_HEADER,
                        section_header=GoogleFormsSectionHeader(
                            title="Contact Information",
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Full Name",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SHORT_TEXT,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Email",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SHORT_TEXT,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Phone Number",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.SHORT_TEXT,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Position Applied For",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.DROPDOWN,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Software Engineer",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Product Manager",
                                ),
                                GoogleFormsChoiceOption(
                                    value="UX Designer",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Data Scientist",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Marketing Specialist",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Sales Representative",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Customer Support",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Experience Level",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.MULTIPLE_CHOICE,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Entry Level (0-2 years)",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Mid Level (2-5 years)",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Senior Level (5-10 years)",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Executive (10+ years)",
                                ),
                            ],
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Earliest Start Date",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.DATE,
                            include_year=True,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="Cover Letter",
                            description="Tell us why you're interested in this position and what makes you a great fit",
                            required=True,
                            question_type=GoogleFormsQuestionQuestionType.PARAGRAPH,
                        ),
                    ),
                    GoogleFormsItem(
                        item_type=GoogleFormsItemOutputItemType.QUESTION,
                        question=GoogleFormsQuestion(
                            title="How did you find this job posting?",
                            required=False,
                            question_type=GoogleFormsQuestionQuestionType.CHECKBOX,
                            options=[
                                GoogleFormsChoiceOption(
                                    value="Company Website",
                                ),
                                GoogleFormsChoiceOption(
                                    value="LinkedIn",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Indeed",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Glassdoor",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Employee Referral",
                                ),
                                GoogleFormsChoiceOption(
                                    value="Other",
                                ),
                            ],
                        ),
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GoogleFormsDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_google_forms_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_google_forms_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_google_sheets_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with google_sheets-specific data following the defined schema.
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
from klavis import (
    GoogleSheetsCell,
    GoogleSheetsDataInput,
    GoogleSheetsSheet,
    GoogleSheetsSpreadsheet,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_google_sheets_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GoogleSheetsDataInput(
        spreadsheets=[
            GoogleSheetsSpreadsheet(
                title="Sales Data 2025",
                sheets=[
                    GoogleSheetsSheet(
                        title="Q1 Sales",
                        index=0,
                        row_count=100,
                        column_count=10,
                        cells=[
                            GoogleSheetsCell(
                                row=0,
                                col=0,
                                value="Date",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=1,
                                value="Product",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=2,
                                value="Quantity",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=3,
                                value="Revenue",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=4,
                                value="Region",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=0,
                                value="2025-01-15",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=1,
                                value="Widget A",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=2,
                                value=100,
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=3,
                                value=5000,
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=4,
                                value="North America",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=0,
                                value="2025-02-20",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=1,
                                value="Widget B",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=2,
                                value=150,
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=3,
                                value=7500,
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=4,
                                value="Europe",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=0,
                                value="2025-03-10",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=1,
                                value="Widget A",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=2,
                                value=200,
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=3,
                                value=10000,
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=4,
                                value="Asia Pacific",
                            ),
                        ],
                    )
                ],
            ),
            GoogleSheetsSpreadsheet(
                title="Customer Database",
                sheets=[
                    GoogleSheetsSheet(
                        title="Customers",
                        index=0,
                        row_count=100,
                        column_count=8,
                        cells=[
                            GoogleSheetsCell(
                                row=0,
                                col=0,
                                value="ID",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=1,
                                value="Company Name",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=2,
                                value="Contact Email",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=3,
                                value="Status",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=4,
                                value="Account Value",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=0,
                                value=1,
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=1,
                                value="Acme Corporation",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=2,
                                value="contact@acme.com",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=3,
                                value="Active",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=4,
                                value=50000,
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=0,
                                value=2,
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=1,
                                value="TechStart Inc",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=2,
                                value="info@techstart.com",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=3,
                                value="Active",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=4,
                                value=75000,
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=0,
                                value=3,
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=1,
                                value="Global Industries",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=2,
                                value="sales@global.com",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=3,
                                value="Pending",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=4,
                                value=120000,
                            ),
                        ],
                    )
                ],
            ),
            GoogleSheetsSpreadsheet(
                title="Project Tracker",
                sheets=[
                    GoogleSheetsSheet(
                        title="Projects",
                        index=0,
                        row_count=50,
                        column_count=6,
                        cells=[
                            GoogleSheetsCell(
                                row=0,
                                col=0,
                                value="Project Name",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=1,
                                value="Status",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=2,
                                value="Owner",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=3,
                                value="Deadline",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=4,
                                value="Progress",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=0,
                                value="Website Redesign",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=1,
                                value="In Progress",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=2,
                                value="John Doe",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=3,
                                value="2025-04-30",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=4,
                                value=0.65,
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=0,
                                value="Mobile App Development",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=1,
                                value="Planning",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=2,
                                value="Jane Smith",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=3,
                                value="2025-06-15",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=4,
                                value=0.15,
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=0,
                                value="API Integration",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=1,
                                value="Completed",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=2,
                                value="Bob Johnson",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=3,
                                value="2025-01-31",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=4,
                                value=1,
                            ),
                        ],
                    ),
                    GoogleSheetsSheet(
                        title="Budget",
                        index=1,
                        row_count=50,
                        column_count=5,
                        cells=[
                            GoogleSheetsCell(
                                row=0,
                                col=0,
                                value="Category",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=1,
                                value="Allocated",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=2,
                                value="Spent",
                            ),
                            GoogleSheetsCell(
                                row=0,
                                col=3,
                                value="Remaining",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=0,
                                value="Development",
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=1,
                                value=100000,
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=2,
                                value=65000,
                            ),
                            GoogleSheetsCell(
                                row=1,
                                col=3,
                                formula="=B2-C2",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=0,
                                value="Design",
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=1,
                                value=30000,
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=2,
                                value=22000,
                            ),
                            GoogleSheetsCell(
                                row=2,
                                col=3,
                                formula="=B3-C3",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=0,
                                value="Marketing",
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=1,
                                value=50000,
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=2,
                                value=38000,
                            ),
                            GoogleSheetsCell(
                                row=3,
                                col=3,
                                formula="=B4-C4",
                            ),
                        ],
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GoogleSheetsDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_google_sheets_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_google_sheets_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_salesforce_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with salesforce-specific data following the defined schema.
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
from klavis import (
    Account,
    Address,
    Campaign,
    Case,
    Contact,
    Klavis,
    Lead,
    Opportunity,
    SalesforceDataInput,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_salesforce_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=SalesforceDataInput(
        accounts=[
            Account(
                name="Acme Corporation",
                industry="Technology",
                type="Customer",
                phone="+1-555-0100",
                website="https://www.acmecorp.com",
                revenue=5000000.0,
                employees=250,
                address=Address(
                    street="123 Tech Street",
                    city="San Francisco",
                    state="California",
                    postal_code="94105",
                    country="United States",
                ),
                description="Leading technology solutions provider",
                rating="Hot",
            ),
            Account(
                name="Global Enterprises Inc",
                industry="Finance",
                type="Prospect",
                phone="+1-555-0200",
                website="https://www.globalenterprises.com",
                revenue=15000000.0,
                employees=500,
                address=Address(
                    street="456 Finance Ave",
                    city="New York",
                    state="New York",
                    postal_code="10001",
                    country="United States",
                ),
                description="International financial services company",
                rating="Warm",
            ),
            Account(
                name="Tech Solutions Ltd",
                industry="Technology",
                type="Partner",
                phone="+1-555-0300",
                website="https://www.techsolutions.com",
                revenue=3000000.0,
                employees=150,
                address=Address(
                    street="789 Innovation Blvd",
                    city="Austin",
                    state="Texas",
                    postal_code="78701",
                    country="United States",
                ),
                description="Custom software development partner",
                rating="Hot",
            ),
        ],
        contacts=[
            Contact(
                first_name="John",
                last_name="Doe",
                email="john.doe@acmecorp.com",
                phone="+1-555-0101",
                mobile="+1-555-0102",
                title="VP of Technology",
                department="IT",
                address=Address(
                    street="123 Tech Street",
                    city="San Francisco",
                    state="California",
                    postal_code="94105",
                    country="United States",
                ),
                description="Key decision maker for technology purchases",
                source="Web",
            ),
            Contact(
                first_name="Jane",
                last_name="Smith",
                email="jane.smith@globalenterprises.com",
                phone="+1-555-0201",
                mobile="+1-555-0202",
                title="Chief Financial Officer",
                department="Finance",
                address=Address(
                    street="456 Finance Ave",
                    city="New York",
                    state="New York",
                    postal_code="10001",
                    country="United States",
                ),
                description="Budget approver and executive sponsor",
                source="Phone Inquiry",
            ),
            Contact(
                first_name="Bob",
                last_name="Johnson",
                email="bob.johnson@techsolutions.com",
                phone="+1-555-0301",
                mobile="+1-555-0302",
                title="Director of Operations",
                department="Operations",
                address=Address(
                    street="789 Innovation Blvd",
                    city="Austin",
                    state="Texas",
                    postal_code="78701",
                    country="United States",
                ),
                description="Partnership coordinator and technical lead",
                source="Partner Referral",
            ),
            Contact(
                first_name="Alice",
                last_name="Williams",
                email="alice.williams@acmecorp.com",
                phone="+1-555-0103",
                title="Product Manager",
                department="Product",
                source="Web",
            ),
            Contact(
                first_name="Charlie",
                last_name="Brown",
                email="charlie.brown@globalenterprises.com",
                phone="+1-555-0203",
                title="IT Manager",
                department="IT",
                source="Trade Show",
            ),
        ],
        opportunities=[
            Opportunity(
                name="Acme Corp - Q4 Enterprise Deal",
                stage="Qualification",
                close_date="2025-12-31",
                amount=250000.0,
                probability=75,
                type="New Business",
                source="Web",
                next_step="Schedule executive demo",
                description="Large enterprise deal for full platform implementation",
            ),
            Opportunity(
                name="Global Enterprises - Annual Subscription",
                stage="Proposal/Price Quote",
                close_date="2026-02-28",
                amount=500000.0,
                probability=50,
                type="New Business",
                source="Phone Inquiry",
                next_step="Present pricing proposal to CFO",
                description="Multi-year subscription for financial services platform",
            ),
            Opportunity(
                name="Tech Solutions - Partnership Expansion",
                stage="Negotiation/Review",
                close_date="2025-12-07",
                amount=150000.0,
                probability=80,
                type="Existing Business",
                source="Partner Referral",
                next_step="Finalize contract terms",
                description="Expanding existing partnership agreement",
            ),
            Opportunity(
                name="Acme Corp - Additional Licenses",
                stage="Prospecting",
                close_date="2026-02-28",
                amount=75000.0,
                probability=60,
                type="Existing Business",
                source="Web",
                next_step="Identify additional use cases",
                description="Upsell opportunity for additional user licenses",
            ),
        ],
        leads=[
            Lead(
                first_name="David",
                last_name="Martinez",
                company="Startup Innovations Inc",
                email="david.martinez@startupinnovations.com",
                phone="+1-555-0400",
                mobile="+1-555-0401",
                title="Founder & CEO",
                status="Open - Not Contacted",
                source="Web",
                industry="Technology",
                rating="Hot",
                address=Address(
                    street="321 Startup Lane",
                    city="Seattle",
                    state="Washington",
                    postal_code="98101",
                    country="United States",
                ),
                website="https://www.startupinnovations.com",
                description="Fast-growing startup looking for enterprise solutions",
                employees=25,
                revenue=500000.0,
            ),
            Lead(
                first_name="Emma",
                last_name="Garcia",
                company="Healthcare Systems LLC",
                email="emma.garcia@healthcaresystems.com",
                phone="+1-555-0500",
                title="Director of IT",
                status="Working - Contacted",
                source="Phone Inquiry",
                industry="Healthcare",
                rating="Warm",
                address=Address(
                    city="Boston",
                    state="Massachusetts",
                    country="United States",
                ),
                description="Exploring new healthcare IT solutions",
                employees=300,
            ),
            Lead(
                first_name="Frank",
                last_name="Wilson",
                company="Manufacturing Corp",
                email="frank.wilson@manufacturingcorp.com",
                phone="+1-555-0600",
                title="Operations Manager",
                status="Open - Not Contacted",
                source="Partner Referral",
                industry="Manufacturing",
                rating="Warm",
                address=Address(
                    city="Detroit",
                    state="Michigan",
                    country="United States",
                ),
                description="Interested in automation solutions",
            ),
        ],
        cases=[
            Case(
                subject="Login Issues - Urgent",
                status="New",
                priority="High",
                origin="Phone",
                type="Problem",
                description="Customer reporting intermittent login failures affecting multiple users",
                customer_email="support@acmecorp.com",
                customer_name="John Doe",
                customer_phone="+1-555-0101",
            ),
            Case(
                subject="Feature Request - Custom Reporting",
                status="Working",
                priority="Medium",
                origin="Email",
                type="Feature Request",
                reason="Enhancement",
                description="Customer requesting custom reporting capabilities for executive dashboard",
            ),
            Case(
                subject="API Integration Question",
                status="New",
                priority="Low",
                origin="Web",
                type="Question",
                description="Developer needs clarification on API authentication flow",
                customer_email="developer@techsolutions.com",
            ),
            Case(
                subject="Performance Degradation",
                status="Escalated",
                priority="High",
                origin="Phone",
                type="Problem",
                description="System response times have increased significantly during peak hours",
            ),
            Case(
                subject="Training Request",
                status="New",
                priority="Medium",
                origin="Email",
                type="Question",
                description="New admin team needs comprehensive platform training",
            ),
        ],
        campaigns=[
            Campaign(
                name="Q4 2024 Product Launch",
                type="Email",
                status="In Progress",
                start_date="2024-10-01",
                end_date="2024-12-31",
                expected_revenue=1000000.0,
                budget=50000.0,
                actual_cost=25000.0,
                description="Major product launch campaign targeting enterprise customers",
                active=True,
            ),
            Campaign(
                name="Partner Webinar Series",
                type="Webinar",
                status="Planned",
                start_date="2025-01-15",
                end_date="2025-03-31",
                expected_revenue=250000.0,
                budget=15000.0,
                description="Educational webinar series for partner network",
                active=False,
            ),
            Campaign(
                name="Industry Conference 2024",
                type="Conference",
                status="Completed",
                start_date="2024-09-15",
                end_date="2024-09-17",
                expected_revenue=500000.0,
                budget=75000.0,
                actual_cost=80000.0,
                description="Annual industry conference with booth and speaking sessions",
                active=False,
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[SalesforceDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_salesforce_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_salesforce_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_onedrive_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with onedrive-specific data following the defined schema.
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
from klavis import Klavis, OneDriveDataInput, OneDriveFile, OneDriveFolder

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_onedrive_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=OneDriveDataInput(
        root=[
            OneDriveFolder(
                name="root",
                files=[
                    OneDriveFile(
                        name="welcome.txt",
                        content="Welcome to your OneDrive!\nThis is your personal cloud storage space.",
                    )
                ],
            )
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[OneDriveDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_onedrive_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_onedrive_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_microsoft_teams_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with microsoft_teams-specific data following the defined schema.
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
from klavis import (
    Klavis,
    MsTeamsDataInput,
    TeamsChannel,
    TeamsChat,
    TeamsMessage,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_microsoft_teams_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=MsTeamsDataInput(
        team_channels=[
            TeamsChannel(
                name="Engineering",
                channel_description="Channel for engineering team discussions",
                channel_messages=[
                    TeamsMessage(
                        content="Welcome to the Engineering channel! This is where we discuss technical topics and share updates.",
                    ),
                    TeamsMessage(
                        content="Reminder: Code review sessions every Tuesday at 10 AM",
                    ),
                    TeamsMessage(
                        content="New deployment pipeline is ready for testing. Please check the documentation in our wiki.",
                    ),
                ],
            ),
            TeamsChannel(
                name="Marketing",
                channel_description="Channel for marketing campaigns and strategies",
                channel_messages=[
                    TeamsMessage(
                        content="Q4 campaign planning meeting scheduled for next week",
                    ),
                    TeamsMessage(
                        content="Great job on the recent product launch! The social media engagement exceeded our targets by 40%",
                    ),
                ],
            ),
            TeamsChannel(
                name="Project Alpha",
                channel_description="Dedicated channel for Project Alpha collaboration",
                channel_messages=[
                    TeamsMessage(
                        content="Project kickoff meeting notes: https://docs.example.com/project-alpha/kickoff",
                    ),
                    TeamsMessage(
                        content="Phase 1 milestone completed! Moving to Phase 2 next sprint.",
                    ),
                    TeamsMessage(
                        content="Updated timeline shared in the files tab. Please review and provide feedback by EOW.",
                    ),
                ],
            ),
        ],
        team_chats=[TeamsChat()],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[MsTeamsDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_microsoft_teams_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_microsoft_teams_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_outlook_mail_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with outlook_mail-specific data following the defined schema.
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
from klavis import Klavis, OutlookMailData, OutlookMailMessage

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_outlook_mail_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=OutlookMailData(
        messages=[
            OutlookMailMessage(
                title="Welcome to the Team!",
                content={
                    "contentType": "HTML",
                    "content": "<p>Hi there!</p><p>Welcome to our team. We're excited to have you on board. Please feel free to reach out if you have any questions.</p><p>Best regards,<br>HR Team</p>",
                },
                to_addresses=["newemployee@company.com"],
                cc_addresses=["hr@company.com", "manager@company.com"],
            ),
            OutlookMailMessage(
                title="Q4 Budget Review Meeting",
                content={
                    "contentType": "Text",
                    "content": "Hi,\n\nThis is a reminder about our Q4 budget review meeting scheduled for next Tuesday at 2 PM. Please come prepared with your department's spending reports.\n\nThanks,\nFinance Team",
                },
                to_addresses=["team@company.com"],
                cc_addresses=["cfo@company.com"],
            ),
            OutlookMailMessage(
                title="Project Alpha - Status Update",
                content={
                    "contentType": "HTML",
                    "content": "<h3>Project Alpha Status Report</h3><p>Current Status: <strong>On Track</strong></p><ul><li>Phase 1: Completed</li><li>Phase 2: 75% complete</li><li>Phase 3: Planning</li></ul><p>Next milestone: December 15th</p>",
                },
                to_addresses=[
                    "projectteam@company.com",
                    "stakeholders@company.com",
                ],
                cc_addresses=["cc_addresses"],
            ),
            OutlookMailMessage(
                title="Action Required: Security Policy Update",
                content={
                    "contentType": "Text",
                    "content": "IMPORTANT: Please review and acknowledge the updated security policy by end of week.\n\nKey changes:\n- Password complexity requirements\n- 2FA mandatory for all accounts\n- VPN usage guidelines\n\nClick the link in your security portal to acknowledge.\n\nIT Security Team",
                },
                to_addresses=["allstaff@company.com"],
                cc_addresses=["compliance@company.com", "legal@company.com"],
            ),
            OutlookMailMessage(
                title="Team Lunch - Friday 12:30 PM",
                content={
                    "contentType": "HTML",
                    "content": "<p>Hey team! </p><p>Let's grab lunch together this Friday at 12:30 PM. I've made a reservation at the Italian place downtown.</p><p>Please RSVP by Wednesday so I can confirm the headcount.</p><p>Looking forward to it!<br>Sarah</p>",
                },
                to_addresses=["dev-team@company.com"],
                cc_addresses=["sarah.manager@company.com"],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[OutlookMailData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_outlook_mail_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_outlook_mail_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with localmemory-specific data following the defined schema.
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
from klavis import (
    Klavis,
    LocalMemoryData,
    LocalMemoryEntity,
    LocalMemoryRelation,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=LocalMemoryData(
        entities=[
            LocalMemoryEntity(
                name="Alice",
                entity_type="person",
                observations=[
                    "Software engineer at TechCorp",
                    "Specializes in Python and machine learning",
                    "Team lead for the AI project",
                ],
            ),
            LocalMemoryEntity(
                name="Bob",
                entity_type="person",
                observations=[
                    "Frontend developer at TechCorp",
                    "Expert in React and TypeScript",
                    "Works on the dashboard team",
                ],
            ),
            LocalMemoryEntity(
                name="Carol",
                entity_type="person",
                observations=[
                    "Product manager at TechCorp",
                    "Manages the AI and Dashboard projects",
                    "Previously worked at StartupXYZ",
                ],
            ),
            LocalMemoryEntity(
                name="TechCorp",
                entity_type="organization",
                observations=[
                    "Technology company founded in 2015",
                    "Headquarters in San Francisco",
                    "Specializes in AI-powered business solutions",
                ],
            ),
            LocalMemoryEntity(
                name="AI Project",
                entity_type="project",
                observations=[
                    "Machine learning recommendation system",
                    "Started in Q1 2024",
                    "Uses TensorFlow and Python",
                ],
            ),
            LocalMemoryEntity(
                name="Dashboard Project",
                entity_type="project",
                observations=[
                    "Analytics dashboard for enterprise clients",
                    "Built with React and Node.js",
                    "Launched in 2023",
                ],
            ),
            LocalMemoryEntity(
                name="Python",
                entity_type="technology",
                observations=[
                    "Programming language",
                    "Used for backend and ML development",
                ],
            ),
            LocalMemoryEntity(
                name="React",
                entity_type="technology",
                observations=[
                    "JavaScript library for building UIs",
                    "Maintained by Meta",
                ],
            ),
        ],
        relations=[
            LocalMemoryRelation(
                from_="Alice",
                to="TechCorp",
                relation_type="works_at",
            ),
            LocalMemoryRelation(
                from_="Bob",
                to="TechCorp",
                relation_type="works_at",
            ),
            LocalMemoryRelation(
                from_="Carol",
                to="TechCorp",
                relation_type="works_at",
            ),
            LocalMemoryRelation(
                from_="Alice",
                to="AI Project",
                relation_type="leads",
            ),
            LocalMemoryRelation(
                from_="Alice",
                to="Bob",
                relation_type="collaborates_with",
            ),
            LocalMemoryRelation(
                from_="Carol",
                to="AI Project",
                relation_type="manages",
            ),
            LocalMemoryRelation(
                from_="Carol",
                to="Dashboard Project",
                relation_type="manages",
            ),
            LocalMemoryRelation(
                from_="Bob",
                to="Dashboard Project",
                relation_type="contributes_to",
            ),
            LocalMemoryRelation(
                from_="AI Project",
                to="Python",
                relation_type="uses",
            ),
            LocalMemoryRelation(
                from_="Dashboard Project",
                to="React",
                relation_type="uses",
            ),
            LocalMemoryRelation(
                from_="Alice",
                to="Python",
                relation_type="skilled_in",
            ),
            LocalMemoryRelation(
                from_="Bob",
                to="React",
                relation_type="skilled_in",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[LocalMemoryData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_hubspot_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with hubspot-specific data following the defined schema.
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
from klavis import (
    HubSpotCompany,
    HubSpotContact,
    HubSpotDataInput,
    HubSpotDeal,
    HubSpotTask,
    HubSpotTicket,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_hubspot_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=HubSpotDataInput(
        companies=[
            HubSpotCompany(
                company_name="TechCorp Solutions",
                website_domain="techcorp.com",
                industry="COMPUTER_SOFTWARE",
                city="San Francisco",
                state_region="CA",
                country="United States",
                phone_number="+1-415-555-0101",
                employee_count="250",
                yearly_revenue="15000000",
            ),
            HubSpotCompany(
                company_name="DataFlow Analytics",
                website_domain="dataflow-analytics.com",
                industry="INFORMATION_TECHNOLOGY_AND_SERVICES",
                city="Austin",
                state_region="TX",
                country="United States",
                phone_number="+1-512-555-0201",
                employee_count="75",
                yearly_revenue="5000000",
            ),
            HubSpotCompany(
                company_name="CloudScale Inc",
                website_domain="cloudscale.io",
                industry="INTERNET",
                city="Seattle",
                state_region="WA",
                country="United States",
                phone_number="+1-206-555-0301",
                employee_count="500",
                yearly_revenue="45000000",
            ),
        ],
        contacts=[
            HubSpotContact(
                first_name="John",
                last_name="Smith",
                email_address="john.smith@techcorp.com",
                phone_number="+1-415-555-0102",
                job_title="CTO",
            ),
            HubSpotContact(
                first_name="Sarah",
                last_name="Johnson",
                email_address="sarah.johnson@techcorp.com",
                phone_number="+1-415-555-0103",
                job_title="VP of Engineering",
            ),
            HubSpotContact(
                first_name="Michael",
                last_name="Chen",
                email_address="michael.chen@techcorp.com",
                phone_number="+1-415-555-0104",
                job_title="Product Manager",
            ),
            HubSpotContact(
                first_name="Emily",
                last_name="Rodriguez",
                email_address="emily@dataflow-analytics.com",
                phone_number="+1-512-555-0202",
                job_title="CEO",
            ),
            HubSpotContact(
                first_name="David",
                last_name="Kim",
                email_address="david@dataflow-analytics.com",
                phone_number="+1-512-555-0203",
                job_title="Data Architect",
            ),
            HubSpotContact(
                first_name="Jennifer",
                last_name="Williams",
                email_address="jennifer@cloudscale.io",
                phone_number="+1-206-555-0302",
                job_title="Head of Operations",
            ),
            HubSpotContact(
                first_name="Alex",
                last_name="Thompson",
                email_address="alex.thompson@freelancer.com",
                phone_number="+1-555-0401",
                job_title="Independent Consultant",
            ),
            HubSpotContact(
                first_name="Maria",
                last_name="Garcia",
                email_address="maria.garcia@startup.com",
                phone_number="+1-555-0402",
                job_title="Founder",
            ),
        ],
        deals=[
            HubSpotDeal(
                title="Enterprise License Agreement",
                value="150000",
                stage="contractsent",
                pipeline="default",
                expected_close_date="2024-03-15T00:00:00Z",
            ),
            HubSpotDeal(
                title="Professional Services Package",
                value="50000",
                stage="qualifiedtobuy",
                pipeline="default",
                expected_close_date="2024-04-01T00:00:00Z",
            ),
            HubSpotDeal(
                title="Annual Platform Subscription",
                value="200000",
                stage="decisionmakerboughtin",
                pipeline="default",
                expected_close_date="2024-02-28T00:00:00Z",
            ),
            HubSpotDeal(
                title="Starter Package",
                value="25000",
                stage="presentationscheduled",
                pipeline="default",
                expected_close_date="2024-03-30T00:00:00Z",
            ),
            HubSpotDeal(
                title="Multi-year Enterprise Deal",
                value="500000",
                stage="appointmentscheduled",
                pipeline="default",
                expected_close_date="2024-05-15T00:00:00Z",
            ),
            HubSpotDeal(
                title="Consulting Engagement",
                value="75000",
                stage="qualifiedtobuy",
                pipeline="default",
                expected_close_date="2024-03-20T00:00:00Z",
            ),
            HubSpotDeal(
                title="Individual License",
                value="5000",
                stage="qualifiedtobuy",
                pipeline="default",
                expected_close_date="2024-02-28T00:00:00Z",
            ),
            HubSpotDeal(
                title="Partnership Opportunity",
                value="100000",
                stage="qualifiedtobuy",
                pipeline="default",
                expected_close_date="2024-04-30T00:00:00Z",
            ),
        ],
        tickets=[
            HubSpotTicket(
                title="API integration question",
                description="Need clarification on webhook authentication",
                pipeline="0",
                workflow_stage="1",
                priority_level="MEDIUM",
            ),
            HubSpotTicket(
                title="Feature request: SSO integration",
                description="Request for SAML-based single sign-on capability",
                pipeline="0",
                workflow_stage="1",
                priority_level="HIGH",
            ),
            HubSpotTicket(
                title="Data export format question",
                description="Need to understand available export formats and scheduling options",
                pipeline="0",
                workflow_stage="1",
                priority_level="LOW",
            ),
            HubSpotTicket(
                title="Billing question",
                description="Question about payment options and invoicing",
                pipeline="0",
                workflow_stage="1",
                priority_level="LOW",
            ),
            HubSpotTicket(
                title="Startup program inquiry",
                description="Interested in joining startup accelerator program",
                pipeline="0",
                workflow_stage="1",
                priority_level="MEDIUM",
            ),
            HubSpotTicket(
                title="General inquiry from website",
                description="Visitor submitted question through contact form",
                pipeline="0",
                workflow_stage="1",
                priority_level="LOW",
            ),
        ],
        tasks=[
            HubSpotTask(
                title="Follow up on contract review",
                description="Check if legal team has finished reviewing the contract",
                task_status="IN_PROGRESS",
                priority_level="HIGH",
                deadline="2024-02-20T17:00:00Z",
            ),
            HubSpotTask(
                title="Schedule implementation call",
                description="Set up kick-off meeting with implementation team",
                task_status="NOT_STARTED",
                priority_level="MEDIUM",
                deadline="2024-03-01T10:00:00Z",
            ),
            HubSpotTask(
                title="Prepare custom proposal",
                description="Create tailored services proposal based on discovery call",
                task_status="IN_PROGRESS",
                priority_level="HIGH",
                deadline="2024-02-18T17:00:00Z",
            ),
            HubSpotTask(
                title="Research webhook authentication options",
                description="Document different authentication methods available",
                task_status="COMPLETED",
                priority_level="MEDIUM",
                deadline="2024-02-15T12:00:00Z",
            ),
            HubSpotTask(
                title="Send quarterly business review invitation",
                description="Schedule QBR meeting for Q1 2024",
                task_status="NOT_STARTED",
                priority_level="MEDIUM",
                deadline="2024-03-01T09:00:00Z",
            ),
            HubSpotTask(
                title="Evaluate SSO requirements",
                description="Gather detailed requirements from customer",
                task_status="IN_PROGRESS",
                priority_level="HIGH",
                deadline="2024-02-22T17:00:00Z",
            ),
            HubSpotTask(
                title="Create SSO implementation estimate",
                task_status="NOT_STARTED",
                priority_level="MEDIUM",
                deadline="2024-02-25T17:00:00Z",
            ),
            HubSpotTask(
                title="Schedule product demo",
                description="Demo new features to TechCorp team",
                task_status="NOT_STARTED",
                priority_level="HIGH",
                deadline="2024-02-28T14:00:00Z",
            ),
            HubSpotTask(
                title="Prepare pricing options",
                description="Create tiered pricing proposal with volume discounts",
                task_status="COMPLETED",
                priority_level="HIGH",
                deadline="2024-02-10T17:00:00Z",
            ),
            HubSpotTask(
                title="Coordinate with finance team",
                description="Ensure invoicing and payment terms are set up",
                task_status="IN_PROGRESS",
                priority_level="MEDIUM",
                deadline="2024-02-25T12:00:00Z",
            ),
            HubSpotTask(
                title="Prepare demo presentation",
                description="Customize demo to show analytics-specific features",
                task_status="IN_PROGRESS",
                priority_level="HIGH",
                deadline="2024-02-19T15:00:00Z",
            ),
            HubSpotTask(
                title="Send case study documents",
                description="Share relevant customer success stories",
                task_status="NOT_STARTED",
                priority_level="MEDIUM",
                deadline="2024-02-20T10:00:00Z",
            ),
            HubSpotTask(
                title="Schedule C-level meeting",
                description="Arrange meeting with CEO and CFO",
                task_status="IN_PROGRESS",
                priority_level="HIGH",
                deadline="2024-02-21T16:00:00Z",
            ),
            HubSpotTask(
                title="Prepare ROI analysis",
                description="Build comprehensive ROI model for 3-year contract",
                task_status="NOT_STARTED",
                priority_level="HIGH",
                deadline="2024-02-27T17:00:00Z",
            ),
            HubSpotTask(
                title="Draft statement of work",
                description="Create detailed SOW for consulting services",
                task_status="IN_PROGRESS",
                priority_level="HIGH",
                deadline="2024-02-23T17:00:00Z",
            ),
            HubSpotTask(
                title="Send license agreement",
                task_status="NOT_STARTED",
                priority_level="MEDIUM",
                deadline="2024-02-17T12:00:00Z",
            ),
            HubSpotTask(
                title="Review startup program eligibility",
                description="Check if company meets program criteria",
                task_status="IN_PROGRESS",
                priority_level="MEDIUM",
                deadline="2024-02-19T17:00:00Z",
            ),
            HubSpotTask(
                title="Send startup program information",
                description="Share details about benefits and application process",
                task_status="NOT_STARTED",
                priority_level="HIGH",
                deadline="2024-02-20T11:00:00Z",
            ),
            HubSpotTask(
                title="Research potential partner",
                description="Gather information about partnership fit and objectives",
                task_status="IN_PROGRESS",
                priority_level="MEDIUM",
                deadline="2024-02-25T17:00:00Z",
            ),
            HubSpotTask(
                title="Respond to inquiry",
                description="Provide initial response and gather more details",
                task_status="NOT_STARTED",
                priority_level="LOW",
                deadline="2024-02-18T17:00:00Z",
            ),
            HubSpotTask(
                title="Weekly team standup",
                description="Regular sync meeting with sales team",
                task_status="NOT_STARTED",
                priority_level="MEDIUM",
                deadline="2024-02-19T10:00:00Z",
            ),
            HubSpotTask(
                title="Update CRM data quality",
                description="Review and clean up duplicate records",
                task_status="IN_PROGRESS",
                priority_level="LOW",
                deadline="2024-02-29T17:00:00Z",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[HubSpotDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_hubspot_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_hubspot_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_quickbooks_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with quickbooks-specific data following the defined schema.
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
from klavis import Klavis, QuickBooksData

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_quickbooks_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=QuickBooksData(
        accounts=[
            {"Name": "Business Checking Account", "AccountType": "Bank"},
            {"Name": "Savings Account", "AccountType": "Bank"},
            {
                "Name": "Accounts Receivable",
                "AccountType": "Accounts Receivable",
            },
            {"Name": "Sales Revenue", "AccountType": "Income"},
            {"Name": "Consulting Revenue", "AccountType": "Income"},
            {"Name": "Product Sales", "AccountType": "Income"},
            {"Name": "Office Expenses", "AccountType": "Expense"},
            {"Name": "Rent Expense", "AccountType": "Expense"},
            {"Name": "Utilities Expense", "AccountType": "Expense"},
            {"Name": "Marketing Expense", "AccountType": "Expense"},
            {"Name": "Travel Expense", "AccountType": "Expense"},
            {"Name": "Insurance Expense", "AccountType": "Expense"},
            {"Name": "Equipment", "AccountType": "Other Current Asset"},
            {"Name": "Accounts Payable", "AccountType": "Accounts Payable"},
            {
                "Name": "Sales Tax Payable",
                "AccountType": "Other Current Liability",
            },
        ],
        customers=[
            {
                "DisplayName": "Acme Corporation",
                "CompanyName": "Acme Corporation",
                "PrimaryEmailAddr": {"Address": "billing@acme.com"},
                "BillAddr": {
                    "Line1": "123 Business Street",
                    "City": "San Francisco",
                    "CountrySubDivisionCode": "CA",
                    "PostalCode": "94105",
                },
            },
            {
                "DisplayName": "Tech Start Inc",
                "CompanyName": "Tech Start Inc",
                "PrimaryEmailAddr": {"Address": "accounts@techstart.io"},
                "BillAddr": {
                    "Line1": "456 Innovation Drive",
                    "City": "Palo Alto",
                    "CountrySubDivisionCode": "CA",
                    "PostalCode": "94301",
                },
            },
            {
                "DisplayName": "Global Enterprises LLC",
                "CompanyName": "Global Enterprises LLC",
                "PrimaryEmailAddr": {"Address": "finance@globalent.com"},
                "BillAddr": {
                    "Line1": "789 Commerce Ave",
                    "City": "New York",
                    "CountrySubDivisionCode": "NY",
                    "PostalCode": "10001",
                },
            },
            {
                "DisplayName": "Blue Sky Solutions",
                "CompanyName": "Blue Sky Solutions",
                "PrimaryEmailAddr": {"Address": "billing@bluesky.com"},
            },
            {
                "DisplayName": "Metro Systems Corp",
                "CompanyName": "Metro Systems Corp",
                "PrimaryEmailAddr": {"Address": "ap@metrosystems.com"},
            },
            {
                "DisplayName": "Sunrise Technologies",
                "CompanyName": "Sunrise Technologies",
                "PrimaryEmailAddr": {"Address": "accounting@sunrise.tech"},
            },
            {
                "DisplayName": "Pacific Coast Partners",
                "CompanyName": "Pacific Coast Partners",
                "PrimaryEmailAddr": {"Address": "billing@pacificcoast.com"},
            },
            {
                "DisplayName": "Quantum Dynamics Inc",
                "CompanyName": "Quantum Dynamics Inc",
                "PrimaryEmailAddr": {"Address": "invoices@quantum.com"},
            },
            {
                "DisplayName": "Silver Lining Consulting",
                "CompanyName": "Silver Lining Consulting",
                "PrimaryEmailAddr": {"Address": "payments@silverlining.co"},
            },
            {
                "DisplayName": "Mountain View Associates",
                "CompanyName": "Mountain View Associates",
                "PrimaryEmailAddr": {"Address": "finance@mountainview.com"},
            },
            {
                "DisplayName": "Urban Development Group",
                "CompanyName": "Urban Development Group",
                "PrimaryEmailAddr": {"Address": "billing@urbandev.com"},
            },
            {
                "DisplayName": "Coastal Innovations",
                "CompanyName": "Coastal Innovations",
                "PrimaryEmailAddr": {"Address": "accounting@coastal.io"},
            },
            {
                "DisplayName": "Premier Business Services",
                "CompanyName": "Premier Business Services",
                "PrimaryEmailAddr": {"Address": "accounts@premier.biz"},
            },
            {
                "DisplayName": "NextGen Solutions",
                "CompanyName": "NextGen Solutions",
                "PrimaryEmailAddr": {"Address": "billing@nextgen.com"},
            },
            {
                "DisplayName": "Digital Horizon Corp",
                "CompanyName": "Digital Horizon Corp",
                "PrimaryEmailAddr": {"Address": "invoicing@digitalhorizon.com"},
            },
        ],
        vendors=[
            {
                "DisplayName": "Office Supply Company",
                "CompanyName": "Office Supply Company",
            },
            {
                "DisplayName": "Cloud Services Provider",
                "CompanyName": "Cloud Services Provider",
            },
            {
                "DisplayName": "Marketing Agency Solutions",
                "CompanyName": "Marketing Agency Solutions",
            },
            {
                "DisplayName": "Legal Services Partners",
                "CompanyName": "Legal Services Partners",
            },
            {
                "DisplayName": "Telecommunications Inc",
                "CompanyName": "Telecommunications Inc",
            },
            {
                "DisplayName": "Equipment Rental Company",
                "CompanyName": "Equipment Rental Company",
            },
            {
                "DisplayName": "Insurance Brokers LLC",
                "CompanyName": "Insurance Brokers LLC",
            },
            {
                "DisplayName": "Property Management Group",
                "CompanyName": "Property Management Group",
            },
            {
                "DisplayName": "IT Services Consultant",
                "CompanyName": "IT Services Consultant",
            },
            {
                "DisplayName": "Accounting Services Co",
                "CompanyName": "Accounting Services Co",
            },
            {
                "DisplayName": "Shipping & Logistics Inc",
                "CompanyName": "Shipping & Logistics Inc",
            },
            {
                "DisplayName": "Web Development Studio",
                "CompanyName": "Web Development Studio",
            },
            {
                "DisplayName": "Facility Maintenance Services",
                "CompanyName": "Facility Maintenance Services",
            },
            {
                "DisplayName": "Professional Training Corp",
                "CompanyName": "Professional Training Corp",
            },
            {
                "DisplayName": "Security Systems Provider",
                "CompanyName": "Security Systems Provider",
            },
        ],
        invoices=[
            {
                "Line": [
                    {
                        "Amount": 1500,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Consulting Services - Strategic Planning",
                        "SalesItemLineDetail": {"Qty": 10, "UnitPrice": 150},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 2500,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Software Development Services",
                        "SalesItemLineDetail": {"Qty": 20, "UnitPrice": 125},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 800,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Monthly Maintenance Agreement",
                        "SalesItemLineDetail": {"Qty": 1, "UnitPrice": 800},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 3200,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Custom Application Development",
                        "SalesItemLineDetail": {"Qty": 32, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 1200,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Project Management Services",
                        "SalesItemLineDetail": {"Qty": 12, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 950,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Business Analysis and Requirements",
                        "SalesItemLineDetail": {"Qty": 10, "UnitPrice": 95},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 1800,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Training and Documentation",
                        "SalesItemLineDetail": {"Qty": 18, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 2200,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "System Integration Services",
                        "SalesItemLineDetail": {"Qty": 20, "UnitPrice": 110},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 1600,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Quality Assurance and Testing",
                        "SalesItemLineDetail": {"Qty": 16, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 2800,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Database Design and Implementation",
                        "SalesItemLineDetail": {"Qty": 20, "UnitPrice": 140},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 1400,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Security Audit Services",
                        "SalesItemLineDetail": {"Qty": 14, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 3000,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Cloud Migration Services",
                        "SalesItemLineDetail": {"Qty": 30, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 1100,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Performance Optimization",
                        "SalesItemLineDetail": {"Qty": 11, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 2400,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "API Development and Integration",
                        "SalesItemLineDetail": {"Qty": 24, "UnitPrice": 100},
                    }
                ]
            },
            {
                "Line": [
                    {
                        "Amount": 1750,
                        "DetailType": "SalesItemLineDetail",
                        "Description": "Mobile Application Development",
                        "SalesItemLineDetail": {"Qty": 14, "UnitPrice": 125},
                    }
                ]
            },
        ],
        payments=[
            {"TotalAmt": 1500},
            {"TotalAmt": 2500},
            {"TotalAmt": 800},
            {"TotalAmt": 3200},
            {"TotalAmt": 1200},
            {"TotalAmt": 950},
            {"TotalAmt": 1800},
            {"TotalAmt": 2200},
            {"TotalAmt": 1600},
            {"TotalAmt": 2800},
            {"TotalAmt": 1400},
            {"TotalAmt": 3000},
            {"TotalAmt": 1100},
            {"TotalAmt": 2400},
            {"TotalAmt": 1750},
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[QuickBooksData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_quickbooks_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_quickbooks_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_moneybird_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with moneybird-specific data following the defined schema.
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
from klavis import (
    Klavis,
    MoneybirdContact,
    MoneybirdDataInput,
    MoneybirdInvoiceDetail,
    MoneybirdLedgerAccount,
    MoneybirdProduct,
    MoneybirdProject,
    MoneybirdSalesInvoice,
    MoneybirdTimeEntry,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_moneybird_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=MoneybirdDataInput(
        ledger_accounts=[
            MoneybirdLedgerAccount(
                name="Sandbox Sales Revenue",
                account_type="revenue",
                account_id="8000",
            ),
            MoneybirdLedgerAccount(
                name="Sandbox Consulting Revenue",
                account_type="revenue",
                account_id="8100",
            ),
            MoneybirdLedgerAccount(
                name="Sandbox Product Revenue",
                account_type="revenue",
                account_id="8200",
            ),
        ],
        contacts=[
            MoneybirdContact(
                company_name="Sandbox Tech Solutions B.V.",
                phone="+31201234567",
                address1="Herengracht 123",
                city="Amsterdam",
                zipcode="1012 AB",
                country="NL",
                sepa_iban="NL91ABNA0417164300",
            ),
            MoneybirdContact(
                company_name="Sandbox Digital Marketing GmbH",
                phone="+4930123456",
                address1="Friedrichstraße 50",
                city="Berlin",
                zipcode="10117",
                country="DE",
            ),
            MoneybirdContact(
                firstname="Emma",
                lastname="van der Berg",
                phone="+31207654321",
                address1="Prinsengracht 456",
                city="Amsterdam",
                zipcode="1016 HJ",
                country="NL",
            ),
        ],
        products=[
            MoneybirdProduct(
                description="Premium Software License - Annual Subscription",
                title="Software License",
                price="2999.00",
                currency="EUR",
                identifier="SANDBOX-SOFT-001",
            ),
            MoneybirdProduct(
                description="Professional Consulting Services - Per Hour",
                title="Consulting",
                price="150.00",
                currency="EUR",
                identifier="SANDBOX-CONS-001",
            ),
            MoneybirdProduct(
                description="Web Development Services - Per Hour",
                title="Web Development",
                price="125.00",
                currency="EUR",
                identifier="SANDBOX-DEV-001",
            ),
        ],
        projects=[
            MoneybirdProject(
                name="Sandbox Website Redesign 2025",
                state="active",
                budget=15000.0,
            ),
            MoneybirdProject(
                name="Sandbox Mobile App Development",
                state="active",
                budget=50000.0,
            ),
            MoneybirdProject(
                name="Sandbox Marketing Campaign Q1",
                state="active",
                budget=10000.0,
            ),
        ],
        time_entries=[
            MoneybirdTimeEntry(
                description="Frontend development - Homepage redesign",
                hours=2.0,
                billable=True,
            ),
            MoneybirdTimeEntry(
                description="Client meeting - Project kickoff",
                hours=1.0,
                billable=True,
            ),
            MoneybirdTimeEntry(
                description="Backend API development",
                hours=4.0,
                billable=True,
            ),
        ],
        sales_invoices=[
            MoneybirdSalesInvoice(
                reference="SANDBOX-2025-001",
                currency="EUR",
                prices_are_incl_tax=False,
                state="draft",
                details=[
                    MoneybirdInvoiceDetail(
                        description="Premium Software License - Annual",
                        price="2999.00",
                        amount="1",
                    ),
                    MoneybirdInvoiceDetail(
                        description="Setup and Configuration",
                        price="500.00",
                        amount="1",
                    ),
                ],
            ),
            MoneybirdSalesInvoice(
                reference="SANDBOX-2025-002",
                currency="EUR",
                prices_are_incl_tax=False,
                state="draft",
                details=[
                    MoneybirdInvoiceDetail(
                        description="Consulting Services",
                        price="150.00",
                        amount="20",
                    )
                ],
            ),
            MoneybirdSalesInvoice(
                reference="SANDBOX-2025-003",
                currency="EUR",
                prices_are_incl_tax=False,
                state="draft",
                details=[
                    MoneybirdInvoiceDetail(
                        description="Web Development Services",
                        price="125.00",
                        amount="40",
                    ),
                    MoneybirdInvoiceDetail(
                        description="Design Services",
                        price="100.00",
                        amount="15",
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[MoneybirdDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_moneybird_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_moneybird_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_dropbox_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with dropbox-specific data following the defined schema.
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
from klavis import DropboxData, DropboxFile, Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_dropbox_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=DropboxData(
        folders=[
            "/SandboxTest",
            "/SandboxTest/Documents",
            "/SandboxTest/Documents/Reports",
            "/SandboxTest/Documents/Contracts",
            "/SandboxTest/Images",
            "/SandboxTest/Images/Photos",
            "/SandboxTest/Images/Graphics",
            "/SandboxTest/Projects",
            "/SandboxTest/Projects/ProjectA",
            "/SandboxTest/Projects/ProjectB",
            "/SandboxTest/Archives",
            "/SandboxTest/Templates",
            "/SandboxTest/Shared",
            "/SandboxTest/Backups",
        ],
        files=[
            DropboxFile(
                path="/SandboxTest/README.txt",
                content="Welcome to the Klavis Sandbox Test Environment. This is a test workspace for file operations.",
            ),
            DropboxFile(
                path="/SandboxTest/Documents/meeting_notes.txt",
                content="Meeting Notes - 2025-01-15\\n\\n- Discussed Q1 objectives\\n- Reviewed project timeline\\n- Action items assigned",
            ),
            DropboxFile(
                path="/SandboxTest/Documents/Reports/quarterly_report.txt",
                content="Q4 2024 Quarterly Report\\n\\nRevenue: $1.2M\\nExpenses: $800K\\nProfit: $400K\\n\\nKey highlights: Strong growth in enterprise segment.",
            ),
            DropboxFile(
                path="/SandboxTest/Documents/Reports/annual_summary.txt",
                content="Annual Summary 2024\\n\\nTotal revenue: $4.5M\\nYear-over-year growth: 35%\\nNew customers: 150",
            ),
            DropboxFile(
                path="/SandboxTest/Documents/Contracts/client_agreement.txt",
                content="Client Service Agreement\\n\\nThis agreement is entered into on January 1, 2025\\nBetween: Klavis AI\\nAnd: Acme Corporation",
            ),
            DropboxFile(
                path="/SandboxTest/Documents/Contracts/vendor_contract.txt",
                content="Vendor Service Contract\\n\\nContract ID: VC-2025-001\\nEffective Date: 2025-01-01\\nTerm: 12 months",
            ),
            DropboxFile(
                path="/SandboxTest/Images/sample_image.txt",
                content="[Image placeholder: sample_image.jpg - Landscape photo]",
            ),
            DropboxFile(
                path="/SandboxTest/Images/Photos/vacation_photo.txt",
                content="[Image placeholder: vacation_photo.jpg - Beach sunset]",
            ),
            DropboxFile(
                path="/SandboxTest/Images/Graphics/logo_design.txt",
                content="[Image placeholder: logo_design.svg - Company logo vector]",
            ),
            DropboxFile(
                path="/SandboxTest/Projects/ProjectA/project_plan.txt",
                content="Project A - Implementation Plan\\n\\nPhase 1: Requirements gathering (2 weeks)\\nPhase 2: Development (6 weeks)\\nPhase 3: Testing (2 weeks)\\nPhase 4: Deployment (1 week)",
            ),
            DropboxFile(
                path="/SandboxTest/Projects/ProjectA/status.txt",
                content="Project A Status Update\\n\\nCurrent Phase: Phase 2 (Development)\\nProgress: 45% complete\\nNext milestone: Alpha release",
            ),
            DropboxFile(
                path="/SandboxTest/Projects/ProjectB/specifications.txt",
                content="Project B Technical Specifications\\n\\nPlatform: Web-based\\nFramework: React + Node.js\\nDatabase: PostgreSQL\\nDeployment: AWS",
            ),
            DropboxFile(
                path="/SandboxTest/Projects/ProjectB/timeline.txt",
                content="Project B Timeline\\n\\nStart Date: 2025-02-01\\nEstimated Completion: 2025-05-31\\nMilestones: 5 key deliverables",
            ),
            DropboxFile(
                path="/SandboxTest/Archives/archive_2024.txt",
                content="Archived data from 2024 fiscal year. Contains completed projects and finalized documents.",
            ),
            DropboxFile(
                path="/SandboxTest/Templates/email_template.txt",
                content="Email Template\\n\\nSubject: [Topic]\\n\\nDear [Name],\\n\\n[Message body]\\n\\nBest regards,\\n[Your name]",
            ),
            DropboxFile(
                path="/SandboxTest/Templates/report_template.txt",
                content="Report Template\\n\\n1. Executive Summary\\n2. Introduction\\n3. Findings\\n4. Recommendations\\n5. Conclusion",
            ),
            DropboxFile(
                path="/SandboxTest/Shared/team_calendar.txt",
                content="Team Calendar - January 2025\\n\\nWeek 1: Sprint planning\\nWeek 2: Development\\nWeek 3: Code review\\nWeek 4: Sprint retrospective",
            ),
            DropboxFile(
                path="/SandboxTest/Shared/resources.txt",
                content="Shared Resources\\n\\n- Design guidelines\\n- Code style guide\\n- Documentation templates\\n- Testing procedures",
            ),
            DropboxFile(
                path="/SandboxTest/Backups/config_backup.txt",
                content="Configuration Backup\\n\\nBackup Date: 2025-01-15\\nSystem: Production\\nStatus: Complete\\nRetention: 90 days",
            ),
            DropboxFile(
                path="/SandboxTest/notes.txt",
                content="General Notes\\n\\n- Remember to update documentation\\n- Schedule team sync meeting\\n- Review pending pull requests",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[DropboxData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_dropbox_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_dropbox_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_shopify_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with shopify-specific data following the defined schema.
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
from klavis import (
    Klavis,
    ShopifyCustomer,
    ShopifyDataInput,
    ShopifyOrder,
    ShopifyOrderLineItem,
    ShopifyProduct,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_shopify_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=ShopifyDataInput(
        products=[
            ShopifyProduct(
                title="[Sandbox] Premium Cotton T-Shirt",
                description="High-quality cotton t-shirt perfect for everyday wear",
                vendor="Sandbox Apparel Co",
                category="Apparel",
                price="29.99",
                sku="SAND-TSHIRT-001",
                stock=100,
            ),
            ShopifyProduct(
                title="[Sandbox] Wireless Bluetooth Headphones",
                description="Premium noise-canceling headphones with 30-hour battery life",
                vendor="Sandbox Electronics",
                category="Electronics",
                price="149.99",
                sku="SAND-HEADPH-001",
                stock=50,
            ),
            ShopifyProduct(
                title="[Sandbox] Organic Coffee Beans - Dark Roast",
                description="Ethically sourced, organic dark roast coffee beans",
                vendor="Sandbox Coffee Roasters",
                category="Food & Beverage",
                price="18.99",
                sku="SAND-COFFEE-001",
                stock=200,
            ),
            ShopifyProduct(
                title="[Sandbox] Yoga Mat - Eco Friendly",
                description="Non-slip, eco-friendly yoga mat made from natural rubber",
                vendor="Sandbox Fitness Gear",
                category="Sports & Fitness",
                price="45.00",
                sku="SAND-YOGA-001",
                stock=75,
            ),
            ShopifyProduct(
                title="[Sandbox] Leather Wallet - Minimalist",
                description="Handcrafted minimalist leather wallet with RFID protection",
                vendor="Sandbox Leather Goods",
                category="Accessories",
                price="59.99",
                sku="SAND-WALLET-001",
                stock=60,
            ),
            ShopifyProduct(
                title="[Sandbox] Smart Watch - Fitness Tracker",
                description="Advanced fitness tracking with heart rate monitor and GPS",
                vendor="Sandbox Tech",
                category="Electronics",
                price="199.99",
                sku="SAND-WATCH-001",
                stock=40,
            ),
            ShopifyProduct(
                title="[Sandbox] Ceramic Coffee Mug Set",
                description="Set of 4 handmade ceramic coffee mugs in various colors",
                vendor="Sandbox Home Goods",
                category="Home & Kitchen",
                price="39.99",
                sku="SAND-MUG-001",
                stock=120,
            ),
            ShopifyProduct(
                title="[Sandbox] Portable Phone Charger",
                description="High-capacity 20000mAh portable battery pack with fast charging",
                vendor="Sandbox Electronics",
                category="Electronics",
                price="34.99",
                sku="SAND-CHARGER-001",
                stock=150,
            ),
            ShopifyProduct(
                title="[Sandbox] Stainless Steel Water Bottle",
                description="Insulated water bottle keeps drinks cold for 24 hours",
                vendor="Sandbox Outdoor Gear",
                category="Sports & Fitness",
                price="24.99",
                sku="SAND-BOTTLE-001",
                stock=180,
            ),
            ShopifyProduct(
                title="[Sandbox] Backpack - Travel",
                description="Durable travel backpack with laptop compartment",
                vendor="Sandbox Travel Gear",
                category="Bags & Luggage",
                price="69.99",
                sku="SAND-BACKPACK-001",
                stock=90,
            ),
        ],
        customers=[
            ShopifyCustomer(
                email="john.smith@sandbox-test.example.com",
                name="John Smith",
                address="123 Main Street",
                city="San Francisco",
                state="CA",
                zip="94102",
                country="US",
            ),
            ShopifyCustomer(
                email="emma.wilson@sandbox-test.example.com",
                name="Emma Wilson",
                address="456 Oak Avenue",
                city="New York",
                state="NY",
                zip="10001",
                country="US",
            ),
            ShopifyCustomer(
                email="michael.chen@sandbox-test.example.com",
                name="Michael Chen",
                address="789 Pine Road",
                city="Seattle",
                state="WA",
                zip="98101",
                country="US",
            ),
            ShopifyCustomer(
                email="sophia.martinez@sandbox-test.example.com",
                name="Sophia Martinez",
                address="321 Elm Street",
                city="Austin",
                state="TX",
                zip="78701",
                country="US",
            ),
            ShopifyCustomer(
                email="oliver.brown@sandbox-test.example.com",
                name="Oliver Brown",
                address="654 Maple Drive",
                city="Boston",
                state="MA",
                zip="02101",
                country="US",
            ),
            ShopifyCustomer(
                email="ava.johnson@sandbox-test.example.com",
                name="Ava Johnson",
                address="987 Cedar Lane",
                city="Denver",
                state="CO",
                zip="80201",
                country="US",
            ),
            ShopifyCustomer(
                email="isabella.garcia@sandbox-test.example.com",
                name="Isabella Garcia",
                address="258 Willow Way",
                city="Miami",
                state="FL",
                zip="33101",
                country="US",
            ),
            ShopifyCustomer(
                email="liam.miller@sandbox-test.example.com",
                name="Liam Miller",
                address="369 Spruce Court",
                city="Chicago",
                state="IL",
                zip="60601",
                country="US",
            ),
        ],
        orders=[
            ShopifyOrder(
                customer_index=0,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=0,
                        quantity=2,
                    )
                ],
                financial_status="paid",
            ),
            ShopifyOrder(
                customer_index=1,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=1,
                        quantity=1,
                    )
                ],
                financial_status="pending",
            ),
            ShopifyOrder(
                customer_index=2,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=2,
                        quantity=3,
                    )
                ],
                financial_status="paid",
            ),
            ShopifyOrder(
                customer_index=3,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=3,
                        quantity=1,
                    ),
                    ShopifyOrderLineItem(
                        product_index=4,
                        quantity=2,
                    ),
                ],
                financial_status="paid",
            ),
            ShopifyOrder(
                customer_index=4,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=5,
                        quantity=1,
                    )
                ],
                financial_status="pending",
            ),
            ShopifyOrder(
                customer_index=5,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=6,
                        quantity=4,
                    )
                ],
                financial_status="paid",
            ),
            ShopifyOrder(
                customer_index=6,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=7,
                        quantity=1,
                    ),
                    ShopifyOrderLineItem(
                        product_index=8,
                        quantity=2,
                    ),
                ],
                financial_status="paid",
            ),
            ShopifyOrder(
                customer_index=7,
                line_items=[
                    ShopifyOrderLineItem(
                        product_index=9,
                        quantity=1,
                    )
                ],
                financial_status="pending",
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[ShopifyDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_shopify_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_shopify_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_outlook_calendar_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with outlook_calendar-specific data following the defined schema.
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
from klavis import Klavis, OutlookCalendarData, OutlookCalendarEvent

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_outlook_calendar_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=OutlookCalendarData(
        calendar_events=[
            OutlookCalendarEvent(
                title="Team Meeting",
                start_time={
                    "dateTime": "2025-11-20T14:00:00",
                    "timeZone": "UTC",
                },
                end_time={"dateTime": "2025-11-20T15:00:00", "timeZone": "UTC"},
                event_location="Conference Room A",
            ),
            OutlookCalendarEvent(
                title="Project Review",
                start_time={
                    "dateTime": "2025-11-21T10:00:00",
                    "timeZone": "UTC",
                },
                end_time={"dateTime": "2025-11-21T12:00:00", "timeZone": "UTC"},
                event_location="Virtual",
                event_attendees=[
                    "colleague@example.com",
                    "manager@example.com",
                ],
            ),
            OutlookCalendarEvent(
                title="1:1 with Manager",
                start_time={
                    "dateTime": "2025-11-22T15:00:00",
                    "timeZone": "UTC",
                },
                end_time={"dateTime": "2025-11-22T15:30:00", "timeZone": "UTC"},
            ),
            OutlookCalendarEvent(
                title="Sprint Planning",
                start_time={
                    "dateTime": "2025-11-23T09:00:00",
                    "timeZone": "UTC",
                },
                end_time={"dateTime": "2025-11-23T11:00:00", "timeZone": "UTC"},
                event_location="Main Office - Room 301",
                event_attendees=[
                    "dev1@example.com",
                    "dev2@example.com",
                    "pm@example.com",
                ],
            ),
            OutlookCalendarEvent(
                title="Client Presentation",
                start_time={
                    "dateTime": "2025-11-24T14:00:00",
                    "timeZone": "UTC",
                },
                end_time={"dateTime": "2025-11-24T16:00:00", "timeZone": "UTC"},
                event_location="Zoom Meeting",
                event_attendees=["client@company.com", "sales@example.com"],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[OutlookCalendarData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_outlook_calendar_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_outlook_calendar_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_clickup_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with clickup-specific data following the defined schema.
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
from klavis import (
    ClickUpComment,
    ClickUpDataInput,
    ClickUpFolder,
    ClickUpList,
    ClickUpSpace,
    ClickUpTask,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_clickup_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=ClickUpDataInput(
        spaces=[
            ClickUpSpace(
                name="Product Development Space",
                folders=[
                    ClickUpFolder(
                        name="Engineering Projects",
                        lists=[
                            ClickUpList(
                                name="Backend Development",
                                description="API and server-side development tasks",
                                tasks=[
                                    ClickUpTask(
                                        name="Implement user authentication API",
                                        description="Create REST API endpoints for user login, registration, and password reset",
                                        priority=1,
                                        comments=[
                                            ClickUpComment(
                                                body="We should use OAuth2 with JWT tokens for better security",
                                            ),
                                            ClickUpComment(
                                                body="Don't forget to implement rate limiting",
                                            ),
                                        ],
                                    ),
                                    ClickUpTask(
                                        name="Integrate payment gateway",
                                        description="Integrate Stripe payment processing for subscription billing",
                                        priority=1,
                                        comments=[
                                            ClickUpComment(
                                                body="We need to handle webhook events for payment status updates",
                                            )
                                        ],
                                    ),
                                    ClickUpTask(
                                        name="Optimize database queries",
                                        description="Identify and optimize slow database queries, add appropriate indexes",
                                        priority=2,
                                    ),
                                    ClickUpTask(
                                        name="Set up Redis caching",
                                        priority=2,
                                    ),
                                ],
                            ),
                            ClickUpList(
                                name="Frontend Development",
                                description="UI/UX implementation tasks",
                                tasks=[
                                    ClickUpTask(
                                        name="Build responsive navigation component",
                                        description="Implement responsive navigation menu with mobile hamburger menu support",
                                        priority=3,
                                        comments=[
                                            ClickUpComment(
                                                body="Consider using a CSS framework like Tailwind for faster development",
                                            )
                                        ],
                                    ),
                                    ClickUpTask(
                                        name="Create onboarding flow",
                                        description="Design and implement user onboarding flow with progress indicators",
                                        priority=2,
                                    ),
                                    ClickUpTask(
                                        name="Fix layout bug on mobile",
                                        priority=1,
                                        comments=[
                                            ClickUpComment(
                                                body="Issue reported on iPhone 12 and 13",
                                            ),
                                            ClickUpComment(
                                                body="Seems to be related to flexbox layout",
                                            ),
                                            ClickUpComment(
                                                body="Fixed in dev branch, ready for testing",
                                            ),
                                        ],
                                    ),
                                ],
                            ),
                            ClickUpList(
                                name="Mobile Development",
                                description="iOS and Android app development",
                                tasks=[
                                    ClickUpTask(
                                        name="Implement push notifications",
                                        description="Add push notification support for iOS and Android using Firebase",
                                        priority=3,
                                    ),
                                    ClickUpTask(
                                        name="Update app icons",
                                        description="Create and update app icons for all required sizes",
                                        priority=4,
                                    ),
                                    ClickUpTask(
                                        name="Research biometric authentication",
                                    ),
                                ],
                            ),
                            ClickUpList(
                                name="Backlog",
                                tasks=[
                                    ClickUpTask(
                                        name="name",
                                    )
                                ],
                            ),
                        ],
                    ),
                    ClickUpFolder(
                        name="Design & UX",
                        lists=[
                            ClickUpList(
                                name="Design Assets",
                                description="Design mockups and assets",
                                tasks=[
                                    ClickUpTask(
                                        name="Design landing page mockups",
                                        description="Create high-fidelity mockups for the new landing page with mobile and desktop variants",
                                        priority=2,
                                        comments=[
                                            ClickUpComment(
                                                body="Let's follow the existing design system for consistency",
                                            )
                                        ],
                                    ),
                                    ClickUpTask(
                                        name="Create icon set",
                                        description="Design custom icon set for the application",
                                        priority=3,
                                    ),
                                ],
                            ),
                            ClickUpList(
                                name="User Research",
                                description="User testing and feedback",
                                tasks=[
                                    ClickUpTask(
                                        name="Conduct user interviews",
                                        description="Interview 10 users about their experience with the product",
                                        priority=2,
                                        comments=[
                                            ClickUpComment(
                                                body="Schedule for next week",
                                            )
                                        ],
                                    )
                                ],
                            ),
                        ],
                    ),
                    ClickUpFolder(
                        name="Quality Assurance",
                        lists=[
                            ClickUpList(
                                name="Testing & Bug Fixes",
                                description="QA testing and bug tracking",
                                tasks=[
                                    ClickUpTask(
                                        name="Conduct accessibility audit",
                                        description="Review and improve accessibility features to meet WCAG 2.1 AA standards",
                                        priority=3,
                                    ),
                                    ClickUpTask(
                                        name="Write integration tests",
                                        priority=2,
                                        comments=[
                                            ClickUpComment(
                                                body="body",
                                            )
                                        ],
                                    ),
                                    ClickUpTask(
                                        name="Load testing",
                                    ),
                                ],
                            )
                        ],
                    ),
                    ClickUpFolder(
                        name="Archive",
                        lists=[
                            ClickUpList(
                                name="name",
                            )
                        ],
                    ),
                ],
                lists=[
                    ClickUpList(
                        name="DevOps & Infrastructure",
                        description="Infrastructure and deployment tasks (folderless)",
                        tasks=[
                            ClickUpTask(
                                name="Set up CI/CD pipeline",
                                description="Configure automated testing and deployment pipeline using GitHub Actions",
                                priority=2,
                                comments=[
                                    ClickUpComment(
                                        body="Make sure to include automated tests in the pipeline",
                                    )
                                ],
                            ),
                            ClickUpTask(
                                name="Write API documentation",
                                description="Document all API endpoints with examples using OpenAPI/Swagger",
                                priority=3,
                            ),
                            ClickUpTask(
                                name="Set up monitoring alerts",
                                priority=1,
                                comments=[
                                    ClickUpComment(
                                        body="Use Datadog or similar",
                                    )
                                ],
                            ),
                        ],
                    ),
                    ClickUpList(
                        name="General Tasks",
                        tasks=[
                            ClickUpTask(
                                name="Team standup meeting notes",
                            )
                        ],
                    ),
                ],
            ),
            ClickUpSpace(
                name="Marketing & Sales Space",
                folders=[
                    ClickUpFolder(
                        name="Campaigns",
                        lists=[
                            ClickUpList(
                                name="Q1 Campaign",
                                description="First quarter marketing campaign",
                                tasks=[
                                    ClickUpTask(
                                        name="Create email templates",
                                        description="Design and code responsive email templates",
                                        priority=1,
                                    ),
                                    ClickUpTask(
                                        name="Social media content calendar",
                                        priority=2,
                                        comments=[
                                            ClickUpComment(
                                                body="Focus on LinkedIn and Twitter",
                                            )
                                        ],
                                    ),
                                ],
                            )
                        ],
                    )
                ],
                lists=[
                    ClickUpList(
                        name="Sales Pipeline",
                        description="Track sales opportunities",
                        tasks=[
                            ClickUpTask(
                                name="Follow up with Enterprise Lead A",
                                description="Schedule demo call",
                                priority=1,
                                comments=[
                                    ClickUpComment(
                                        body="They requested custom pricing",
                                    )
                                ],
                            ),
                            ClickUpTask(
                                name="Prepare Q4 sales report",
                            ),
                        ],
                    )
                ],
            ),
            ClickUpSpace(
                name="Personal Workspace",
                folders=[
                    ClickUpFolder(
                        name="name",
                    )
                ],
                lists=[
                    ClickUpList(
                        name="My Tasks",
                        tasks=[
                            ClickUpTask(
                                name="Review code",
                                priority=1,
                            )
                        ],
                    )
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[ClickUpDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_clickup_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_clickup_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_close_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with close-specific data following the defined schema.
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
from klavis import (
    CloseContact,
    CloseDataInput,
    CloseLead,
    CloseOpportunity,
    CloseTask,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_close_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=CloseDataInput(
        leads=[
            CloseLead(
                name="CloudScale Technologies Inc.",
                status="Potential",
                contacts=[
                    CloseContact(
                        name="Sarah Mitchell",
                        emails=[
                            {
                                "email": "sarah.mitchell@cloudscale.tech",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    ),
                    CloseContact(
                        name="David Thompson",
                        emails=[
                            {
                                "email": "dthompson@cloudscale.tech",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    ),
                ],
                opportunities=[
                    CloseOpportunity(
                        note="Annual SaaS subscription renewal - CloudScale Technologies",
                        value=48000,
                        confidence=85,
                        period="annual",
                    ),
                    CloseOpportunity(
                        note="Cloud infrastructure migration - CloudScale expansion",
                        value=180000,
                        confidence=55,
                        period="one_time",
                    ),
                ],
                tasks=[
                    CloseTask(
                        description="Send proposal document to Sarah Mitchell at CloudScale",
                        date="2025-12-02",
                        completed=False,
                    ),
                    CloseTask(
                        description="Connect with decision maker David Thompson regarding budget approval",
                        date="2025-12-03",
                        completed=False,
                    ),
                    CloseTask(
                        description="Submit quarterly business review deck to CloudScale Technologies",
                        date="2025-12-09",
                        completed=False,
                    ),
                ],
            ),
            CloseLead(
                name="DataFlow Analytics Corp",
                status="Potential",
                contacts=[
                    CloseContact(
                        name="Michael Chen",
                        emails=[
                            {
                                "email": "m.chen@dataflowanalytics.com",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    ),
                    CloseContact(
                        name="Jennifer Martinez",
                        emails=[
                            {
                                "email": "jen.martinez@dataflowanalytics.com",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    ),
                ],
                opportunities=[
                    CloseOpportunity(
                        note="Enterprise data analytics platform implementation for DataFlow",
                        value=125000,
                        confidence=60,
                        period="one_time",
                    )
                ],
                tasks=[
                    CloseTask(
                        description="Schedule technical demo call with DataFlow Analytics team",
                        date="2025-12-03",
                        completed=False,
                    ),
                    CloseTask(
                        description="Send case studies and customer references to Michael Chen",
                        date="2025-12-08",
                        completed=False,
                    ),
                    CloseTask(
                        description="Follow up on security compliance questions from Jennifer Martinez",
                        date="2025-12-06",
                        completed=False,
                    ),
                ],
            ),
            CloseLead(
                name="Phoenix Digital Marketing Agency",
                status="Potential",
                contacts=[
                    CloseContact(
                        name="Emily Rodriguez",
                        emails=[
                            {
                                "email": "emily.r@phoenixdigital.io",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    ),
                    CloseContact(
                        name="Robert Chang",
                        emails=[
                            {
                                "email": "rchang@phoenixdigital.io",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    ),
                ],
                opportunities=[
                    CloseOpportunity(
                        note="Digital transformation consulting package - Phoenix Digital",
                        value=75000,
                        confidence=70,
                        period="one_time",
                    ),
                    CloseOpportunity(
                        note="Marketing automation platform upgrade - Phoenix Digital",
                        value=28000,
                        confidence=90,
                        period="monthly",
                    ),
                ],
                tasks=[
                    CloseTask(
                        description="Follow up on pricing questions from Emily Rodriguez",
                        date="2025-12-02",
                        completed=False,
                    ),
                    CloseTask(
                        description="Schedule onboarding kickoff meeting with Phoenix Digital",
                        date="2025-12-10",
                        completed=False,
                    ),
                ],
            ),
            CloseLead(
                name="Vertex Manufacturing Solutions",
                status="Potential",
                contacts=[
                    CloseContact(
                        name="James Patterson",
                        emails=[
                            {
                                "email": "j.patterson@vertexmfg.com",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    )
                ],
                opportunities=[
                    CloseOpportunity(
                        note="ERP system integration and training - Vertex Manufacturing",
                        value=95000,
                        confidence=45,
                        period="one_time",
                    )
                ],
                tasks=[
                    CloseTask(
                        description="Review and finalize contract terms with Vertex Manufacturing legal",
                        date="2025-12-05",
                        completed=False,
                    )
                ],
            ),
            CloseLead(
                name="Lighthouse Financial Advisors",
                status="Potential",
                contacts=[
                    CloseContact(
                        name="Alexandra Kim",
                        emails=[
                            {
                                "email": "alex.kim@lighthousefa.com",
                                "type": "office",
                                "is_unsubscribed": False,
                            }
                        ],
                    )
                ],
                opportunities=[
                    CloseOpportunity(
                        note="Financial planning software suite - Lighthouse FA",
                        value=32000,
                        confidence=80,
                        period="annual",
                    )
                ],
                tasks=[
                    CloseTask(
                        description="Prepare ROI analysis for Lighthouse Financial Advisors",
                        date="2025-12-04",
                        completed=False,
                    )
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[CloseDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_close_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_close_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_resend_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with resend-specific data following the defined schema.
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
from klavis import (
    Klavis,
    ResendBroadcast,
    ResendContact,
    ResendDataInput,
    ResendSegment,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_resend_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=ResendDataInput(
        contacts=[
            ResendContact(
                email="robert.johnson@techcorp.com",
                first_name="Robert",
                last_name="Johnson",
                unsubscribed=False,
            ),
            ResendContact(
                email="maria.garcia@innovate.io",
                first_name="Maria",
                last_name="Garcia",
                unsubscribed=False,
            ),
            ResendContact(
                email="david.lee@startup.com",
                first_name="David",
                last_name="Lee",
                unsubscribed=False,
            ),
        ],
        segments=[
            ResendSegment(
                name="Premium Customers",
                broadcasts=[
                    ResendBroadcast(
                        from_="onboarding@resend.dev",
                        subject="Exclusive Premium Member Benefits This Month",
                        name="Premium Benefits December",
                        html="<h1>Premium Member Exclusive</h1><p>As a valued premium member, enjoy these exclusive benefits this month...</p><ul><li>20% off all products</li><li>Early access to new features</li><li>Priority support</li></ul>",
                        text="Premium Member Exclusive - Enjoy 20% off all products, early access to new features, and priority support this month.",
                        status="draft",
                    )
                ],
            ),
            ResendSegment(
                name="Newsletter Subscribers",
                broadcasts=[
                    ResendBroadcast(
                        from_="onboarding@resend.dev",
                        subject="ACME Monthly Newsletter - December 2025",
                        name="December Newsletter",
                        html="<div><h1>December Newsletter</h1><h2>What's New This Month</h2><p>Here are the highlights from December...</p><ul><li>Product updates</li><li>Customer success stories</li><li>Upcoming events</li></ul></div>",
                        text="December Newsletter - What's New This Month: Product updates, customer success stories, and upcoming events.",
                        reply_to="feedback@acmecorp.com",
                        status="draft",
                    )
                ],
            ),
            ResendSegment(
                name="Trial Users",
                broadcasts=[
                    ResendBroadcast(
                        from_="onboarding@resend.dev",
                        subject="Getting Started with Your Free Trial",
                        name="Trial Onboarding Sequence",
                        html="<h1>Welcome to Your Free Trial!</h1><p>Let's get you started with some helpful resources...</p><div><h3>Quick Start Guide</h3><ol><li>Complete your profile</li><li>Explore the dashboard</li><li>Try our key features</li></ol></div>",
                        text="Welcome to Your Free Trial! Quick Start Guide: 1) Complete your profile 2) Explore the dashboard 3) Try our key features",
                        status="draft",
                    )
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[ResendDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_resend_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_resend_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_wordpress_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with wordpress-specific data following the defined schema.
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
from klavis import Klavis, Post, PostFormat, Status, WordPressData

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_wordpress_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=WordPressData(
        posts=[
            Post(
                title="Welcome to Klavis AI WordPress Integration",
                content="<p>This is the first test post created through Klavis AI's WordPress sandbox.</p><p>We're testing the full CRUD functionality with WordPress.com REST API v1.1.</p><p>Key features being tested:</p><ul><li>Post creation with multiple statuses</li><li>Categories and tags management</li><li>Different post formats</li><li>Content formatting with HTML</li></ul>",
                status=Status.PUBLISH,
                summary="Testing Klavis AI WordPress sandbox integration with full CRUD support",
                categories=["Technology", "Integration", "API"],
                tags=["klavis", "wordpress", "mcp", "testing", "rest-api"],
                format=PostFormat.STANDARD,
            ),
            Post(
                title="Understanding MCP (Model Context Protocol)",
                content="<h2>What is MCP?</h2><p>The Model Context Protocol (MCP) is a revolutionary approach to AI integrations.</p><h3>Key Benefits</h3><ul><li>Standardized integration patterns</li><li>Secure authentication flows</li><li>Sandbox testing environments</li><li>Rate limiting and error handling</li></ul><blockquote>MCP enables AI agents to reliably interact with 100+ tools at scale.</blockquote>",
                status=Status.PUBLISH,
                summary="Learn about the Model Context Protocol and how it revolutionizes AI integrations",
                categories=["Technology", "Education"],
                tags=["mcp", "ai", "protocol", "integration"],
                format=PostFormat.STANDARD,
            ),
            Post(
                title="Draft Post: Future Features Roadmap",
                content="<p>This is a draft post about upcoming features in the WordPress sandbox...</p><h3>Planned Features</h3><ul><li><strong>Pages Support</strong>: Create and manage WordPress pages</li><li><strong>Media Management</strong>: Upload and attach featured images</li><li><strong>Comments</strong>: Handle post comments via API</li><li><strong>Custom Post Types</strong>: Support for custom content types</li><li><strong>Post Relationships</strong>: Parent/child post hierarchies</li></ul><p>Stay tuned for updates!</p>",
                status=Status.DRAFT,
                summary="Planning future WordPress integration features and enhancements",
                categories=["Product Updates", "Roadmap"],
                tags=["roadmap", "features", "planning"],
                format=PostFormat.STANDARD,
            ),
            Post(
                title="Quick Note: Integration Best Practices",
                content="<p>A quick aside about best practices when integrating with WordPress.com API:</p><ol><li>Always handle rate limits gracefully</li><li>Use OAuth 2.0 for authentication</li><li>Validate data before sending to API</li><li>Normalize responses for consistency</li></ol>",
                status=Status.PUBLISH,
                summary="Best practices for WordPress API integration",
                categories=["Documentation"],
                tags=["notes", "quick", "best-practices"],
                format=PostFormat.ASIDE,
            ),
            Post(
                title="Image Gallery: Integration Screenshots",
                content="<p>This post showcases screenshots of the integration process.</p><p>[Gallery would go here with multiple images showing the OAuth flow, sandbox dashboard, and API responses]</p>",
                status=Status.PUBLISH,
                summary="Visual guide to WordPress integration",
                categories=["Documentation", "Visual"],
                tags=["gallery", "screenshots", "visual"],
                format=PostFormat.GALLERY,
            ),
            Post(
                title="Link: WordPress REST API Documentation",
                content='<p>Check out the official WordPress.com REST API documentation for more details:</p><p><a href="https://developer.wordpress.com/docs/api/">https://developer.wordpress.com/docs/api/</a></p>',
                status=Status.PUBLISH,
                categories=["Resources"],
                tags=["link", "documentation", "reference"],
                format=PostFormat.LINK,
            ),
            Post(
                title="Inspirational Quote",
                content='<blockquote>"The best way to predict the future is to implement it." - Klavis AI Team</blockquote><p>This quote inspires our approach to building robust integrations.</p>',
                status=Status.PUBLISH,
                categories=["Inspiration"],
                tags=["quote", "inspiration"],
                format=PostFormat.QUOTE,
            ),
            Post(
                title="Private Internal Note",
                content="<p>This is a private post for internal team use only.</p><p>Internal metrics:</p><ul><li>OAuth completion rate: 98%</li><li>API success rate: 99.5%</li><li>Average response time: 250ms</li></ul>",
                status=Status.PRIVATE,
                summary="Internal metrics and notes",
                categories=["Internal"],
                tags=["private", "metrics", "internal"],
                format=PostFormat.STANDARD,
            ),
            Post(
                title="Testing Categories and Tags",
                content="<p>This post tests extensive categorization and tagging capabilities.</p><p>WordPress allows multiple categories and tags per post, which we're testing here.</p>",
                status=Status.PUBLISH,
                summary="Testing multi-category and multi-tag support",
                categories=[
                    "Testing",
                    "Quality Assurance",
                    "Automation",
                    "CI/CD",
                ],
                tags=[
                    "test",
                    "qa",
                    "automation",
                    "categories",
                    "tags",
                    "metadata",
                ],
                format=PostFormat.STANDARD,
            ),
            Post(
                title="Draft: Pending Review Article",
                content="<p>This article is pending editorial review before publication.</p><p>It covers advanced topics in WordPress automation and sandbox testing.</p>",
                status=Status.PENDING,
                summary="Advanced WordPress automation topics - pending review",
                categories=["Advanced"],
                tags=["pending", "review", "advanced"],
                format=PostFormat.STANDARD,
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[WordPressData]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_wordpress_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_wordpress_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_asana_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with asana-specific data following the defined schema.
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
from klavis import AsanaDataInput, AsanaProject, AsanaStory, AsanaTask, Klavis

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_asana_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=AsanaDataInput(
        projects=[
            AsanaProject(
                name="Website Redesign Project",
                description="Complete redesign of company website with modern UI/UX",
                tasks=[
                    AsanaTask(
                        name="Design homepage mockups",
                        description="Create initial design mockups for the new homepage layout",
                        completed=False,
                        due_date="2025-12-15",
                        stories=[
                            AsanaStory(
                                text="Let's prioritize the mobile-first design approach for this mockup",
                            )
                        ],
                    ),
                    AsanaTask(
                        name="Fix navigation menu bug",
                        description="Navigation menu not working properly on mobile devices",
                        completed=False,
                        due_date="2025-12-03",
                        stories=[
                            AsanaStory(
                                text="This bug is blocking the mobile release, marking as urgent",
                            )
                        ],
                    ),
                ],
            ),
            AsanaProject(
                name="Mobile App Development",
                description="iOS and Android app development for customer portal",
                tasks=[
                    AsanaTask(
                        name="Set up development environment",
                        description="Configure local development environment for mobile app",
                        completed=False,
                        due_date="2025-12-05",
                        stories=[
                            AsanaStory(
                                text="We should ensure the development environment uses the latest stable versions",
                            )
                        ],
                    ),
                    AsanaTask(
                        name="Write API documentation",
                        description="Document all REST API endpoints for the mobile app",
                        completed=False,
                        due_date="2025-12-20",
                        stories=[
                            AsanaStory(
                                text="Include code examples for each API endpoint to help developers",
                            )
                        ],
                    ),
                    AsanaTask(
                        name="Implement user authentication",
                        description="Add OAuth2 authentication flow to mobile app",
                        completed=False,
                        due_date="2025-12-22",
                    ),
                ],
            ),
            AsanaProject(
                name="Marketing Campaign Q4",
                description="Q4 marketing initiatives and campaign planning",
                tasks=[
                    AsanaTask(
                        name="Create social media content calendar",
                        description="Plan and schedule social media posts for Q4 campaign",
                        completed=False,
                        due_date="2025-12-10",
                        stories=[
                            AsanaStory(
                                text="Don't forget to coordinate with the content team for approval",
                            )
                        ],
                    ),
                    AsanaTask(
                        name="Review competitor analysis",
                        description="Analyze competitor offerings and positioning",
                        completed=False,
                        due_date="2025-12-08",
                        stories=[
                            AsanaStory(
                                text="This is critical for our competitive positioning",
                            )
                        ],
                    ),
                    AsanaTask(
                        name="Update brand guidelines",
                        description="Refresh brand guidelines to reflect new visual identity",
                        completed=False,
                        due_date="2025-12-12",
                        stories=[
                            AsanaStory(
                                text="The new guidelines should include updated logo usage rules",
                            )
                        ],
                    ),
                ],
            ),
            AsanaProject(
                name="Product Launch 2025",
                description="New product launch preparation and coordination",
                tasks=[
                    AsanaTask(
                        name="Conduct user testing sessions",
                        description="Schedule and conduct user testing for new features",
                        completed=False,
                        due_date="2025-12-18",
                        stories=[
                            AsanaStory(
                                text="We need at least 10 participants for meaningful user testing results",
                            )
                        ],
                    ),
                    AsanaTask(
                        name="Prepare product demo presentation",
                        description="Create compelling demo presentation for stakeholders",
                        completed=False,
                        due_date="2025-12-25",
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[AsanaDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_asana_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_asana_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_mem0sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with mem0-specific data following the defined schema.
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
from klavis import Klavis, Mem0DataInput, Mem0Memory, Mem0Message

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_mem0sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=Mem0DataInput(
        memory_list=[
            Mem0Memory(
                message_list=[
                    Mem0Message(
                        role="user",
                        content="I prefer dark mode for all applications",
                    )
                ],
                agent_id="agent_assistant",
                user_id="user_001",
                app_id="settings_app",
                run_id="run_12345",
                metadata={
                    "category": "preferences",
                    "tags": ["ui", "settings"],
                },
                auto_infer=True,
                category_definitions=[
                    {
                        "ui_preferences": "Tracks user interface settings and visual preferences including themes, colors, and display options"
                    }
                ],
                background_processing=True,
            ),
            Mem0Memory(
                message_list=[
                    Mem0Message(
                        role="user",
                        content="My favorite programming language is Python",
                    ),
                    Mem0Message(
                        role="assistant",
                        content="I've noted that Python is your favorite programming language.",
                    ),
                ],
                agent_id="agent_assistant",
                user_id="user_001",
                app_id="dev_app",
                run_id="run_12346",
                metadata={
                    "category": "preferences",
                    "tags": ["programming", "development"],
                },
                auto_infer=True,
                category_definitions=[
                    {
                        "technical_skills": "Tracks programming languages, frameworks, tools and technical expertise levels"
                    }
                ],
                background_processing=True,
            ),
            Mem0Memory(
                message_list=[
                    Mem0Message(
                        role="user",
                        content="I have a meeting every Monday at 9 AM",
                    )
                ],
                agent_id="agent_calendar",
                user_id="user_001",
                app_id="calendar_app",
                run_id="run_12347",
                metadata={
                    "category": "schedule",
                    "tags": ["calendar", "recurring"],
                },
                auto_infer=True,
                category_definitions=[
                    {
                        "schedule_management": "Tracks recurring events, meetings, appointments and time commitments"
                    }
                ],
                processing_instructions="Store all calendar events with timezone information",
                background_processing=False,
            ),
            Mem0Memory(
                message_list=[
                    Mem0Message(
                        role="user",
                        content="I'm working on a machine learning project using TensorFlow",
                    )
                ],
                agent_id="agent_assistant",
                user_id="user_001",
                app_id="project_app",
                run_id="run_12348",
                metadata={
                    "category": "projects",
                    "tags": ["ml", "tensorflow", "current"],
                },
                include_preferences="project details, technologies, status",
                auto_infer=True,
                category_definitions=[
                    {
                        "project_tracking": "Tracks active and past projects including technologies used, status, and objectives"
                    }
                ],
                background_processing=True,
            ),
            Mem0Memory(
                message_list=[
                    Mem0Message(
                        role="user",
                        content="My email is user@example.com",
                    )
                ],
                agent_id="agent_assistant",
                user_id="user_001",
                app_id="contact_app",
                run_id="run_12349",
                metadata={"category": "contact", "tags": ["email", "personal"]},
                exclude_preferences="temporary contact info",
                auto_infer=False,
                category_definitions=[
                    {
                        "contact_information": "Tracks permanent contact details including email, phone numbers, and social media handles"
                    }
                ],
                read_only=True,
                background_processing=True,
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[Mem0DataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_mem0sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_mem0sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_supabase_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with supabase-specific data following the defined schema.
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
from klavis import Klavis, SupabaseDataInput, SupabaseProject, SupabaseTable

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_supabase_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=SupabaseDataInput(
        projects=[
            SupabaseProject(
                name="test-project",
                tables=[
                    SupabaseTable(
                        name="users",
                        columns={
                            "email": "TEXT",
                            "name": "TEXT",
                            "age": "INTEGER",
                            "is_active": "BOOLEAN",
                            "balance": "REAL",
                            "avatar_url": "TEXT",
                            "roles": "JSONB",
                            "metadata": "JSONB",
                            "created_at": "TEXT",
                        },
                        rows=[
                            {
                                "id": 1,
                                "email": "john@example.com",
                                "name": "John Doe",
                                "age": 30,
                                "is_active": True,
                                "balance": 1250.5,
                                "roles": ["admin", "user"],
                                "metadata": {
                                    "last_login": "2024-01-15T10:00:00Z",
                                    "login_count": 42,
                                },
                                "created_at": "2024-01-01T10:00:00Z",
                            },
                            {
                                "id": 2,
                                "email": "jane@example.com",
                                "name": "Jane Smith",
                                "age": 28,
                                "is_active": True,
                                "balance": 3500.75,
                                "avatar_url": "https://example.com/avatars/jane.jpg",
                                "roles": ["user"],
                                "metadata": {
                                    "last_login": "2024-01-16T11:30:00Z",
                                    "login_count": 156,
                                },
                                "created_at": "2024-01-02T11:30:00Z",
                            },
                            {
                                "id": 3,
                                "email": "bob@example.com",
                                "name": "Bob Johnson",
                                "age": 45,
                                "is_active": False,
                                "balance": 0,
                                "roles": ["user", "moderator"],
                                "metadata": {
                                    "last_login": "2023-12-20T09:15:00Z",
                                    "login_count": 8,
                                },
                                "created_at": "2024-01-03T09:15:00Z",
                            },
                        ],
                    ),
                    SupabaseTable(
                        name="posts",
                        columns={
                            "title": "TEXT",
                            "content": "TEXT",
                            "author_id": "INTEGER",
                            "view_count": "INTEGER",
                            "like_count": "INTEGER",
                            "is_published": "BOOLEAN",
                            "is_featured": "BOOLEAN",
                            "tags": "JSONB",
                            "rating": "REAL",
                            "settings": "JSONB",
                            "created_at": "TEXT",
                            "updated_at": "TEXT",
                        },
                        rows=[
                            {
                                "id": 101,
                                "title": "First Post",
                                "content": "This is my first post!",
                                "author_id": 1,
                                "view_count": 245,
                                "like_count": 18,
                                "is_published": True,
                                "is_featured": False,
                                "tags": ["introduction", "welcome"],
                                "rating": 4.5,
                                "settings": {
                                    "allow_comments": True,
                                    "notify_author": True,
                                },
                                "created_at": "2024-01-01T12:00:00Z",
                            },
                            {
                                "id": 102,
                                "title": "Hello World",
                                "content": "Welcome to my blog",
                                "author_id": 2,
                                "view_count": 1032,
                                "like_count": 67,
                                "is_published": True,
                                "is_featured": True,
                                "tags": ["blog", "announcement", "community"],
                                "rating": 4.8,
                                "settings": {
                                    "allow_comments": True,
                                    "notify_author": False,
                                },
                                "created_at": "2024-01-02T14:30:00Z",
                                "updated_at": "2024-01-05T09:20:00Z",
                            },
                        ],
                    ),
                ],
            ),
            SupabaseProject(
                name="analytics-project",
                tables=[
                    SupabaseTable(
                        name="events",
                        columns={
                            "event_name": "TEXT",
                            "user_id": "INTEGER",
                            "user_agent": "TEXT",
                            "duration_ms": "INTEGER",
                            "is_bot": "BOOLEAN",
                            "coordinates": "JSONB",
                            "timestamp": "TEXT",
                        },
                        rows=[
                            {
                                "id": 5001,
                                "event_name": "page_view",
                                "user_id": 1,
                                "user_agent": "Mozilla/5.0",
                                "duration_ms": 3450,
                                "is_bot": False,
                                "coordinates": {
                                    "latitude": 37.7749,
                                    "longitude": -122.4194,
                                },
                                "timestamp": "2024-01-01T08:00:00Z",
                            },
                            {
                                "id": 5002,
                                "event_name": "click",
                                "user_id": 2,
                                "user_agent": "Chrome/120.0",
                                "is_bot": False,
                                "coordinates": {
                                    "latitude": 40.7128,
                                    "longitude": -74.006,
                                },
                                "timestamp": "2024-01-01T08:15:00Z",
                            },
                        ],
                    ),
                    SupabaseTable(
                        name="metrics",
                        columns={
                            "metric_name": "TEXT",
                            "value": "INTEGER",
                            "percentage": "REAL",
                            "is_trending": "BOOLEAN",
                            "change_rate": "REAL",
                            "thresholds": "JSONB",
                            "recorded_at": "TEXT",
                        },
                        rows=[
                            {
                                "id": 1,
                                "metric_name": "total_visits",
                                "value": 1250,
                                "is_trending": True,
                                "change_rate": 15.5,
                                "thresholds": {
                                    "warning": 1000,
                                    "critical": 500,
                                },
                                "recorded_at": "2024-01-01T00:00:00Z",
                            },
                            {
                                "id": 2,
                                "metric_name": "bounce_rate",
                                "value": 35,
                                "percentage": 0.35,
                                "is_trending": False,
                                "change_rate": -2.3,
                                "thresholds": {"warning": 50, "critical": 70},
                                "recorded_at": "2024-01-01T00:00:00Z",
                            },
                            {
                                "id": 3,
                                "metric_name": "avg_session_duration",
                                "value": 180,
                                "is_trending": True,
                                "change_rate": 8.7,
                                "thresholds": {"warning": 120, "critical": 60},
                                "recorded_at": "2024-01-01T00:00:00Z",
                            },
                        ],
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[SupabaseDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_supabase_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_supabase_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_github_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with github-specific data following the defined schema.
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
from klavis import (
    GitHubBranch,
    GitHubDataInput,
    GitHubFile,
    GitHubFolder,
    GitHubIssue,
    GitHubPullRequest,
    GitHubRepo,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_github_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GitHubDataInput(
        repos=[
            GitHubRepo(
                name="test-repo",
                description="A test repository for GitHub sandbox",
                branches=[
                    GitHubBranch(
                        name="main",
                        folders=GitHubFolder(
                            name="root",
                            path="",
                            files=[
                                GitHubFile(
                                    name="README.md",
                                    path="README.md",
                                    content="# Test Repository\n\nThis is a test repository for the GitHub sandbox.\n\n## Features\n- Test files\n- Test folders\n- Sample issues and PRs",
                                )
                            ],
                        ),
                    ),
                    GitHubBranch(
                        name="feature-branch",
                        folders=GitHubFolder(
                            name="root",
                            path="",
                            files=[
                                GitHubFile(
                                    name="README.md",
                                    path="README.md",
                                    content="# Test Repository\n\nThis is a test repository for the GitHub sandbox.\n\n## Features\n- Test files\n- Test folders\n- Sample issues and PRs\n- New feature in development",
                                )
                            ],
                        ),
                    ),
                ],
                prs=[
                    GitHubPullRequest(
                        pr_title="Add new feature",
                        description="This PR adds a new feature to the repository.\n\n## Changes\n- Added new functionality\n- Updated documentation\n- Added tests",
                        status="open",
                        source_branch="feature-branch",
                        target_branch="main",
                        labels=["enhancement"],
                    )
                ],
                issues=[
                    GitHubIssue(
                        issue_title="Sample issue for testing",
                        description="This is a test issue created for GitHub sandbox testing.\n\n## Description\nWe should implement feature X.\n\n## Steps\n1. Plan the feature\n2. Implement the code\n3. Write tests",
                        status="open",
                        labels=["bug", "enhancement"],
                    )
                ],
            )
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GitHubDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_github_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_github_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_linear_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with linear-specific data following the defined schema.
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
from klavis import (
    Klavis,
    LinearComment,
    LinearDataInput,
    LinearIssue,
    LinearProject,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_linear_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=LinearDataInput(
        projects=[
            LinearProject(
                name="Q1 2024 Product Roadmap",
                description="First quarter 2024 product development roadmap",
                state="started",
                issues=[
                    LinearIssue(
                        title="Implement user authentication",
                        description="Add OAuth2 authentication flow with PKCE support",
                        priority=1,
                        state_name="In Progress",
                        comments=[
                            LinearComment(
                                body="We should use OAuth 2.0 with PKCE for better security",
                            ),
                            LinearComment(
                                body="I'll handle the backend implementation",
                            ),
                        ],
                    ),
                    LinearIssue(
                        title="Design database schema",
                        description="Create initial database schema for users and projects",
                        priority=2,
                        state_name="Done",
                        comments=[
                            LinearComment(
                                body="Schema design completed and reviewed",
                            )
                        ],
                    ),
                    LinearIssue(
                        title="Setup CI/CD pipeline",
                        description="Configure automated testing and deployment pipeline",
                        priority=3,
                        state_name="Todo",
                        comments=[
                            LinearComment(
                                body="body",
                            )
                        ],
                    ),
                    LinearIssue(
                        title="Fix login page responsiveness",
                        priority=4,
                        state_name="Backlog",
                        comments=[
                            LinearComment(
                                body="body",
                            )
                        ],
                    ),
                    LinearIssue(
                        title="Research new UI framework",
                        description="Evaluate modern UI frameworks for future migration",
                        priority=0,
                        state_name="Todo",
                        comments=[
                            LinearComment(
                                body="Looking at React, Vue, and Svelte",
                            )
                        ],
                    ),
                ],
            ),
            LinearProject(
                name="Customer Dashboard Redesign",
                state="completed",
                issues=[
                    LinearIssue(
                        title="Create wireframes for dashboard",
                        description="Design initial wireframes and mockups",
                        priority=2,
                        state_name="Done",
                        comments=[
                            LinearComment(
                                body="Wireframes approved by design team",
                            ),
                            LinearComment(
                                body="Moving to implementation phase",
                            ),
                            LinearComment(
                                body="All stakeholders signed off",
                            ),
                        ],
                    ),
                    LinearIssue(
                        title="Implement dashboard components",
                        description="Build reusable dashboard components",
                        priority=1,
                        state_name="Done",
                        comments=[
                            LinearComment(
                                body="body",
                            )
                        ],
                    ),
                    LinearIssue(
                        title="Add analytics widgets",
                        priority=2,
                        state_name="Done",
                        comments=[
                            LinearComment(
                                body="Integrated with analytics API",
                            )
                        ],
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[LinearDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_linear_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_linear_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_notion_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with notion-specific data following the defined schema.
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
from klavis import (
    Klavis,
    NotionBlock,
    NotionComment,
    NotionDatabase,
    NotionDataInput,
    NotionDataSource,
    NotionPage,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_notion_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=NotionDataInput(
        databases=[
            NotionDatabase(
                name="Product Roadmap",
                summary="Track product features and releases",
                display_icon="🚀",
                sources=[
                    NotionDataSource(
                        label="Features",
                        summary="Feature tracking table",
                        fields={
                            "Name": {"type": "title"},
                            "Status": {
                                "type": "select",
                                "options": ["Planning", "In Progress", "Done"],
                            },
                            "Priority": {
                                "type": "select",
                                "options": ["High", "Medium", "Low"],
                            },
                            "Assignee": {"type": "people"},
                        },
                        pages=[
                            NotionPage(
                                name="User Authentication",
                                attributes={
                                    "Status": "Done",
                                    "Priority": "High",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Implement secure user authentication with OAuth2 support",
                                    ),
                                    NotionBlock(
                                        block_type="heading_2",
                                        content="Requirements",
                                    ),
                                    NotionBlock(
                                        block_type="bulleted_list_item",
                                        content="Support email/password login",
                                    ),
                                    NotionBlock(
                                        block_type="bulleted_list_item",
                                        content="Implement JWT tokens",
                                    ),
                                    NotionBlock(
                                        block_type="bulleted_list_item",
                                        content="Add OAuth2 providers (Google, GitHub)",
                                    ),
                                ],
                                comments=[
                                    NotionComment(
                                        content="Should we support social login from day one?",
                                    ),
                                    NotionComment(
                                        content="Yes, let's add Google and GitHub OAuth",
                                    ),
                                ],
                            ),
                            NotionPage(
                                name="Real-time Notifications",
                                attributes={
                                    "Status": "In Progress",
                                    "Priority": "High",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Build real-time notification system using WebSockets",
                                    ),
                                    NotionBlock(
                                        block_type="to_do",
                                        content="Set up WebSocket server",
                                    ),
                                    NotionBlock(
                                        block_type="to_do",
                                        content="Create notification service",
                                    ),
                                    NotionBlock(
                                        block_type="to_do",
                                        content="Design notification UI components",
                                    ),
                                ],
                                comments=[
                                    NotionComment(
                                        content="content",
                                    )
                                ],
                            ),
                            NotionPage(
                                name="Dark Mode Support",
                                attributes={
                                    "Status": "Planning",
                                    "Priority": "Medium",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Add dark mode theme toggle",
                                    ),
                                    NotionBlock(
                                        block_type="callout",
                                        content="💡 Consider using CSS variables for easy theme switching",
                                    ),
                                ],
                                comments=[
                                    NotionComment(
                                        content="Users have been requesting this feature frequently",
                                    )
                                ],
                            ),
                        ],
                    ),
                    NotionDataSource(
                        label="Releases",
                        summary="Release planning and tracking",
                        fields={
                            "Name": {"type": "title"},
                            "Release Date": {"type": "date"},
                            "Status": {
                                "type": "select",
                                "options": [
                                    "Planned",
                                    "In Development",
                                    "Released",
                                ],
                            },
                        },
                        pages=[
                            NotionPage(
                                name="v1.0 - MVP Release",
                                attributes={
                                    "Release Date": "2024-03-15",
                                    "Status": "In Development",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="heading_2",
                                        content="Release Goals",
                                    ),
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="First production-ready version with core functionality",
                                    ),
                                    NotionBlock(
                                        block_type="numbered_list_item",
                                        content="User authentication and authorization",
                                    ),
                                    NotionBlock(
                                        block_type="numbered_list_item",
                                        content="Real-time notifications",
                                    ),
                                    NotionBlock(
                                        block_type="numbered_list_item",
                                        content="Core API endpoints",
                                    ),
                                ],
                                comments=[
                                    NotionComment(
                                        content="content",
                                    )
                                ],
                            ),
                            NotionPage(
                                name="v1.1 - Enhanced UX",
                                attributes={
                                    "Release Date": "2024-04-30",
                                    "Status": "Planned",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Focus on user experience improvements",
                                    )
                                ],
                                comments=[
                                    NotionComment(
                                        content="content",
                                    )
                                ],
                            ),
                        ],
                    ),
                ],
            ),
            NotionDatabase(
                name="Team Tasks",
                summary="Daily task management for the team",
                display_icon="✅",
                sources=[
                    NotionDataSource(
                        label="Tasks",
                        summary="Task tracking",
                        fields={
                            "Task": {"type": "title"},
                            "Status": {"type": "status"},
                            "Assignee": {"type": "people"},
                            "Due Date": {"type": "date"},
                            "Priority": {
                                "type": "select",
                                "options": ["High", "Medium", "Low"],
                            },
                        },
                        pages=[
                            NotionPage(
                                name="Review pull request #123",
                                attributes={
                                    "Status": "In Progress",
                                    "Priority": "High",
                                    "Due Date": "2024-02-10",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Review authentication implementation PR",
                                    ),
                                    NotionBlock(
                                        block_type="code",
                                        content="// Check for proper error handling and security best practices",
                                    ),
                                ],
                                comments=[
                                    NotionComment(
                                        content="Found a potential security issue in token validation",
                                    ),
                                    NotionComment(
                                        content="Fixed in latest commit",
                                    ),
                                ],
                            ),
                            NotionPage(
                                name="Update deployment documentation",
                                attributes={
                                    "Status": "Todo",
                                    "Priority": "Medium",
                                    "Due Date": "2024-02-15",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Add new deployment steps for Docker setup",
                                    )
                                ],
                                comments=[
                                    NotionComment(
                                        content="content",
                                    )
                                ],
                            ),
                            NotionPage(
                                name="Fix responsive layout on mobile",
                                attributes={
                                    "Status": "Done",
                                    "Priority": "High",
                                    "Due Date": "2024-02-08",
                                },
                                content_blocks=[
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Navigation menu was broken on screens < 768px",
                                    ),
                                    NotionBlock(
                                        block_type="heading_3",
                                        content="Solution",
                                    ),
                                    NotionBlock(
                                        block_type="paragraph",
                                        content="Implemented hamburger menu for mobile devices",
                                    ),
                                ],
                                comments=[
                                    NotionComment(
                                        content="Tested on iPhone and Android devices, looks good!",
                                    )
                                ],
                            ),
                        ],
                    )
                ],
            ),
        ],
        pages=[
            NotionPage(
                name="Team Meeting Notes - Feb 2024",
                content_blocks=[
                    NotionBlock(
                        block_type="heading_1",
                        content="Weekly Sync - February 5, 2024",
                    ),
                    NotionBlock(
                        block_type="paragraph",
                        content="Attendees: Alice, Bob, Charlie, Diana",
                    ),
                    NotionBlock(
                        block_type="heading_2",
                        content="Discussion Points",
                    ),
                    NotionBlock(
                        block_type="bulleted_list_item",
                        content="Sprint retrospective review",
                    ),
                    NotionBlock(
                        block_type="bulleted_list_item",
                        content="Q1 roadmap planning",
                    ),
                    NotionBlock(
                        block_type="bulleted_list_item",
                        content="New hire onboarding process",
                    ),
                    NotionBlock(
                        block_type="heading_2",
                        content="Action Items",
                    ),
                    NotionBlock(
                        block_type="to_do",
                        content="Alice: Schedule 1-on-1s with new team members",
                    ),
                    NotionBlock(
                        block_type="to_do",
                        content="Bob: Update API documentation",
                    ),
                    NotionBlock(
                        block_type="to_do",
                        content="Charlie: Review security audit findings",
                    ),
                ],
                comments=[
                    NotionComment(
                        content="Great meeting! Let's make sure we follow up on action items by Friday",
                    ),
                    NotionComment(
                        content="Added calendar invites for the 1-on-1s",
                    ),
                ],
            ),
            NotionPage(
                name="Engineering Wiki Home",
                content_blocks=[
                    NotionBlock(
                        block_type="heading_1",
                        content="Welcome to Engineering Wiki",
                    ),
                    NotionBlock(
                        block_type="paragraph",
                        content="This wiki contains all technical documentation, guides, and best practices for our engineering team.",
                    ),
                    NotionBlock(
                        block_type="heading_2",
                        content="Quick Links",
                    ),
                    NotionBlock(
                        block_type="bulleted_list_item",
                        content="Getting Started Guide",
                    ),
                    NotionBlock(
                        block_type="bulleted_list_item",
                        content="API Documentation",
                    ),
                    NotionBlock(
                        block_type="bulleted_list_item",
                        content="Architecture Overview",
                    ),
                    NotionBlock(
                        block_type="bulleted_list_item",
                        content="Deployment Procedures",
                    ),
                    NotionBlock(
                        block_type="heading_2",
                        content="Code of Conduct",
                    ),
                    NotionBlock(
                        block_type="quote",
                        content="Write code that is clear, maintainable, and well-tested. When in doubt, prioritize readability over cleverness.",
                    ),
                ],
                comments=[
                    NotionComment(
                        content="content",
                    )
                ],
            ),
            NotionPage(
                name="API Design Guidelines",
                content_blocks=[
                    NotionBlock(
                        block_type="heading_1",
                        content="REST API Design Guidelines",
                    ),
                    NotionBlock(
                        block_type="paragraph",
                        content="Follow these guidelines when designing new API endpoints",
                    ),
                    NotionBlock(
                        block_type="heading_2",
                        content="General Principles",
                    ),
                    NotionBlock(
                        block_type="numbered_list_item",
                        content="Use RESTful conventions (GET, POST, PUT, DELETE)",
                    ),
                    NotionBlock(
                        block_type="numbered_list_item",
                        content="Use plural nouns for resource names",
                    ),
                    NotionBlock(
                        block_type="numbered_list_item",
                        content="Version your APIs (e.g., /v1/users)",
                    ),
                    NotionBlock(
                        block_type="numbered_list_item",
                        content="Use HTTP status codes correctly",
                    ),
                    NotionBlock(
                        block_type="heading_2",
                        content="Example",
                    ),
                    NotionBlock(
                        block_type="code",
                        content="GET /v1/users - List all users\nGET /v1/users/:id - Get specific user\nPOST /v1/users - Create new user\nPUT /v1/users/:id - Update user\nDELETE /v1/users/:id - Delete user",
                    ),
                    NotionBlock(
                        block_type="callout",
                        content="⚠️ Always validate input data and sanitize user-provided content",
                    ),
                ],
                comments=[
                    NotionComment(
                        content="Should we use GraphQL for more complex queries?",
                    ),
                    NotionComment(
                        content="Let's discuss in next architecture meeting",
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[NotionDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_notion_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_notion_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_slack_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with slack-specific data following the defined schema.
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
from klavis import (
    Klavis,
    SlackChannel,
    SlackDataInput,
    SlackMessage,
    SlackReaction,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_slack_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=SlackDataInput(
        channels=[
            SlackChannel(
                name="sandbox-test",
                description="Company-wide announcements and work-based matters",
                is_private=False,
                messages=[
                    SlackMessage(
                        text="Welcome to the new Slack workspace!",
                        reactions=[
                            SlackReaction(
                                name="wave",
                            ),
                            SlackReaction(
                                name="tada",
                            ),
                        ],
                    ),
                    SlackMessage(
                        text="Thanks! Excited to be here.",
                        reactions=[
                            SlackReaction(
                                name="+1",
                            )
                        ],
                    ),
                ],
            ),
            SlackChannel(
                name="project-alpha",
                description="Discussion for Project Alpha",
                is_private=False,
                messages=[
                    SlackMessage(
                        text="Has anyone seen the latest specs?",
                        reactions=[
                            SlackReaction(
                                name="name",
                            )
                        ],
                    ),
                    SlackMessage(
                        text="Here are the project specs...",
                        reactions=[
                            SlackReaction(
                                name="rocket",
                            )
                        ],
                    ),
                ],
            ),
            SlackChannel(
                name="sandbox-test-private",
                description="Top secret stuff",
                is_private=True,
                messages=[
                    SlackMessage(
                        text="This is confidential information",
                        reactions=[
                            SlackReaction(
                                name="shushing_face",
                            )
                        ],
                    )
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[SlackDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_slack_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_slack_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_confluence_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with confluence-specific data following the defined schema.
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
from klavis import (
    ConfluenceComment,
    ConfluenceDataInput,
    ConfluencePage,
    ConfluenceSpace,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_confluence_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=ConfluenceDataInput(
        spaces=[
            ConfluenceSpace(
                identifier="TEAM",
                name="Team Space",
                description="Space for team collaboration",
                pages=[
                    ConfluencePage(
                        title="Welcome to the Team",
                        content="<p>This is the home page for our team.</p>",
                        comments=[
                            ConfluenceComment(
                                content="<p>Great start!</p>",
                            )
                        ],
                    )
                ],
            ),
            ConfluenceSpace(
                identifier="DOCS",
                name="Documentation",
                description="Product documentation",
                pages=[
                    ConfluencePage(
                        title="Getting Started",
                        content="<p>How to use the product.</p>",
                    )
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[ConfluenceDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_confluence_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_confluence_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_discord_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with discord-specific data following the defined schema.
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
from klavis import (
    DiscordChannel,
    DiscordDataInput,
    DiscordMessage,
    DiscordReaction,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_discord_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=DiscordDataInput(
        channels=[
            DiscordChannel(
                messages=[
                    DiscordMessage(
                        content="Welcome to the Discord sandbox test!",
                        reactions=[
                            DiscordReaction(
                                name="👋",
                            ),
                            DiscordReaction(
                                name="🎉",
                            ),
                        ],
                    ),
                    DiscordMessage(
                        content="This is the second test message.",
                        reactions=[
                            DiscordReaction(
                                name="👍",
                            )
                        ],
                    ),
                    DiscordMessage(
                        content="Message without reactions for testing.",
                        reactions=[
                            DiscordReaction(
                                name="name",
                            )
                        ],
                    ),
                ],
            )
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[DiscordDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_discord_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_discord_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_airtable_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with airtable-specific data following the defined schema.
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
from klavis import (
    AirtableDataInput,
    AirtableField,
    AirtableRecord,
    AirtableTable,
    Klavis,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_airtable_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=AirtableDataInput(
        tables=[
            AirtableTable(
                name="Projects",
                description="Track all projects and their details",
                fields=[
                    AirtableField(
                        name="Name",
                        type="singleLineText",
                    ),
                    AirtableField(
                        name="Status",
                        type="singleSelect",
                        options={
                            "choices": [
                                {"name": "Planning"},
                                {"name": "In Progress"},
                                {"name": "On Hold"},
                                {"name": "Completed"},
                            ]
                        },
                    ),
                    AirtableField(
                        name="Description",
                        type="multilineText",
                    ),
                    AirtableField(
                        name="Start Date",
                        type="date",
                    ),
                    AirtableField(
                        name="Due Date",
                        type="date",
                    ),
                    AirtableField(
                        name="Budget",
                        type="number",
                    ),
                    AirtableField(
                        name="Priority",
                        type="singleSelect",
                        options={
                            "choices": [
                                {"name": "High"},
                                {"name": "Medium"},
                                {"name": "Low"},
                            ]
                        },
                    ),
                    AirtableField(
                        name="Tasks",
                        type="multipleRecordLinks",
                    ),
                ],
                records=[
                    AirtableRecord(
                        fields={
                            "Name": "Website Redesign",
                            "Status": "In Progress",
                            "Description": "Complete overhaul of company website with modern design and improved UX",
                            "Start Date": "2024-01-15",
                            "Due Date": "2024-03-30",
                            "Budget": 50000,
                            "Priority": "High",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Name": "Mobile App Development",
                            "Status": "Planning",
                            "Description": "Develop iOS and Android mobile applications for customer engagement",
                            "Start Date": "2024-02-01",
                            "Due Date": "2024-06-30",
                            "Budget": 120000,
                            "Priority": "High",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Name": "Marketing Campaign Q1",
                            "Status": "In Progress",
                            "Description": "Launch social media and email marketing campaign for Q1",
                            "Start Date": "2024-01-01",
                            "Due Date": "2024-03-31",
                            "Budget": 25000,
                            "Priority": "Medium",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Name": "Infrastructure Upgrade",
                            "Status": "Planning",
                            "Description": "Upgrade cloud infrastructure and migrate to Kubernetes",
                            "Start Date": "2024-03-01",
                            "Due Date": "2024-05-31",
                            "Budget": 75000,
                            "Priority": "High",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Name": "Customer Support Portal",
                            "Status": "On Hold",
                            "Description": "Build self-service customer support portal with knowledge base",
                            "Start Date": "2024-01-20",
                            "Due Date": "2024-04-30",
                            "Budget": 30000,
                            "Priority": "Low",
                        },
                    ),
                ],
            ),
            AirtableTable(
                name="Tasks",
                description="Individual tasks and action items",
                fields=[
                    AirtableField(
                        name="Task Name",
                        type="singleLineText",
                    ),
                    AirtableField(
                        name="Description",
                        type="multilineText",
                    ),
                    AirtableField(
                        name="Status",
                        type="singleSelect",
                        options={
                            "choices": [
                                {"name": "To Do"},
                                {"name": "In Progress"},
                                {"name": "Review"},
                                {"name": "Done"},
                            ]
                        },
                    ),
                    AirtableField(
                        name="Assignee",
                        type="singleLineText",
                    ),
                    AirtableField(
                        name="Due Date",
                        type="date",
                    ),
                    AirtableField(
                        name="Priority",
                        type="singleSelect",
                        options={
                            "choices": [
                                {"name": "Critical"},
                                {"name": "High"},
                                {"name": "Medium"},
                                {"name": "Low"},
                            ]
                        },
                    ),
                    AirtableField(
                        name="Estimated Hours",
                        type="number",
                    ),
                    AirtableField(
                        name="Completed",
                        type="checkbox",
                    ),
                    AirtableField(
                        name="Project",
                        type="multipleRecordLinks",
                    ),
                ],
                records=[
                    AirtableRecord(
                        fields={
                            "Task Name": "Design homepage mockup",
                            "Description": "Create high-fidelity mockups for the new homepage layout",
                            "Status": "In Progress",
                            "Assignee": "Sarah Johnson",
                            "Due Date": "2024-02-15",
                            "Priority": "High",
                            "Estimated Hours": 16,
                            "Completed": False,
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Task Name": "Set up development environment",
                            "Description": "Configure local dev environment with all necessary tools",
                            "Status": "Done",
                            "Assignee": "Mike Chen",
                            "Due Date": "2024-01-20",
                            "Priority": "High",
                            "Estimated Hours": 8,
                            "Completed": True,
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Task Name": "Conduct user research",
                            "Description": "Interview 20 users about their needs and pain points",
                            "Status": "In Progress",
                            "Assignee": "Emily Rodriguez",
                            "Due Date": "2024-02-28",
                            "Priority": "Medium",
                            "Estimated Hours": 40,
                            "Completed": False,
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Task Name": "Write API documentation",
                            "Description": "Document all API endpoints with examples and parameters",
                            "Status": "To Do",
                            "Assignee": "David Lee",
                            "Due Date": "2024-03-10",
                            "Priority": "Medium",
                            "Estimated Hours": 24,
                            "Completed": False,
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Task Name": "Implement authentication system",
                            "Description": "Build OAuth2 authentication with JWT tokens",
                            "Status": "In Progress",
                            "Assignee": "Mike Chen",
                            "Due Date": "2024-02-25",
                            "Priority": "Critical",
                            "Estimated Hours": 32,
                            "Completed": False,
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Task Name": "Create social media content calendar",
                            "Description": "Plan content for Twitter, LinkedIn, and Instagram for Q1",
                            "Status": "Review",
                            "Assignee": "Amanda White",
                            "Due Date": "2024-02-05",
                            "Priority": "High",
                            "Estimated Hours": 12,
                            "Completed": False,
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Task Name": "Deploy staging environment",
                            "Description": "Set up staging server for QA testing",
                            "Status": "Done",
                            "Assignee": "Robert Garcia",
                            "Due Date": "2024-01-25",
                            "Priority": "High",
                            "Estimated Hours": 6,
                            "Completed": True,
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Task Name": "Database schema design",
                            "Description": "Design normalized database schema for new features",
                            "Status": "Review",
                            "Assignee": "David Lee",
                            "Due Date": "2024-02-10",
                            "Priority": "Critical",
                            "Estimated Hours": 20,
                            "Completed": False,
                        },
                    ),
                ],
            ),
            AirtableTable(
                name="Team Members",
                description="Team directory with contact information",
                fields=[
                    AirtableField(
                        name="Full Name",
                        type="singleLineText",
                    ),
                    AirtableField(
                        name="Email",
                        type="email",
                    ),
                    AirtableField(
                        name="Phone",
                        type="phoneNumber",
                    ),
                    AirtableField(
                        name="Role",
                        type="singleSelect",
                        options={
                            "choices": [
                                {"name": "Developer"},
                                {"name": "Designer"},
                                {"name": "Product Manager"},
                                {"name": "Marketing"},
                                {"name": "DevOps"},
                            ]
                        },
                    ),
                    AirtableField(
                        name="Department",
                        type="singleSelect",
                        options={
                            "choices": [
                                {"name": "Engineering"},
                                {"name": "Design"},
                                {"name": "Product"},
                                {"name": "Marketing"},
                                {"name": "Operations"},
                            ]
                        },
                    ),
                    AirtableField(
                        name="Start Date",
                        type="date",
                    ),
                    AirtableField(
                        name="Active",
                        type="checkbox",
                    ),
                    AirtableField(
                        name="Profile Picture",
                        type="url",
                    ),
                ],
                records=[
                    AirtableRecord(
                        fields={
                            "Full Name": "Sarah Johnson",
                            "Email": "sarah.johnson@example.com",
                            "Phone": "+1-555-0101",
                            "Role": "Designer",
                            "Department": "Design",
                            "Start Date": "2022-03-15",
                            "Active": True,
                            "Profile Picture": "https://i.pravatar.cc/150?img=1",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Full Name": "Mike Chen",
                            "Email": "mike.chen@example.com",
                            "Phone": "+1-555-0102",
                            "Role": "Developer",
                            "Department": "Engineering",
                            "Start Date": "2021-06-01",
                            "Active": True,
                            "Profile Picture": "https://i.pravatar.cc/150?img=13",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Full Name": "Emily Rodriguez",
                            "Email": "emily.rodriguez@example.com",
                            "Phone": "+1-555-0103",
                            "Role": "Product Manager",
                            "Department": "Product",
                            "Start Date": "2020-09-10",
                            "Active": True,
                            "Profile Picture": "https://i.pravatar.cc/150?img=5",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Full Name": "David Lee",
                            "Email": "david.lee@example.com",
                            "Phone": "+1-555-0104",
                            "Role": "Developer",
                            "Department": "Engineering",
                            "Start Date": "2023-01-20",
                            "Active": True,
                            "Profile Picture": "https://i.pravatar.cc/150?img=12",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Full Name": "Amanda White",
                            "Email": "amanda.white@example.com",
                            "Phone": "+1-555-0105",
                            "Role": "Marketing",
                            "Department": "Marketing",
                            "Start Date": "2022-11-05",
                            "Active": True,
                            "Profile Picture": "https://i.pravatar.cc/150?img=10",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Full Name": "Robert Garcia",
                            "Email": "robert.garcia@example.com",
                            "Phone": "+1-555-0106",
                            "Role": "DevOps",
                            "Department": "Operations",
                            "Start Date": "2021-02-28",
                            "Active": True,
                            "Profile Picture": "https://i.pravatar.cc/150?img=15",
                        },
                    ),
                ],
            ),
            AirtableTable(
                name="Meetings",
                description="Schedule and track team meetings",
                fields=[
                    AirtableField(
                        name="Meeting Title",
                        type="singleLineText",
                    ),
                    AirtableField(
                        name="Date",
                        type="date",
                    ),
                    AirtableField(
                        name="Duration (minutes)",
                        type="number",
                    ),
                    AirtableField(
                        name="Type",
                        type="singleSelect",
                        options={
                            "choices": [
                                {"name": "Stand-up"},
                                {"name": "Planning"},
                                {"name": "Review"},
                                {"name": "Retrospective"},
                                {"name": "One-on-One"},
                            ]
                        },
                    ),
                    AirtableField(
                        name="Attendees",
                        type="multilineText",
                    ),
                    AirtableField(
                        name="Notes",
                        type="multilineText",
                    ),
                    AirtableField(
                        name="Action Items",
                        type="multilineText",
                    ),
                    AirtableField(
                        name="Recording URL",
                        type="url",
                    ),
                ],
                records=[
                    AirtableRecord(
                        fields={
                            "Meeting Title": "Weekly Team Stand-up",
                            "Date": "2024-02-05",
                            "Duration (minutes)": 30,
                            "Type": "Stand-up",
                            "Attendees": "Sarah, Mike, Emily, David, Amanda, Robert",
                            "Notes": "Discussed progress on current sprint. Team velocity is good. No major blockers.",
                            "Action Items": "- Mike to review David's PR\n- Sarah to finalize designs by EOD\n- Emily to schedule client demo",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Meeting Title": "Sprint Planning - Sprint 5",
                            "Date": "2024-02-01",
                            "Duration (minutes)": 120,
                            "Type": "Planning",
                            "Attendees": "All team members",
                            "Notes": "Planned 25 story points for the upcoming sprint. Focus on authentication and API development.",
                            "Action Items": "- Break down epic into smaller tasks\n- Update story estimates\n- Assign tasks to team members",
                            "Recording URL": "https://zoom.us/rec/example123",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Meeting Title": "Design Review - Homepage",
                            "Date": "2024-02-03",
                            "Duration (minutes)": 60,
                            "Type": "Review",
                            "Attendees": "Sarah, Emily, Mike",
                            "Notes": "Reviewed new homepage designs. Overall positive feedback. Some minor adjustments needed.",
                            "Action Items": "- Sarah to update color palette\n- Increase font size for headings\n- Add more whitespace in hero section",
                        },
                    ),
                    AirtableRecord(
                        fields={
                            "Meeting Title": "1:1 - Emily & Mike",
                            "Date": "2024-02-02",
                            "Duration (minutes)": 30,
                            "Type": "One-on-One",
                            "Attendees": "Emily, Mike",
                            "Notes": "Discussed career growth and upcoming projects. Mike interested in learning more about system architecture.",
                            "Action Items": "- Emily to share architecture resources\n- Mike to shadow senior architect next month",
                        },
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[AirtableDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_airtable_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_airtable_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_snowflake_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with snowflake-specific data following the defined schema.
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
from klavis import (
    Klavis,
    SnowflakeColumn,
    SnowflakeDatabase,
    SnowflakeDataInput,
    SnowflakeRow,
    SnowflakeSchema,
    SnowflakeTable,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_snowflake_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=SnowflakeDataInput(
        databases=[
            SnowflakeDatabase(
                name="SANDBOX_DB",
                description="Main sandbox database for testing and development",
                schemas=[
                    SnowflakeSchema(
                        name="SALES",
                        tables=[
                            SnowflakeTable(
                                name="CUSTOMERS",
                                columns=[
                                    SnowflakeColumn(
                                        name="CUSTOMER_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="FIRST_NAME",
                                        data_type="VARCHAR(100)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="LAST_NAME",
                                        data_type="VARCHAR(100)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="EMAIL",
                                        data_type="VARCHAR(255)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="COUNTRY",
                                        data_type="VARCHAR(100)",
                                        nullable=True,
                                    ),
                                    SnowflakeColumn(
                                        name="CREATED_AT",
                                        data_type="TIMESTAMP_NTZ(9)",
                                        nullable=True,
                                        default_value="CURRENT_TIMESTAMP()",
                                    ),
                                ],
                                rows=[
                                    SnowflakeRow(
                                        values={
                                            "CUSTOMER_ID": 1,
                                            "FIRST_NAME": "John",
                                            "LAST_NAME": "Doe",
                                            "EMAIL": "john.doe@example.com",
                                            "COUNTRY": "USA",
                                            "CREATED_AT": "2024-01-15T09:00:00",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "CUSTOMER_ID": 2,
                                            "FIRST_NAME": "Jane",
                                            "LAST_NAME": "Smith",
                                            "EMAIL": "jane.smith@example.com",
                                            "COUNTRY": "Canada",
                                            "CREATED_AT": "2024-01-15T09:05:00",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "CUSTOMER_ID": 3,
                                            "FIRST_NAME": "Bob",
                                            "LAST_NAME": "Johnson",
                                            "EMAIL": "bob.johnson@example.com",
                                            "COUNTRY": "UK",
                                            "CREATED_AT": "2024-01-15T09:10:00",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "CUSTOMER_ID": 4,
                                            "FIRST_NAME": "Alice",
                                            "LAST_NAME": "Williams",
                                            "EMAIL": "alice.williams@example.com",
                                            "COUNTRY": "Australia",
                                            "CREATED_AT": "2024-01-15T09:15:00",
                                        },
                                    ),
                                ],
                            ),
                            SnowflakeTable(
                                name="ORDERS",
                                columns=[
                                    SnowflakeColumn(
                                        name="ORDER_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="CUSTOMER_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="ORDER_DATE",
                                        data_type="DATE",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="TOTAL_AMOUNT",
                                        data_type="NUMBER(10,2)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="STATUS",
                                        data_type="VARCHAR(50)",
                                        nullable=False,
                                    ),
                                ],
                                rows=[
                                    SnowflakeRow(
                                        values={
                                            "ORDER_ID": 1001,
                                            "CUSTOMER_ID": 1,
                                            "ORDER_DATE": "2024-01-15",
                                            "TOTAL_AMOUNT": "250.50",
                                            "STATUS": "COMPLETED",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "ORDER_ID": 1002,
                                            "CUSTOMER_ID": 2,
                                            "ORDER_DATE": "2024-01-16",
                                            "TOTAL_AMOUNT": "175.25",
                                            "STATUS": "SHIPPED",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "ORDER_ID": 1003,
                                            "CUSTOMER_ID": 1,
                                            "ORDER_DATE": "2024-01-17",
                                            "TOTAL_AMOUNT": "399.99",
                                            "STATUS": "PROCESSING",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "ORDER_ID": 1004,
                                            "CUSTOMER_ID": 3,
                                            "ORDER_DATE": "2024-01-18",
                                            "TOTAL_AMOUNT": "89.99",
                                            "STATUS": "COMPLETED",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "ORDER_ID": 1005,
                                            "CUSTOMER_ID": 4,
                                            "ORDER_DATE": "2024-01-19",
                                            "TOTAL_AMOUNT": "450.00",
                                            "STATUS": "PENDING",
                                        },
                                    ),
                                ],
                            ),
                            SnowflakeTable(
                                name="PRODUCTS",
                                columns=[
                                    SnowflakeColumn(
                                        name="PRODUCT_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="PRODUCT_NAME",
                                        data_type="VARCHAR(200)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="CATEGORY",
                                        data_type="VARCHAR(100)",
                                        nullable=True,
                                    ),
                                    SnowflakeColumn(
                                        name="PRICE",
                                        data_type="NUMBER(10,2)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="IN_STOCK",
                                        data_type="BOOLEAN",
                                        nullable=False,
                                        default_value="TRUE",
                                    ),
                                ],
                                rows=[
                                    SnowflakeRow(
                                        values={
                                            "PRODUCT_ID": 101,
                                            "PRODUCT_NAME": "Laptop Pro 15",
                                            "CATEGORY": "Electronics",
                                            "PRICE": "1299.99",
                                            "IN_STOCK": True,
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "PRODUCT_ID": 102,
                                            "PRODUCT_NAME": "Wireless Mouse",
                                            "CATEGORY": "Electronics",
                                            "PRICE": "29.99",
                                            "IN_STOCK": True,
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "PRODUCT_ID": 103,
                                            "PRODUCT_NAME": "Office Chair",
                                            "CATEGORY": "Furniture",
                                            "PRICE": "249.99",
                                            "IN_STOCK": False,
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "PRODUCT_ID": 104,
                                            "PRODUCT_NAME": "Desk Lamp",
                                            "CATEGORY": "Furniture",
                                            "PRICE": "45.00",
                                            "IN_STOCK": True,
                                        },
                                    ),
                                ],
                            ),
                        ],
                    ),
                    SnowflakeSchema(
                        name="ANALYTICS",
                        tables=[
                            SnowflakeTable(
                                name="SALES_METRICS",
                                columns=[
                                    SnowflakeColumn(
                                        name="METRIC_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="METRIC_DATE",
                                        data_type="DATE",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="REVENUE",
                                        data_type="NUMBER(12,2)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="ORDERS_COUNT",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="AVG_ORDER_VALUE",
                                        data_type="NUMBER(10,2)",
                                        nullable=False,
                                    ),
                                ],
                                rows=[
                                    SnowflakeRow(
                                        values={
                                            "METRIC_ID": 1,
                                            "METRIC_DATE": "2024-01-15",
                                            "REVENUE": "250.50",
                                            "ORDERS_COUNT": 1,
                                            "AVG_ORDER_VALUE": "250.50",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "METRIC_ID": 2,
                                            "METRIC_DATE": "2024-01-16",
                                            "REVENUE": "175.25",
                                            "ORDERS_COUNT": 1,
                                            "AVG_ORDER_VALUE": "175.25",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "METRIC_ID": 3,
                                            "METRIC_DATE": "2024-01-17",
                                            "REVENUE": "399.99",
                                            "ORDERS_COUNT": 1,
                                            "AVG_ORDER_VALUE": "399.99",
                                        },
                                    ),
                                ],
                            ),
                            SnowflakeTable(
                                name="USER_ACTIVITY",
                                columns=[
                                    SnowflakeColumn(
                                        name="ACTIVITY_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="USER_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="ACTIVITY_TYPE",
                                        data_type="VARCHAR(100)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="ACTIVITY_TIMESTAMP",
                                        data_type="TIMESTAMP_NTZ(9)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="METADATA",
                                        data_type="VARIANT",
                                        nullable=True,
                                    ),
                                ],
                                rows=[
                                    SnowflakeRow(
                                        values={
                                            "ACTIVITY_ID": 1,
                                            "USER_ID": 1,
                                            "ACTIVITY_TYPE": "LOGIN",
                                            "ACTIVITY_TIMESTAMP": "2024-01-15T08:30:00",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "ACTIVITY_ID": 2,
                                            "USER_ID": 1,
                                            "ACTIVITY_TYPE": "PURCHASE",
                                            "ACTIVITY_TIMESTAMP": "2024-01-15T10:45:00",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "ACTIVITY_ID": 3,
                                            "USER_ID": 2,
                                            "ACTIVITY_TYPE": "LOGIN",
                                            "ACTIVITY_TIMESTAMP": "2024-01-16T09:15:00",
                                        },
                                    ),
                                ],
                            ),
                        ],
                    ),
                ],
            ),
            SnowflakeDatabase(
                name="TEST_DB",
                description="Secondary database for integration testing",
                schemas=[
                    SnowflakeSchema(
                        name="OBSERVATION",
                        tables=[
                            SnowflakeTable(
                                name="TEST_LOGS",
                                columns=[
                                    SnowflakeColumn(
                                        name="LOG_ID",
                                        data_type="NUMBER(38,0)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="LOG_MESSAGE",
                                        data_type="VARCHAR(1000)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="LOG_LEVEL",
                                        data_type="VARCHAR(20)",
                                        nullable=False,
                                    ),
                                    SnowflakeColumn(
                                        name="CREATED_AT",
                                        data_type="TIMESTAMP_NTZ(9)",
                                        nullable=False,
                                    ),
                                ],
                                rows=[
                                    SnowflakeRow(
                                        values={
                                            "LOG_ID": 1,
                                            "LOG_MESSAGE": "Application started successfully",
                                            "LOG_LEVEL": "INFO",
                                            "CREATED_AT": "2024-01-15T08:00:00",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "LOG_ID": 2,
                                            "LOG_MESSAGE": "Database connection established",
                                            "LOG_LEVEL": "INFO",
                                            "CREATED_AT": "2024-01-15T08:00:05",
                                        },
                                    ),
                                    SnowflakeRow(
                                        values={
                                            "LOG_ID": 3,
                                            "LOG_MESSAGE": "Warning: High memory usage detected",
                                            "LOG_LEVEL": "WARNING",
                                            "CREATED_AT": "2024-01-15T10:30:00",
                                        },
                                    ),
                                ],
                            )
                        ],
                    )
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[SnowflakeDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_snowflake_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_snowflake_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_google_cloud_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with google_cloud-specific data following the defined schema.
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
from klavis import (
    BigQueryDataset,
    BigQueryField,
    BigQueryTable,
    ComputeInstance,
    GoogleCloudDataInput,
    Klavis,
    LifecycleRule,
    LogBucket,
    LogEntry,
    LogSink,
    StorageBucket,
    StorageObject,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_google_cloud_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=GoogleCloudDataInput(
        datasets=[
            BigQueryDataset(
                id="sales_analytics",
                description="Sales and revenue analytics data warehouse",
                location="US",
            ),
            BigQueryDataset(
                id="customer_data",
                description="Customer information and interactions",
                location="US",
            ),
            BigQueryDataset(
                id="product_catalog",
                description="Product inventory and catalog data",
                location="EU",
            ),
        ],
        tables=[
            BigQueryTable(
                dataset_id="sales_analytics",
                id="daily_sales",
                description="Daily sales transactions",
                fields=[
                    BigQueryField(
                        name="transaction_id",
                        type="STRING",
                        mode="REQUIRED",
                        description="Unique transaction identifier",
                    ),
                    BigQueryField(
                        name="sale_date",
                        type="DATE",
                        mode="REQUIRED",
                        description="Date of sale",
                    ),
                    BigQueryField(
                        name="product_id",
                        type="STRING",
                        mode="REQUIRED",
                        description="Product identifier",
                    ),
                    BigQueryField(
                        name="quantity",
                        type="INTEGER",
                        mode="REQUIRED",
                        description="Quantity sold",
                    ),
                    BigQueryField(
                        name="unit_price",
                        type="FLOAT",
                        mode="REQUIRED",
                        description="Price per unit",
                    ),
                    BigQueryField(
                        name="total_amount",
                        type="FLOAT",
                        mode="REQUIRED",
                        description="Total sale amount",
                    ),
                    BigQueryField(
                        name="region",
                        type="STRING",
                        mode="NULLABLE",
                        description="Sales region",
                    ),
                ],
            ),
            BigQueryTable(
                dataset_id="sales_analytics",
                id="monthly_revenue",
                description="Monthly revenue aggregation",
                fields=[
                    BigQueryField(
                        name="month",
                        type="DATE",
                        mode="REQUIRED",
                        description="First day of the month",
                    ),
                    BigQueryField(
                        name="region",
                        type="STRING",
                        mode="REQUIRED",
                        description="Sales region",
                    ),
                    BigQueryField(
                        name="total_revenue",
                        type="FLOAT",
                        mode="REQUIRED",
                        description="Total revenue for the month",
                    ),
                    BigQueryField(
                        name="transaction_count",
                        type="INTEGER",
                        mode="REQUIRED",
                        description="Number of transactions",
                    ),
                    BigQueryField(
                        name="avg_order_value",
                        type="FLOAT",
                        mode="NULLABLE",
                        description="Average order value",
                    ),
                ],
            ),
            BigQueryTable(
                dataset_id="customer_data",
                id="customers",
                description="Customer master data",
                fields=[
                    BigQueryField(
                        name="customer_id",
                        type="STRING",
                        mode="REQUIRED",
                        description="Unique customer identifier",
                    ),
                    BigQueryField(
                        name="email",
                        type="STRING",
                        mode="REQUIRED",
                        description="Customer email address",
                    ),
                    BigQueryField(
                        name="name",
                        type="STRING",
                        mode="REQUIRED",
                        description="Customer full name",
                    ),
                    BigQueryField(
                        name="created_at",
                        type="TIMESTAMP",
                        mode="REQUIRED",
                        description="Account creation timestamp",
                    ),
                    BigQueryField(
                        name="tier",
                        type="STRING",
                        mode="NULLABLE",
                        description="Customer tier (bronze, silver, gold)",
                    ),
                    BigQueryField(
                        name="lifetime_value",
                        type="FLOAT",
                        mode="NULLABLE",
                        description="Customer lifetime value",
                    ),
                ],
            ),
            BigQueryTable(
                dataset_id="product_catalog",
                id="products",
                description="Product catalog",
                fields=[
                    BigQueryField(
                        name="product_id",
                        type="STRING",
                        mode="REQUIRED",
                        description="Product identifier",
                    ),
                    BigQueryField(
                        name="name",
                        type="STRING",
                        mode="REQUIRED",
                        description="Product name",
                    ),
                    BigQueryField(
                        name="category",
                        type="STRING",
                        mode="REQUIRED",
                        description="Product category",
                    ),
                    BigQueryField(
                        name="price",
                        type="FLOAT",
                        mode="REQUIRED",
                        description="Current price",
                    ),
                    BigQueryField(
                        name="stock_quantity",
                        type="INTEGER",
                        mode="REQUIRED",
                        description="Available stock",
                    ),
                    BigQueryField(
                        name="is_active",
                        type="BOOLEAN",
                        mode="REQUIRED",
                        description="Whether product is active",
                    ),
                ],
            ),
        ],
        buckets=[
            StorageBucket(
                name="sandbox-data-lake-123",
                location="US",
                storage_class="STANDARD",
                versioning_enabled=True,
                lifecycle_rules=[
                    LifecycleRule(
                        action="Delete",
                        age_days=365,
                    )
                ],
            ),
            StorageBucket(
                name="sandbox-exports-123",
                location="US",
                storage_class="STANDARD",
                versioning_enabled=False,
            ),
            StorageBucket(
                name="sandbox-backups-123",
                location="US-EAST1",
                storage_class="NEARLINE",
                versioning_enabled=True,
                lifecycle_rules=[
                    LifecycleRule(
                        action="SetStorageClass",
                        action_storage_class="COLDLINE",
                        age_days=90,
                    ),
                    LifecycleRule(
                        action="Delete",
                        age_days=730,
                    ),
                ],
            ),
            StorageBucket(
                name="sandbox-logs-archive-123",
                location="US",
                storage_class="ARCHIVE",
                versioning_enabled=False,
            ),
        ],
        objects=[
            StorageObject(
                bucket="sandbox-data-lake-123",
                name="raw/sales/2025/01/daily_sales_20250101.csv",
                content_type="text/csv",
                content="transaction_id,sale_date,product_id,quantity,unit_price,total_amount,region\nTXN001,2025-01-01,PROD001,5,19.99,99.95,North America\nTXN002,2025-01-01,PROD002,3,29.99,89.97,Europe\nTXN003,2025-01-01,PROD001,10,19.99,199.90,Asia Pacific",
            ),
            StorageObject(
                bucket="sandbox-data-lake-123",
                name="raw/sales/2025/01/daily_sales_20250102.csv",
                content_type="text/csv",
                content="transaction_id,sale_date,product_id,quantity,unit_price,total_amount,region\nTXN004,2025-01-02,PROD003,2,49.99,99.98,North America\nTXN005,2025-01-02,PROD001,7,19.99,139.93,Europe\nTXN006,2025-01-02,PROD002,4,29.99,119.96,Asia Pacific",
            ),
            StorageObject(
                bucket="sandbox-data-lake-123",
                name="processed/customers/customer_segments.json",
                content_type="application/json",
                content='{"segments": [{"name": "High Value", "count": 1500, "avgLTV": 2500}, {"name": "Medium Value", "count": 5000, "avgLTV": 800}, {"name": "Low Value", "count": 12000, "avgLTV": 150}]}',
            ),
            StorageObject(
                bucket="sandbox-exports-123",
                name="exports/monthly_report_202501.csv",
                content_type="text/csv",
                content="month,total_revenue,total_transactions,avg_order_value\n2025-01,1250000.00,15000,83.33",
            ),
            StorageObject(
                bucket="sandbox-data-lake-123",
                name="config/etl_pipeline_config.yaml",
                content_type="application/x-yaml",
                content='pipeline:\n  name: daily_sales_etl\n  schedule: "0 2 * * *"\n  source:\n    type: gcs\n    bucket: sandbox-data-lake-123\n    prefix: raw/sales/\n  destination:\n    type: bigquery\n    dataset: sales_analytics\n    table: daily_sales',
            ),
        ],
        log_entries=[
            LogEntry(
                log_name="application-logs",
                message="Application started successfully",
                severity="INFO",
                timestamp="2025-01-15T08:00:00Z",
                resource_type="gce_instance",
                resource_labels={
                    "instance_id": "1234567890",
                    "zone": "us-central1-a",
                },
            ),
            LogEntry(
                log_name="application-logs",
                message="Database connection established",
                severity="INFO",
                timestamp="2025-01-15T08:00:05Z",
                resource_type="gce_instance",
                resource_labels={
                    "instance_id": "1234567890",
                    "zone": "us-central1-a",
                },
            ),
            LogEntry(
                log_name="application-logs",
                json_data={
                    "event": "user_login",
                    "user_id": "user_123",
                    "ip_address": "192.168.1.100",
                    "success": True,
                },
                severity="INFO",
                timestamp="2025-01-15T09:30:00Z",
                resource_type="gce_instance",
                resource_labels={
                    "instance_id": "1234567890",
                    "zone": "us-central1-a",
                },
            ),
            LogEntry(
                log_name="error-logs",
                message="Failed to process batch: timeout exceeded",
                severity="ERROR",
                timestamp="2025-01-15T14:22:00Z",
                resource_type="cloud_function",
                resource_labels={
                    "function_name": "process_batch",
                    "region": "us-central1",
                },
            ),
            LogEntry(
                log_name="audit-logs",
                json_data={
                    "action": "resource.create",
                    "resource_type": "storage.bucket",
                    "resource_name": "new-bucket",
                    "actor": "admin@example.com",
                },
                severity="NOTICE",
                timestamp="2025-01-15T10:15:00Z",
                resource_type="project",
            ),
        ],
        log_sinks=[
            LogSink(
                name="bigquery-audit-sink",
                filter='logName:"cloudaudit.googleapis.com"',
                description="Export audit logs for analysis",
            ),
            LogSink(
                name="error-logs-sink",
                filter="severity>=ERROR",
                description="Capture error logs",
            ),
            LogSink(
                name="all-logs-sink",
                description="Stream all logs for processing",
            ),
        ],
        log_buckets=[
            LogBucket(
                name="app-logs-bucket5",
                location="global",
                retention_days=30,
                description="Bucket for app logs with 30-day retention",
            ),
            LogBucket(
                name="security-logs-bucket5",
                location="us-central1",
                retention_days=365,
                description="Bucket for security logs with 1-year retention",
            ),
        ],
        instances=[
            ComputeInstance(
                name="web-server-1",
                zone="us-central1-a",
                machine_type="e2-medium",
                description="Primary web server",
                labels={"environment": "production", "team": "web"},
            ),
            ComputeInstance(
                name="web-server-2",
                zone="us-central1-b",
                machine_type="e2-medium",
                description="Secondary web server",
                labels={"environment": "production", "team": "web"},
            ),
            ComputeInstance(
                name="database-server",
                zone="us-central1-a",
                machine_type="n2-standard-4",
                description="Main database server",
                labels={"environment": "production", "team": "database"},
            ),
            ComputeInstance(
                name="dev-instance",
                zone="us-west1-a",
                machine_type="e2-micro",
                description="Development and testing instance",
                labels={"environment": "development", "team": "engineering"},
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[GoogleCloudDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_google_cloud_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_google_cloud_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_monday_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with monday-specific data following the defined schema.
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
from klavis import (
    Klavis,
    MondayBoard,
    MondayDataInput,
    MondayGroup,
    MondayItem,
    MondaySubitem,
    MondayUpdate,
    MondayWorkspace,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_monday_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=MondayDataInput(
        workspaces=[
            MondayWorkspace(
                name="Product Development",
                kind="open",
                description="Main workspace for product development and engineering teams",
            ),
            MondayWorkspace(
                name="Marketing & Sales",
                kind="open",
                description="Workspace for marketing campaigns and sales tracking",
            ),
        ],
        boards=[
            MondayBoard(
                name="Sprint Planning Q1",
                description="Agile sprint planning and task tracking for Q1 2024",
                board_kind="public",
                groups=[
                    MondayGroup(
                        title="Backlog",
                        color="#808080",
                        items=[
                            MondayItem(
                                name="Research new authentication methods",
                                column_values={
                                    "status": "Not Started",
                                    "priority": "Low",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Need to evaluate OAuth 2.0, SAML, and WebAuthn",
                                    )
                                ],
                            )
                        ],
                    ),
                    MondayGroup(
                        title="Sprint 1 - Foundation",
                        color="#0086c0",
                        items=[
                            MondayItem(
                                name="Set up project repository",
                                column_values={
                                    "status": "Done",
                                    "priority": "High",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Repository created on GitHub with proper branch protection rules",
                                    )
                                ],
                                subitems=[
                                    MondaySubitem(
                                        name="Initialize Git repository",
                                    )
                                ],
                            ),
                            MondayItem(
                                name="Implement user authentication",
                                column_values={
                                    "status": "Working on it",
                                    "priority": "Critical",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Started with JWT token implementation",
                                    )
                                ],
                                subitems=[
                                    MondaySubitem(
                                        name="Implement JWT authentication",
                                    )
                                ],
                            ),
                        ],
                    ),
                    MondayGroup(
                        title="Completed",
                        color="#00d647",
                        items=[
                            MondayItem(
                                name="Initial project kickoff",
                                column_values={
                                    "status": "Done",
                                    "priority": "High",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Successful kickoff meeting with all stakeholders",
                                    )
                                ],
                            )
                        ],
                    ),
                ],
            ),
            MondayBoard(
                name="Bug Tracker",
                description="Track and manage software bugs and issues",
                board_kind="public",
                groups=[
                    MondayGroup(
                        title="New Bugs",
                        color="#e44258",
                        items=[
                            MondayItem(
                                name="Login fails on Safari browser",
                                column_values={
                                    "status": "New",
                                    "priority": "Critical",
                                    "severity": "High",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Reported by 3 users, reproducible on Safari 17+",
                                    )
                                ],
                            )
                        ],
                    ),
                    MondayGroup(
                        title="In Progress",
                        color="#fdab3d",
                        items=[
                            MondayItem(
                                name="API timeout on large data requests",
                                column_values={
                                    "status": "Investigating",
                                    "priority": "High",
                                    "severity": "Medium",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Identified slow database query as root cause",
                                    )
                                ],
                                subitems=[
                                    MondaySubitem(
                                        name="Add database indexes",
                                    )
                                ],
                            )
                        ],
                    ),
                    MondayGroup(
                        title="Closed",
                        color="#c4c4c4",
                        items=[
                            MondayItem(
                                name="Dark mode toggle not working",
                                column_values={
                                    "status": "Closed",
                                    "priority": "Medium",
                                    "severity": "Low",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Fixed in version 1.2.0",
                                    )
                                ],
                            )
                        ],
                    ),
                ],
            ),
            MondayBoard(
                name="Marketing Campaigns 2024",
                description="Marketing campaign planning and execution",
                board_kind="public",
                groups=[
                    MondayGroup(
                        title="Q1 Campaigns",
                        color="#9cd326",
                        items=[
                            MondayItem(
                                name="Spring Product Launch",
                                column_values={
                                    "status": "In Progress",
                                    "budget": "$50000",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Landing page design completed",
                                    )
                                ],
                                subitems=[
                                    MondaySubitem(
                                        name="Create landing page",
                                    )
                                ],
                            )
                        ],
                    ),
                    MondayGroup(
                        title="Q2 Planning",
                        color="#037f4c",
                        items=[
                            MondayItem(
                                name="Summer Webinar Series",
                                column_values={
                                    "status": "Planning",
                                    "budget": "$25000",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Brainstorming topics with product team",
                                    )
                                ],
                            )
                        ],
                    ),
                ],
            ),
            MondayBoard(
                name="Customer Success",
                description="Customer onboarding and support initiatives",
                board_kind="public",
                groups=[
                    MondayGroup(
                        title="Enterprise Clients",
                        color="#784bd1",
                        items=[
                            MondayItem(
                                name="Acme Corp - Onboarding",
                                column_values={
                                    "status": "In Progress",
                                    "account_value": "$250000",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Kickoff call completed, 50 user licenses purchased",
                                    )
                                ],
                                subitems=[
                                    MondaySubitem(
                                        name="Initial training session",
                                    )
                                ],
                            )
                        ],
                    ),
                    MondayGroup(
                        title="SMB Clients",
                        color="#579bfc",
                        items=[
                            MondayItem(
                                name="Digital Agency Co - Support",
                                column_values={
                                    "status": "Active",
                                    "account_value": "$5000",
                                },
                                updates=[
                                    MondayUpdate(
                                        body="Monthly check-in call completed",
                                    )
                                ],
                            )
                        ],
                    ),
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[MondayDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_monday_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_monday_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_motion_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Initialize the sandbox with motion-specific data following the defined schema.
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
from klavis import (
    Klavis,
    MotionComment,
    MotionDataInput,
    MotionProject,
    MotionTask,
    MotionWorkspace,
)

client = Klavis(
    api_key="YOUR_API_KEY",
)
client.sandbox.initialize_motion_sandbox(
    sandbox_id="sandbox_id",
    init_default_data=True,
    request=MotionDataInput(
        workspaces=[
            MotionWorkspace(
                name="Engineering Team",
                projects=[
                    MotionProject(
                        name="Product Launch Q1",
                        description="Launch new product features for Q1 2024",
                        due_date="2024-03-31T23:59:59.000Z",
                        priority="HIGH",
                        labels=["product", "launch", "q1"],
                        tasks=[
                            MotionTask(
                                name="Design landing page mockups",
                                description="Create high-fidelity mockups for the new landing page using Figma",
                                status="COMPLETED",
                                priority="HIGH",
                                due_date="2024-01-15T17:00:00.000Z",
                                duration=240,
                                labels=["design", "frontend"],
                                comments=[
                                    MotionComment(
                                        text="First draft of mockups is ready for review",
                                    ),
                                    MotionComment(
                                        text="Looks great! Just need to adjust the color scheme",
                                    ),
                                    MotionComment(
                                        text="Final version approved by the team",
                                    ),
                                ],
                            ),
                            MotionTask(
                                name="Implement authentication flow",
                                description="Build secure authentication with OAuth2 and JWT tokens",
                                status="IN_PROGRESS",
                                priority="ASAP",
                                due_date="2024-01-20T17:00:00.000Z",
                                duration=480,
                                labels=["backend", "security"],
                                comments=[
                                    MotionComment(
                                        text="Starting with OAuth2 provider integration",
                                    ),
                                    MotionComment(
                                        text="Token refresh logic implemented and tested",
                                    ),
                                ],
                            ),
                            MotionTask(
                                name="Set up CI/CD pipeline",
                                description="Configure automated testing and deployment workflows",
                                status="TODO",
                                priority="HIGH",
                                due_date="2024-01-25T17:00:00.000Z",
                                duration=180,
                                labels=["devops", "infrastructure"],
                                comments=[
                                    MotionComment(
                                        text="Need to decide between GitHub Actions and CircleCI",
                                    )
                                ],
                            ),
                            MotionTask(
                                name="Write API documentation",
                                description="Document all REST API endpoints with examples",
                                status="TODO",
                                priority="MEDIUM",
                                due_date="2024-01-30T17:00:00.000Z",
                                duration=120,
                                labels=["documentation", "api"],
                                comments=[
                                    MotionComment(
                                        text="text",
                                    )
                                ],
                            ),
                        ],
                    ),
                    MotionProject(
                        name="Infrastructure Upgrade",
                        description="Migrate to new cloud infrastructure",
                        due_date="2024-02-28T23:59:59.000Z",
                        priority="MEDIUM",
                        labels=["infrastructure", "migration"],
                        tasks=[
                            MotionTask(
                                name="Audit current infrastructure",
                                description="Document all current services and dependencies",
                                status="COMPLETED",
                                priority="HIGH",
                                due_date="2024-01-10T17:00:00.000Z",
                                duration=180,
                                labels=["infrastructure", "audit"],
                                comments=[
                                    MotionComment(
                                        text="Audit complete - found 23 services to migrate",
                                    )
                                ],
                            ),
                            MotionTask(
                                name="Set up Kubernetes cluster",
                                description="Configure production-ready K8s cluster with monitoring",
                                status="IN_PROGRESS",
                                priority="HIGH",
                                due_date="2024-01-22T17:00:00.000Z",
                                duration=360,
                                labels=["kubernetes", "devops"],
                                comments=[
                                    MotionComment(
                                        text="Cluster is up, working on monitoring setup",
                                    ),
                                    MotionComment(
                                        text="Prometheus and Grafana configured",
                                    ),
                                ],
                            ),
                            MotionTask(
                                name="Migrate database",
                                description="Move production database to new infrastructure with zero downtime",
                                status="TODO",
                                priority="ASAP",
                                due_date="2024-02-01T17:00:00.000Z",
                                duration=480,
                                labels=["database", "migration"],
                                comments=[
                                    MotionComment(
                                        text="Need to plan maintenance window with stakeholders",
                                    )
                                ],
                            ),
                        ],
                    ),
                    MotionProject(
                        name="Technical Debt Reduction",
                        description="Address accumulated technical debt",
                        priority="LOW",
                        labels=["refactoring", "maintenance"],
                        tasks=[
                            MotionTask(
                                name="Refactor legacy authentication module",
                                description="Update old auth code to use modern patterns",
                                status="TODO",
                                priority="MEDIUM",
                                duration=240,
                                labels=["refactoring", "backend"],
                                comments=[
                                    MotionComment(
                                        text="This has been on the backlog for 6 months",
                                    ),
                                    MotionComment(
                                        text="Let's prioritize this after the Q1 launch",
                                    ),
                                ],
                            ),
                            MotionTask(
                                name="Update dependencies",
                                description="Update all outdated npm and pip packages",
                                status="TODO",
                                priority="LOW",
                                duration=90,
                                labels=["maintenance", "dependencies"],
                                comments=[
                                    MotionComment(
                                        text="text",
                                    )
                                ],
                            ),
                        ],
                    ),
                ],
            ),
            MotionWorkspace(
                name="Marketing Team",
                projects=[
                    MotionProject(
                        name="Q1 Content Strategy",
                        description="Plan and execute content marketing for Q1",
                        due_date="2024-03-31T23:59:59.000Z",
                        priority="HIGH",
                        labels=["marketing", "content"],
                        tasks=[
                            MotionTask(
                                name="Create blog post calendar",
                                description="Plan blog posts for January through March",
                                status="COMPLETED",
                                priority="HIGH",
                                due_date="2024-01-05T17:00:00.000Z",
                                duration=120,
                                labels=["content", "planning"],
                                comments=[
                                    MotionComment(
                                        text="Calendar created with 12 blog post ideas",
                                    ),
                                    MotionComment(
                                        text="Topics approved by leadership team",
                                    ),
                                ],
                            ),
                            MotionTask(
                                name="Write launch announcement",
                                description="Draft product launch blog post and press release",
                                status="IN_PROGRESS",
                                priority="ASAP",
                                due_date="2024-01-18T17:00:00.000Z",
                                duration=180,
                                labels=["content", "launch"],
                                comments=[
                                    MotionComment(
                                        text="First draft is ready for review",
                                    )
                                ],
                            ),
                            MotionTask(
                                name="Design social media graphics",
                                description="Create graphics for launch announcement across all platforms",
                                status="TODO",
                                priority="HIGH",
                                due_date="2024-01-20T17:00:00.000Z",
                                duration=150,
                                labels=["design", "social-media"],
                                comments=[
                                    MotionComment(
                                        text="text",
                                    )
                                ],
                            ),
                            MotionTask(
                                name="Schedule email campaign",
                                description="Set up automated email sequence for product launch",
                                status="TODO",
                                priority="MEDIUM",
                                due_date="2024-01-25T17:00:00.000Z",
                                duration=90,
                                labels=["email", "automation"],
                                comments=[
                                    MotionComment(
                                        text="Need to segment the audience first",
                                    ),
                                    MotionComment(
                                        text="Audience segmentation complete",
                                    ),
                                ],
                            ),
                        ],
                    ),
                    MotionProject(
                        name="Brand Refresh",
                        description="Update company branding and visual identity",
                        priority="MEDIUM",
                        labels=["branding", "design"],
                        tasks=[
                            MotionTask(
                                name="Research competitor branding",
                                description="Analyze competitor brand positioning and visual identity",
                                status="COMPLETED",
                                priority="MEDIUM",
                                duration=180,
                                labels=["research", "competitive-analysis"],
                                comments=[
                                    MotionComment(
                                        text="Analyzed 10 key competitors",
                                    )
                                ],
                            ),
                            MotionTask(
                                name="Create new logo concepts",
                                description="Design 3-5 logo variations for review",
                                status="IN_PROGRESS",
                                priority="MEDIUM",
                                duration=240,
                                labels=["design", "logo"],
                                comments=[
                                    MotionComment(
                                        text="Working on the third concept now",
                                    )
                                ],
                            ),
                        ],
                    ),
                ],
            ),
            MotionWorkspace(
                name="Product Team",
                projects=[
                    MotionProject(
                        name="User Research Initiative",
                        description="Conduct user research to inform product decisions",
                        due_date="2024-02-15T23:59:59.000Z",
                        priority="HIGH",
                        labels=["research", "ux"],
                        tasks=[
                            MotionTask(
                                name="Design user survey",
                                description="Create comprehensive survey to gather user feedback",
                                status="COMPLETED",
                                priority="HIGH",
                                due_date="2024-01-08T17:00:00.000Z",
                                duration=120,
                                labels=["research", "survey"],
                                comments=[
                                    MotionComment(
                                        text="Survey has 25 questions covering all key areas",
                                    ),
                                    MotionComment(
                                        text="Survey reviewed and approved",
                                    ),
                                ],
                            ),
                            MotionTask(
                                name="Recruit interview participants",
                                description="Find 15-20 users for in-depth interviews",
                                status="IN_PROGRESS",
                                priority="HIGH",
                                due_date="2024-01-15T17:00:00.000Z",
                                duration=90,
                                labels=["research", "recruitment"],
                                comments=[
                                    MotionComment(
                                        text="12 participants confirmed so far",
                                    )
                                ],
                            ),
                            MotionTask(
                                name="Conduct user interviews",
                                description="Interview users to understand pain points and needs",
                                status="TODO",
                                priority="HIGH",
                                due_date="2024-01-30T17:00:00.000Z",
                                duration=600,
                                labels=["research", "interviews"],
                                comments=[
                                    MotionComment(
                                        text="text",
                                    )
                                ],
                            ),
                            MotionTask(
                                name="Analyze research findings",
                                description="Synthesize research data and create insights report",
                                status="TODO",
                                priority="MEDIUM",
                                due_date="2024-02-10T17:00:00.000Z",
                                duration=240,
                                labels=["research", "analysis"],
                                comments=[
                                    MotionComment(
                                        text="Will use Dovetail for analysis",
                                    )
                                ],
                            ),
                        ],
                    )
                ],
            ),
        ],
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

**sandbox_id:** `str` — The unique sandbox identifier
    
</dd>
</dl>

<dl>
<dd>

**init_default_data:** `typing.Optional[bool]` — If true, use default test data for initialization
    
</dd>
</dl>

<dl>
<dd>

**request:** `typing.Optional[MotionDataInput]` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_motion_sandbox</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Export all data from the sandbox in the same format used for initialization.
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
client.sandbox.dump_motion_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` — The unique sandbox identifier
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">dump_calcom_sandbox</a>(...)</code></summary>
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
client.sandbox.dump_calcom_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` 
    
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

<details><summary><code>client.sandbox.<a href="src/klavis/sandbox/client.py">initialize_calcom_sandbox</a>(...)</code></summary>
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
client.sandbox.initialize_calcom_sandbox(
    sandbox_id="sandbox_id",
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

**sandbox_id:** `str` 
    
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

## Universe
<details><summary><code>client.universe.<a href="src/klavis/universe/client.py">list_universes</a>()</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all available universes.
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
client.universe.list_universes()

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

<details><summary><code>client.universe.<a href="src/klavis/universe/client.py">get_universe_data</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get universe initial data for all services.
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
client.universe.get_universe_data(
    universe_id="universe_id",
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

**universe_id:** `str` 
    
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

<details><summary><code>client.universe.<a href="src/klavis/universe/client.py">acquire_universe</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Acquire the next idle universe instance.
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
client.universe.acquire_universe(
    universe_id="universe_id",
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

**universe_id:** `str` 
    
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

<details><summary><code>client.universe.<a href="src/klavis/universe/client.py">release_universe</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Release and Reinitialize the universe to its initial state.

This immediately returns and handles reset/initialization in the background.
Only gcalendar and notion setup methods use sandbox (which call reset internally).
Others need explicit reset before re-initialization.
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
client.universe.release_universe(
    universe_instance_id="universe_instance_id",
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

**universe_instance_id:** `str` 
    
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

<details><summary><code>client.universe.<a href="src/klavis/universe/client.py">get_task</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get task details within a universe instance.
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
client.universe.get_task(
    universe_id="universe_id",
    task_num="task_num",
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

**universe_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**task_num:** `str` 
    
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

<details><summary><code>client.universe.<a href="src/klavis/universe/client.py">verify_task</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Verify if the task has been performed correctly by running the task's verify function.
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
client.universe.verify_task(
    universe_instance_id="universe_instance_id",
    task_num="task_num",
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

**universe_instance_id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**task_num:** `str` 
    
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

