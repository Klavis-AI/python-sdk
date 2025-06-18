# McpServer

Types:

```python
from klavis.types import (
    ConnectionType,
    ServerName,
    ServerTool,
    McpServerCallToolResponse,
    McpServerGetToolsResponse,
    McpServerListServersResponse,
    McpServerListToolsResponse,
)
```

Methods:

- <code title="post /mcp-server/call-tool">client.mcp_server.<a href="./src/klavis/resources/mcp_server/mcp_server.py">call_tool</a>(\*\*<a href="src/klavis/types/mcp_server_call_tool_params.py">params</a>) -> <a href="./src/klavis/types/mcp_server_call_tool_response.py">McpServerCallToolResponse</a></code>
- <code title="get /mcp-server/tools/{server_name}">client.mcp_server.<a href="./src/klavis/resources/mcp_server/mcp_server.py">get_tools</a>(server_name) -> <a href="./src/klavis/types/mcp_server_get_tools_response.py">McpServerGetToolsResponse</a></code>
- <code title="get /mcp-server/servers">client.mcp_server.<a href="./src/klavis/resources/mcp_server/mcp_server.py">list_servers</a>() -> <a href="./src/klavis/types/mcp_server_list_servers_response.py">McpServerListServersResponse</a></code>
- <code title="get /mcp-server/list-tools/{server_url}">client.mcp_server.<a href="./src/klavis/resources/mcp_server/mcp_server.py">list_tools</a>(server_url, \*\*<a href="src/klavis/types/mcp_server_list_tools_params.py">params</a>) -> <a href="./src/klavis/types/mcp_server_list_tools_response.py">McpServerListToolsResponse</a></code>

## Instance

Types:

```python
from klavis.types.mcp_server import StatusResponse, InstanceCreateResponse, InstanceRetrieveResponse
```

Methods:

- <code title="post /mcp-server/instance/create">client.mcp_server.instance.<a href="./src/klavis/resources/mcp_server/instance.py">create</a>(\*\*<a href="src/klavis/types/mcp_server/instance_create_params.py">params</a>) -> <a href="./src/klavis/types/mcp_server/instance_create_response.py">InstanceCreateResponse</a></code>
- <code title="get /mcp-server/instance/get/{instance_id}">client.mcp_server.instance.<a href="./src/klavis/resources/mcp_server/instance.py">retrieve</a>(instance_id) -> <a href="./src/klavis/types/mcp_server/instance_retrieve_response.py">InstanceRetrieveResponse</a></code>
- <code title="delete /mcp-server/instance/delete/{instance_id}">client.mcp_server.instance.<a href="./src/klavis/resources/mcp_server/instance.py">delete</a>(instance_id) -> <a href="./src/klavis/types/mcp_server/status_response.py">StatusResponse</a></code>
- <code title="delete /mcp-server/instance/delete-auth/{instance_id}">client.mcp_server.instance.<a href="./src/klavis/resources/mcp_server/instance.py">delete_auth</a>(instance_id) -> <a href="./src/klavis/types/mcp_server/status_response.py">StatusResponse</a></code>
- <code title="post /mcp-server/instance/set-auth-token">client.mcp_server.instance.<a href="./src/klavis/resources/mcp_server/instance.py">set_auth_token</a>(\*\*<a href="src/klavis/types/mcp_server/instance_set_auth_token_params.py">params</a>) -> <a href="./src/klavis/types/mcp_server/status_response.py">StatusResponse</a></code>

# WhiteLabeling

Types:

```python
from klavis.types import WhiteLabelingResponse
```

Methods:

- <code title="post /white-labeling/create">client.white_labeling.<a href="./src/klavis/resources/white_labeling.py">create</a>(\*\*<a href="src/klavis/types/white_labeling_create_params.py">params</a>) -> <a href="./src/klavis/types/white_labeling_response.py">WhiteLabelingResponse</a></code>
- <code title="get /white-labeling/get/{client_id}">client.white_labeling.<a href="./src/klavis/resources/white_labeling.py">retrieve</a>(client_id) -> <a href="./src/klavis/types/white_labeling_response.py">WhiteLabelingResponse</a></code>

# User

Types:

```python
from klavis.types import UserListInstancesResponse
```

Methods:

- <code title="get /user/instances">client.user.<a href="./src/klavis/resources/user.py">list_instances</a>(\*\*<a href="src/klavis/types/user_list_instances_params.py">params</a>) -> <a href="./src/klavis/types/user_list_instances_response.py">UserListInstancesResponse</a></code>

# Redirect

Methods:

- <code title="get /redirect">client.redirect.<a href="./src/klavis/resources/redirect.py">to_jira_callback</a>() -> object</code>
