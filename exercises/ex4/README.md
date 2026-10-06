# Exercise 4 - Real world usecase - Enable API Artifact for agentic consumption.

## Overview

The exercise will typically cover:<br>
- How to work with the new API Artifact within SAP Integration Suite.<br>
- How to expose it as MCP server to enable for agentic consumption.<br>
- How AI agent can consume these tools.<br>

In this scenario, the API artifact is the foundation for agentic integration. It already contains the Shopify operations, backend connectivity, request and response
definitions, and runtime policies. By creating an MCP server based on this API artifact, the same operations become available as MCP tools for AI agents. MCP therefore acts as an additional access path to the API artifact: traditional applications can continue to consume the REST API, while AI agents can use the corresponding MCP tools. The agent does not connect directly to Shopify; it invokes a governed MCP tool, which routes the request through the API artifact and applies the configured policies before calling Shopify. This approach enables existing APIs to participate in agentic scenarios without rebuilding the backend integration.<br>


***diagram***

## Exercise 2.1 .

> [!NOTE]
> This is just informative exercise where you don’t need to execute anything but you will get knowledge about securing options.
<br>


  <br>![](/exercises/ex4/images/ex.png)
