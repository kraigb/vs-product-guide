<properties
    pageTitle="Extensibility Model"
    description="Visual Studio Online and Team Foundation Server 2015 are extensible, enabling a wide range of third-party customization."
    slug="vsoextensibility"
    order="100"    
    keywords="visual studio, team foundation server, visual studio online, vs2015, vs, visualstudio, tfs, vso, extensibility"
/>
## REST APIs

JSON REST APIs enable customers and the community to develop custom solutions, making it possible to extend and integrate Visual Studio Online and Team Foundation Server into almost any scenario. These APIs enable a lightweight way to work with Team Foundation Server from virtually any device, platform, or technology stack, including Windows, Android, iOS, Node.js, and others. You can create and query work items, queue a build, get recent team room messages, access source code, and accomplish almost any team or code management task.

## Service hooks

Service hooks make it easy to integrate with external services such as Trello or Campfire, and to build an app experience that is instantly notified when events are triggered in TFS, such as completed builds, commits/check-ins or work item changes.

With service hooks, your app or service can avoid continuously polling to check for these events. This means you can create powerful integration scenarios where Team Foundation Server can inform another service of a change, thereby enabling the use of both services together. You can find services hooks as a new hub in project administration.

A service hook subscription controls what action to perform on a target, external service when a specific type of event happens. Similarly to an e-mail alert subscription, a service hook subscription is associated with the user who created it. When an event occurs and a service hook attempts to match a configured subscription to an event, a permission check is performed to ensure the user who created the subscription has permission to access to the resource associated with the event. For example, a user (likely a project administrator) creates a service hook subscription that is triggered on all “work item created” events. When a new work item is created under an area path that this user does not have access to, the permission check will prevent the subscription from matching and therefore avoid any external notification from being sent via this subscription.

However, because service hooks make it easy to integrate with external services, you should make sure that the data that the creator of a subscription has access to is not made available to other users who might not have the same level of access. For example, a subscription that is defined to send all “code push” events to a Campfire room could result in information being improperly disclosed to users who do not have access to the repository associated with the event (but would be able to see the information because they have access to the Campfire room, for example).
