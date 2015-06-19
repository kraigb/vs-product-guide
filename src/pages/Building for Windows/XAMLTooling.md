<properties
    pageTitle="XAML Tooling"
    description="The Live Visual Tree and Live Property Explorer for XAML (Windows Presentation Foundation and Windows Store apps) make it easier to fine-tune an application's UI, and avoids repeated compile-and-run iterations."
    slug="xamltooling"
    order="300"    
    keywords="visual studio, vs2015, vs, visualstudio, windows, windows 10, XAML"
/>

The Live Visual Tree and the Live Property Explorer let you inspect the visual tree of your running WPF or Windows Store app, as it exists at any point in the life cycle of the app. You can edit properties on the tree, such as button text, which are then displayed in the running app. (note: you cannot change the composition of the tree).

You can also select visual components in the running app. These selections will update the Live Visual Tree in Visual Studio, enabling you to focus in on the parts of your app that might need investigation or updates.


## Live Visual Tree

The Live Visual Tree views the full visual tree of a running application during a debug session. The Live Visual Tree is available when you press F5 in Visual Studio or attach to a running application. You can use the Live Visual Tree to select elements in a running application for inspection in the Live Property Explorer. Descendant count is displayed, and if the source information is available, you can instantly find the file and location of the element's definition.

The Live Visual Tree is also connected to the XAML source editing experience. As you select XAML nodes in the Live Visual Tree, the selected textual XAML in the IDE changes to match. You always know which text matches, making it easy to find the line of XAML to look at or change.

## Live Property Explorer

Use this tool to inspect the properties set on any element in a running application, grouped by the scope in which they are set. You can modify these properties during a debugging session and immediately see their changes in the running application.

Picking apart how properties override each other and figuring out winning behavior can prove difficult at design time. Now, by using our new UI debugging tools for XAML, you can perform these inspections at runtime, when you can take everything into account. 

![UI Debugging Tools for XAML](_assets/dd_LiveXAML.png)






<Image>
