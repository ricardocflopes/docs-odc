---
summary: Explore authentication actions for built-in and external identity providers in OutSystems Developer Cloud (ODC).
tags:
locale: en-us
guid: ba01fdf7-e6d1-42eb-b21a-e9a0f25ef405
app_type: mobile apps, reactive web apps
platform-version: odc
figma:
---

# CallAgent V2 service action

OutSystems provides an in-built CallAgentV2 service action to integrate with the AI model and implement function calling capability.  

The CallAgentV2 service action receives the Agent ID and the user’s prompt as input parameters and allows you to:

* Pass a list of functions to the model to process the prompt. 

* Pass the function output and the user’s prompt to the model to generate a natural language response.

You can access this service action from the **Logic** tab.  Under the Logic tab, go to **Service Actions > AIAgentBuilder > CallAgentV2.**

## Input parameters

- **AgentId** - Identifier of the Agent. Once an agent is created, you can obtain the AgentID from the AI Agent Builder.

- **ChatMessages** - List of chat messages exchanged between an agent and the user. Also, once a specific function is executed, the output of the function is appended to the user's question and is passed to this parameter to generate a response.  

- **Tools** - List of functions to be used by the model to process the prompt. For each function, include the **Name**, **Description**, **Parameters**, and **RequiredParameters**.

## Output parameters

- **Response** - Response generated by the model

- **TokenCount** - Total count of the request tokens, response tokens, and the sum of the request and response tokens.

- **ToolSelection** - The name and the parameters of a specific function to be invoked to process the prompt.

## Error handling

OutSystems handles the following errors internally:

- Invalid agent

- Invalid AI model

- Invalid data source

- AI model doesn’t support function calling

If you see a generic 500 error, refer to logs in the ODC portal for more details.