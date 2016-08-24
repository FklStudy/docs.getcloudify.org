---

title: The Deployments Page



weight: 130

terminology_link: reference-terminology.html
node_types_link: dsl-spec-node-types.html
relationships_link: dsl-spec-relationships.html
---


When clicking on the `Deployments` tab and choosing a deployment you will be able to choose one of the following:

## Actions Available On A Deployment
The table presented on the deployment page contains a dropdown menu, allowing to perform actions on a deployment. Available actions are: `execute workflow`, `update deployment`, and `delete`.<br/>
![Deployment actions]({{ c.img("ui/deploymentActions/actions-dropdown.png" ) }})

### Execute Workflow
To execute a workflow simply choose the desired workflow name, fill the requested parameters and click `Confirm`.<br/>
![Execute workflow]({{ c.img("ui/deploymentActions/execute.png" ) }})

### Delete Deployment
To delete the deployment, simply click `Yes`.<br/>
![Delete deployment]({{ c.img("ui/deploymentActions/delete-deployment.png" ) }})

### Update Deployment
To Update the deployment, simply select or provide a URL to a new archive. If inputs are needed, select an inputs file. If the main blueprint file isn't named 'blueprint.yaml', type a different name. Lastly you can choose whether to run `Install` and `Uninstall` workflows on the changes  - by default install will run on the added sub-graph and uninstall on the removed sub-graph, but the behavior can be overridden by marking which of the workflows should run, or providing a custom workflow of your own. More details on deployment update can be found at <http://docs.getcloudify.org/3.4.0/manager/update-deployment/> <br/>
![Update deployment]({{ c.img("ui/deploymentActions/update-deployment.png" ) }})

# Topology
The Topology is an application’s graph of nodes and their relationships, which describes the lifecycle events or other operations that each node and relationship exposes for use in workflows.<br>
Each of the blueprint's nodes is displayed as a square container, which can contain other nodes. Each node has a title describing its name, and an icon to indicate the [node's type]({{ relRef("blueprints/spec-node-types.md") }}).<br>
[Relationships]({{ relRef("blueprints/spec-relationships.md") }}) between nodes are marked with arrows, starts from the connected node and ends at the target node.<br>
The topology view shows only the application nodes and not the network nodes. If a node has a network dependency, it will be displayed as a bullet icon in the node's title.<br>
Host nodes are shown with number bullet beside the node type icon, which indicates the number of instances and number of initiated instances. Contained nodes are shown with status bullet beside the node type icon, which indicates the node status by bullet icon & color.
The contained nodes bullet indicates the status of all instances of the specific node. For example, if at least one instance raised an error, the bullet will be colored in red.
The bullet color indicates the node current status:<br>

![Loading status]({{ c.img("ui/ui-node-status-process.png" ) }}) - Node is in loading process<br>
![Error status]({{ c.img("ui/ui-node-status-error.png" ) }}) - An error occurred while running the node<br>
![Warning status]({{ c.img("ui/ui-node-status-warning.png" ) }}) - Warning raised while running the node<br>
![Success status]({{ c.img("ui/ui-node-status-success.png" ) }}) - Node was initiated successfully<br>

![Deployment topology]({{ c.img("ui/ui-deployment-ready.jpg" ) }})

Clicking a node's title will open a side panel with runtime properties of the selected node. The floating panel allows the user to select which instance details to show.<br>

![Deployment node details]({{ c.img("ui/ui-deployment-floating-panel.png" ) }})

# Network
A map of networks topologies according to the blueprint's topology contains internal and external networks, hosts, routers.<br/>
The network's name is displayed as a grey title, each network contains sub-networks displayed as colored lines underneath.
Network devices, such as hosts & routers, are displayed as icons, each icon indicates the device's type.
Connections between sub-networks and devices are marked with a colored line, by the color of the connected sub-network.<br>
Clicking a device will open a side panel with details of the selected device.<br>

![Deployment networks]({{ c.img("ui/ui-deployment-networks.jpg" ) }})

# Nodes
A list of nodes according to the blueprint's topology.<br/>
For every node, its type, number of instances, and relationships are shown. By clicking the magnifier icon, a side panel will be opened with the selected node's details.
![Deployment nodes]({{ c.img("ui/ui-deployment-nodes.jpg" ) }})

# Executions
Running instances of a workflow.
![Deployment execution]({{ c.img("ui/ui-deployment-execution.jpg" ) }})

# Monitoring
See the definition [here]({{ relRef("manager_webui/graphing-metrics.md") }}).