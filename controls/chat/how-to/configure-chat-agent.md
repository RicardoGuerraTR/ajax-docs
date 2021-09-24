---
title: Connect to Chatbot Service via Chat Agent
page_title: Connect to Chatbot Service via Chat Agent- RadChat
description: Check our Web Forms article about Connect to Chatbot Service via Chat Agent.
slug: chat/how-to/configure-chat-agent
tags: connect, chatbot, service, configure, agent
published: True
position: 0
---

# Connecting to Chat Bot Services via Chat Agent

To connect the [RadChat]({%slug chat/overview%}) control to any service and render the responses from the service, utilize the [post event]({%slug chat/client-side-programming/events/onpost%}) of the control and its [public client-side API]({%slug chat/client-side-programming/overview%}).

To encapsulate the communication with the specific service, use an **agent** helper class. The **agent** class handles the communication with the external Chat Bot service. The establishment of the connection to the service and the binding of the appropriate events are done within the **init** method of the agent. In this way, the agent is able to receive the responses.

The following example uses the [Microsoft Bot Framework](https://dev.botframework.com/). The **agent** is subscribed to listen for any **activity$** of the remote service. When an activity is detected, the appropriate method from the Chat public API is invoked to render the data. To handle the user input, the example implements the **post** event handler of the Chat and the arguments are passed to the Chat Bot service.

````ASP.NET
<!-- Load Bot Framework Client API -->
<script src="http://unpkg.com/botframework-directlinejs/directLine.js"></script>

<telerik:RadChat runat="server" ID="RadChat1">
    <ClientEvents OnSendMessage="onSendMessage" OnPost="onPost" OnLoad="onLoad" />
    <UserSettings Name="John" />
</telerik:RadChat>
````

````JavaScript
function onLoad(sender, args) {
    // Create a new agent and pass the Chat control
    // This makes the chat agent available as Chat control property for easier usage in events
    sender.agent = new DirectLineAgent(sender, "Y_ly-If6haE.cwA.PQE.ZwOOsq4MlHcD3_YLFI-t9oW6L6DXMMBoi67LBz9WaWA");
}

function onSendMessage(sender, args) {
    var postArgs = {
        text: args.get_text()
    };

    sender.agent.postMessage(postArgs);
}

function onPost(sender, args) {
    var postArgs = {
        text: args.get_text(),
        type: args.get_type(),
        timestamp: args.get_timestamp(),
        from: args.get_from()
    };

    sender.agent.postMessage(postArgs);
}
````

````JavaScript

// configure the Chat Agent
var DirectLineAgent = kendo.Class.extend({
    init: function (chat, secret) {
        this.chat = chat;
        this.iconUrl = "https://demos.telerik.com/kendo-ui/content/chat/avatar.png";

        // Assign here the Bot framework agent
        // The below example uses the Microsoft's Bot Framework
        this.agent = new DirectLine.DirectLine({ secret: secret });

        // The below code would depend on the Bot framework of choice
        // In this case, the agent is subscribed to listen for any activity of the service
        // Its onResponse method would be executed on any activity detected
        this.agent.activity$.subscribe($.proxy(this.onResponse, this));
    },
    // The implementation of the below methods would depend on the Bot framework of choice
    // This example uses the Microsoft's Bot Framework API to demonstrate a possible implementation
    postMessage: function (args) {
        this.agent.postActivity(args).subscribe();
    },

    onResponse: function (response) {
        if (response.from.id === this.chat.get_user().id) {
            return;
        }

        response.from.iconUrl = this.iconUrl;

        this.renderMessage(response);

        this.renderAttachments(response);

        this.renderSuggestedActions(response.suggestedActions);
    },

    renderMessage: function (message) {
        if (message.text || message.type == "typing") {
            this.chat.renderMessage(message, message.from);
        }
    },

    renderAttachments: function (data) {
        this.chat.renderAttachments(data, data.from);
    },

    renderSuggestedActions: function (suggestedActions) {
        var actions = [];

        if (suggestedActions && suggestedActions.actions) {
            actions = suggestedActions.actions;
        }

        this.chat.renderSuggestedActions(actions);
    }
});
````


# See Also

 * [ASP.NET Chat Product Overview]({%slug chat/overview%})

 * [RadChat Travel](https://demos.telerik.com/aspnet-ajax/chat/travel/defaultcs.aspx) online demo

 * [RadChat Client-Side Programming]({%slug chat/client-side-programming/overview%})

 

