### XAML Tooling Improvements: New Live Visual Tree and Property Explorer

The Live Visual Tree and Live Property Explorer for XAML make it easier to fine-tune an application's UI, and avoids repeated compile-and-run iterations. This feature works for both Windows Presentation Foundation (WPF) and apps built for the new Windows 10 Universal App Platform.

With this new feature, you can navigate the visual tree as it exists at any point in the life cycle of the app. You can edit properties on the tree, such as button text, which are then displayed in the running app. (note: you cannot change the composition of the tree).

You can also select visual components in the running app. These selections will update the Live Visual Tree in Visual Studio, enabling you to focus in on the parts of your app that might need investigation or updates.

The Live Visual Tree is also connected to the XAML source editing experience. As you select XAML nodes in the Live Visual Tree, the selected textual XAML in the IDE changes to match. You always know which text matches, making it easy to find the line of XAML to look at or change.

<Image>