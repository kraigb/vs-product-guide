<properties
    pageTitle="The .NET Framework 4.6"
    description="The latest version of the .NET Framework includes a host of new features, such as ASP.NET, ADO.nET, and WPF improvements, more Windows Forms High DPI controls, the next-generation 64-bit JIT compiler, native code generation for UWP apps, CLR performance improvements, async changes, SIMD-enabled vector classes, garbage collector updates, cryptography updates, DateTime to Unix time support, compatibility switches, and much more."
    slug="windowsnetfx"
    order="400"    
    keywords="visual studio, vs2015, vs, visualstudio, windows, windows 10, .NET framework"
/>


The latest version of the .NET Framework includes a host of new features, such as ASP.NET, WPF, and WCF improvements, more Windows Forms High DPI controls, networking enhancements, the next-generation 64-bit JIT compiler, CLR performance improvements, SIMD-enabled vector classes, garbage collector updates, cryptography updates, DateTime to Unix time support, compatibility switches, and much more. Entity Framework 7 introduces additional new features and can run on .NET Framework 4.6 and .NET Core. 

## ASP.NET improvements

ASP.NET includes the following improvements in the .NET Framework 4.6:

- A simple task-based System.Web.HttpResponse.FlushAsync method for asynchronous response flushing. It allows responses to be flushed asynchronously by using your language's async/await support.
- The ASP.NET Model BInding system now supports Task-returning model binding methods. This feature allows Web Forms developers to get the scalability benefits of async with the ease of the data-binding system when using newer versions of ORMs, inlcuding the Entity Framework.
- HTTP/2 support in Windows 10. (HTTP/2 is also on by default in WIndows 10 UWP apps that use the System.NET.Http.HttpClient API.)
- Support for the Token Binding Protocol. This protocol, which is the result of Microsoft's collaboration with Google in the area of online authentication, aims to mitigate the prolem of unauthorized users accessing a user's authentication tokens without requiring the user's password or any other privileged knowledge. The Token Binding Protocol is implemented in Wndows 10 as a browser feature. ASP.NET apps will participate in the protocol, so that authentication tokens are validated to be legitimate. The client and the server implementations establish the end-to-end protection specified by the protocol.

## ADO.NET improvements

ADO .NET now supports the Always Encrypted feature available in SQL Server 2016 Community Technology Preview 2 (CTP2). With Always Encrypted, SQL Server can perform operations on encrypted data, and best of all the encryption key resides with the application inside the customer’s trusted environment and not on the server. Always Encrypted secures customer data so DBAs do not have access to plain text data. Encryption and decryption of data happens transparently at the driver level, minimizing changes that have to be made to existing applications.

## Windows Presentation Framework improvements

Improvements made to the WPF platform in the .NET Framework 4.6 and Visual Studio 2015 include the following:
 
- Better HDPI support. Changes have been made to layout rounding to reduce instances of clipping in controls with borders. By default, this feature is enabled only for applications that target the .NET Framework 4.6. 
- Transparent child windows
- Customer reports on Microsoft Connect that touch produces unpredictable behavior have been addressed in the .NET Framework 4.6. The double tap threshold for Windows store apps and WPF apps is now the same in Windows 8.1 and above.
- Multi-image cursor files
- [New set of Visual Diagnostics tools](../../productivity/debugdiag/)
- [Timeline tool in the Performance and Diagnostics hub](../../productivity/debugdiag/)

## Windowws Communication Foundation improvements

WCF now supports SSL version TLS 1.1 and TLS 1.2, in addition to SSL 3.0 and TLS 1.0, when using NetTcp with transport security and client authentication.  It is now possible to select which protocol to use, or to disable old lesser secure protocols. This can be done either by setting the System.ServiceModel.TcpTransportSecurity.SslProtocols property or by adding a line to a configuration file. 

## Windows Forms High DPI

The .NET Framework 4.5.2 included Windows Forms high DPI support for an initial set of controls. The .NET Framework 4.6 add support for more controls: DataGridView, ComboBox, ToolStripComboBox, ToolStripMenuItem, Cursor, DomainUpDown, NumericUpDown, DataGridViewComboBoxColumn, DataGridViewColumn and ToolStripSplitButton types.

This is an opt-in feature. To enable it, set the EnableWindowsFormsHighDpiAutoResizing element to true in the application configuration (app.config) file:

	<appSettings>
	   <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
	</appSettings>

## Networking enhancements

Networking in the .NET Framework 4.6 supports socket reuse. Ordinarily, there is an artificial concurrent connection limit of 64K in Windows, which can limit the scalability of a service and cause local port exhaustion as the number of clients of high-scale online services grows. In the .NET Framework 4.6, the System.Net.Sockets.SocketOptionName.ReuseUnicastPort enumeration value and the P:System.Net.ServicePointManager.ReusePort property, have been added to enable port reuse, which effectively removes the 64K limit on concurrent connections. By default, the System.Net.ServicePointManager.ReusePort property is false unless the HWRPortResueOnSocketBind value of the HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319 registry key is set to 0x1. To enable local port reuse on HTTP connections, set the System.Net.ServicePointManager.ReusePort property to true. This causes all outgoing TCP socket connections from System.Net.Http.HttpClient and System.Net.HttpWebRequest to use a new Windows 10 socket option, SO_REUSE_UNICASTPORT, that enables local port reuse.  

Developers writing a sockets-only application can specify the System.Net.Sockets.SocketOptionName.ReuseUnicastPort option when calling a method such as System.Net.Sockets.Socket.SetSocketOption so that outbound sockets reuse local ports during binding. 

A new property, System.Uri.IdnHost, has been added to the System.Uri class to better support international domain names and PunyCode. 

## Next generation JIT compiler for managed code

The .NET Framework 4.6 features a new version of the 64-bit JIT compiler. This compiler provides significant performance improvements over the older 64-bit JIT compiler. While care has been taken to make the transition to the new compiler as transparent as possible, changes in behavior are possible. We would like to hear directly about any issues encountered when using the new JIT compiler. Please contact us through http://connect.microsoft.com/ if you encounter an issue that may be related to the new JIT. 

The new 64-bit JIT also includes hardware SIMD acceleration features when coupled with System.Numerics frameworks., which can yield significant performance improvements.

## .NET Native

Windows apps for Windows 10 that target .NET Core and are written in C# or Visual Basic can take advantage of a new technology that compiles apps to native code rather than IL. They produce apps characterized by faster startup and execution times. This feature is enabled by default in Visual Studio 2015. 

## CLR performance improvements

The assembly loader uses memory more efficiency by unloading IL assemblies after a corresponding NGEN image is loaded. This change is a major benefit for virtual memory for large 32-bit apps (such as Visual Studio) and also saves physical memory.

## Async changes

- For apps that target the .NET Framework 4.6, System.Threading.Tasks.Task and System.Threading.Tasks.Task<T> objects inherit the culture and UI culture of the calling thread. The behavior of apps that target previous versions of the .NET Framework, or that do not target a specific version of the .NET Framework, is unaffected. For more information, see the "Culture and task-based asynchronous operations” section of the System.Globalization.CultureInfo class topic. 
- The System.Threading.AsyncLocal<T> class allows you to represent ambient data that is local to a given asynchronous control flow, such as an async method. It can be used to persist data across threads. You can also define a callback method that is notified whenever the ambient data changes either because the AsyncLocal<T>.Value property was explicitly changed, or because the thread encountered a context transition. 
- Some additional members support the task-based asynchronouspattern (TAP), such as System.Threading.Tasks.Task.CompletedTask, System.Threading.Tasks.Task.FromCanceled, System.Threading.Tasks.Task.FromException, and System.IO.Pipes.NamedPipeClientStream.ConnectAsync. 

## Garbage collector updates

The Garbage Collector now has a no GC region latency mode that attempts to avoid garbage collection during the execution of a critical path if certain memory-related conditions are met. This new mode is important for workloads that require uninterupted computation (at least as it relates to GC CPU use).

The no GC region latency mode enables you to specify a certain amount of memory be available as a pre-requisite to enter a No GC Region. You can specify the amount of memory that must be available for both the small object heap and the large object heap, or you can specify the amount of total memory and the amount to make available for the large object heap. While in the critical region, the GC will not collect. It will start collecting if a collection is explicitly requested (for example, if GC.Collect is called) or if the initially specified memory size is exhausted. 

## Cryptography updates

Previous versions of the .NET Framework used the older version of the Windows cryptography APIs as the basis for the System.Security.Cryptography implementations. In the .NET Framework 4.6, System.Security.Cryptography APIs support the Windows CNG cryptography APIs, which provides modern cryptography algorithms that are important for certain categories of apps. In this release, the team has specifically added support for CNG certificate keys with the System.Security.Cryptography.RSACng class.

## Support for converting DateTime to or from Unix time

New methods have been added to support the conversion of date and time values to or from .NET Framework types and Unix time. This can be necessary, for example, when converting time values between a JavaScript client and .NET server. The following APIs have been added to the DateTimeOffset structure:

- static DateTimeOffset FromUnixTimeSeconds(long seconds)
- static DateTimeOffset FromUnixTimeMilliseconds(long milliseconds)
- long DateTimeOffset.ToUnixTimeSeconds()
- long DateTimeOffset.ToUnixTimeMilliseconds()

## Channel support for managed EventSource instrumentation

You now can use .NET EventSource instrumentation to log significant administrative or operational messages to the event log, in addition to any existing ETW sessions created on the machine.

## Compatibility switches

AppContext is a new compatibility feature that enables library writers to provide a uniform opt-out mechanism for new functionality for their users. It establishes a loosley-coupled contract between components in order to communicate an opt-out request. This capability is typically important when a change is made to existing functionality that defines a new default behavior. 

With AppContext, libraries define and expose compatibility switches, while code that depends on them can set those switches  to affect the library behavior. By default libraries provide the new functionality and only alter it (that is, revert to the old behavior) if the switch is set.

An application (or a library) can declare the value (which is always a Boolean value) of a switch that a dependent library defines. The switch is always implicitly false. Setting the switch to true enables it. Explicitly setting the switch to false provides the new behavior.

	AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException”, true); 

The library must check if a consumer has declared the value of the switch and then act appropriately on it.

	bool shouldThrow;
	
	if (!AppContext.TryGetSwitch(“Switch.AmazingLib.ThrowOnException”, out shouldThrow))
	{
	    // The switch value was not set by the application. 
	    // As a result, the value is 'false'. A false value implies the latest behavior.
	
	    // The library can declare a default value for a switch based on a condition
	    // Example: https://github.com/dotnet/coreclr/blob/master/src/mscorlib/src/System/AppContext/AppContextDefaultValues.Defaults.cs
	}
	
	// The library can use the value of shouldThrow to throw exceptions or not.
	if (shouldThrow)
	{
	    // old code
	}
	else
	{
	    //new code
	}

It's beneficial to use a consistent format for switches, since they are a formal contract exposed by libraries. The following are two obvious formats.

- Switch.namespace.switchname
- Switch.library.switchname

This same infrastructure is used by the .NET Framework internally, to enable developers to opt out of updates to existing functionality.

## Code page encodings in .NET Core

.NET Core primarily supports the Unicode encodings and by default provides limited support for code page encodings. You can add support for code page encodings available in the .NET Framework but unsupported in .NET Core by registering code page encodings with the System.Text.Encoding.RegisterProvider method. For more information, see the documentation for the System.Text.CodePagesEncodingProvider class. 

## Other Base Class Library changes

- A number of collection objects, such as System.Collections.Generic.Queue<T> and System.Collections.Generic.Stack<T>, now implement System.Collections.Generic.IReadOnlyCollection<T>.
- The System.Globalization.CultureInfo.CurrentCulture and System.Globalization.CultureInfo.CurrentUICulture properties are now read-write rather than read-only. If you assign a new System.Globalization.CultureInfo object to these properties, the current thread culture defined by the Thread.CurrentThread.CurrentCulture property and the current UI thread culture defined by the Thread.CurrentThread,CurrentUICulture properties also change.
- The System.Numerics namespace now includes a number of SIMD-enabled types for scientific computing, such as System.Numerics.Matrix3x2, System.Numerics.Matrix4x4, System.Numerics.Plane, System.Numerics.Quaternion, System.Numerics.Vector2, System.Numerics.Vector3, and Vector4T:System.Numerics.Vector4.

## Open-source .NET Framework packages

.NET Core  packages such as the Immutable Collections, SIMD API, and the networking APIs such as those found in the System.Net.Http namespace are now available as open source packages on GitHub. 




