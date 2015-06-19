<properties
    pageTitle=".NET Core "
    description="The open-source .NET Core brings everything you need to run .NET code on multiple server platforms, including Windows, Linux, and Mac OS X. Developers can also run .NET inside Docker containers on Linux."
    slug="netcore"
    order="100"    
    keywords="visual studio, vs2015, vs, visualstudio, cross-platform, server, linux, windows, .NET, .NET core"
/>

.NET Core is a version of .NET for modern device and cloud workloads. It provides a single set of APIs for you to use for your apps. .NET has always offered low-level code portability as a fundamental tenet, and now has a uniform API that can be used in multiple app types. You don't need to rely on other code sharing techniques to target multiple app platforms, such as portable libraries and shared projects. 

With .NET Core, developers can build ASP.NET MVC, Web API, and Web Pages (Razor) on multiple platforms, making ASP.NET truly a cross-platform server technology for building websites on all deployment environments.

Developers can now install the .NET Core support for Linux and Mac OS X, start an evaluation, and get involved in the [associated open source project](https://github.com/dotnet/core/blob/master/README.md), overseen by the .NET Foundation.


## Focus and Value of .NET Core

The focus and value of .NET Core is three-part: deployment, open source and cross-platform. We want to provide a version of .NET that you can use where you want and upgrade it when you want. You can use it on-premise, in Microsoft Azure as well as other cloud providers. You can use it on Windows, Linux or Mac. You can upgrade your apps (including .NET Core itself) to meet your business needs, independent of other apps that are running on a machine. You can modify .NET Core to support new scenarios or add features, and contribute those changes to .NET Core on GitHub.

.NET Core is very much in the same family as the .NET Framework. For example, the SIMD and Immutable Collections NuGet packages work on both the .NET Framework and .NET Core, by design. You can expect that most aspects of your development experience will be unchanged when targeting .NET Core. .NET Core has some great characteristics, but it should be considered an evolution of what we’ve been doing with the .NET Framework. With that in mind, we chose an evolutionary approach for versioning .NET Core, which is why it is version 5, the next whole number after 4.6, the latest version of the .NET Framework.

ASP.NET 5 is the first workload that has adopted .NET Core. ASP.NET 5 runs on both the .NET Framework and .NET Core. A key value of ASP.NET 5 is that it can run on multiple versions of .NET Core 5 on the same machine. Website A and website B can run on two different versions of .NET Core on the same machine, or they can use the same version. It’s up to you. Due to its smaller footprint, there are also some performance benefits that are specific to .NET Core, however, most of the ASP.NET 5 performance benefits apply to both the .NET Framework and .NET Core.

.NET Core has two major components. It includes a small runtime that is built from the same codebase as the .NET Framework CLR. The .NET Core runtime includes the same GC and JIT (RyuJIT), but doesn’t include features like Application Domains or Code Access Security. The runtime is delivered via NuGet, as part of the ASP.NET 5 core package.

.NET Core also includes the base class libraries. These libraries are largely the same code as the .NET Framework class libraries, but have been factored (removal of dependencies) to enable us to ship a smaller set of libraries. These libraries are shipped as System.* NuGet packages on NuGet.org.

As we update core components like the GC, JIT and base class libraries, we intend to include those improvements in both the .NET Framework and .NET Core. The use cases for those components are the same in both cases, as is the need for regular improvement. The .NET Core NuGet libraries will follow a similar pattern, running on the latest versions of the .NET Framework and the .NET Core runtime.

## .NET Core for Device and Cloud

Today, the [.NET Core Framework](https://github.com/dotnet/corefx) can be used in ASP.NET 5, Windows 10 apps and .NET Core console apps. The .NET Core API started as the API for Windows 8 Store Apps. It has since grown, both in terms of APIs exposed and to also include other scenarios such as ASP.NET 5 apps. Now, when we add new APIs to .NET Core, they are available for multiple app types at once. This approach makes better use of our engineering time and provides you with a consistent API right away.

All of the .NET Core libraries are distributed as NuGet packages. You can acquire the packages easily within Visual Studio or with one of the NuGet clients directly.

### Self-contained and Efficient

Another major benefit of .NET Core is that it can ship as part of your app. This means that your app is self-contained, with a set of fixed binaries, which includes the .NET Core Framework and runtime. This ensures that your app is unaffected by system updates or other apps that might be updating on the same machine. Your app can also be updated without affecting any other apps. This is especially important for Windows 10 Universal Apps -- where you build and publish a single application that can run consistently on all devices (Tablet, Phone, Desktop, HoloLens, Xbox, IoT, etc). This approach also ensures that new features in .NET Core and C# language improvements are consistently available for you to pick and choose to use across all these environments.

Apps often rely on many .NET Core libraries, such that a lot of self-contained apps might seem like too much of a good thing. This is particularly important for constrained device environments. .NET Native solves this problem by optimizing apps to include only the code that a given app relies on. If you only rely on one type within an assembly, that's the only type that will be retained in your final app. .NET Native has other optimizations that further slim down your overall app.

.NET Native is currently scoped to Windows 10 Universal apps, however, it is intended to fit in as a deployment option for .NET Core apps generally.

### Cross-Platform

.NET Core supports Windows, OS X and Linux. You can write Universal apps on Windows 10 and ASP.NET 5 and Console apps on all of the three OSes. FreeBSD support is in progress, [led by the .NET open source community](https://github.com/dotnet/coreclr/issues?q=label%3AFreeBSD+is%3Aclosed). We expect that the community will create other OS ports. In fact, the OS X port has also been community led.

.NET Core supports x86, x64 and ARM CPUs in order to support device, cloud and console app scenarios. We expect that to see more chips come online, particularly given the [LLILC](https://github.com/dotnet/llilc) LLVM integration project. LLILC will (in theory) make it possible to port .NET Core to all of the chips that LLVM supports.


### PartsUnlimited

PartsUnlimited is a demo of a .NET Core app, using ASP.NET 5, that runs on Linux, OS X and Windows.

Parts Unlimited is an ecommerce app for a ficticious company, based on a website of the same name in The Phoenix Project. The website includes product listings by category, product details, shopping cart, order history, product recommendations, search, and more.

Both the demo and .NET Core are under development. The [master branch](https://github.com/microsoft/partsunlimited) of the repo supports .NET Core and ASP.NET 5 beta 4, and runs on Windows. The [beta 5 branch](https://github.com/microsoft/partsunlimited/tree/dev/beta5) supports .NET Core and ASP.NET 5 beta 5 and runs on Windows, OS X and Linux. You can try out both branches, although you may encounter a beta 5 build that doesn't work as expected.

Key Features:
- Works with Visual Studio 2015
- ASP.NET 5 support for Linux and Mono
- Includes a Dockerfile and sample publishing profile to publish to a Docker container
- Entity Framework code-first using SQL Azure or an in-memory database (Mono)
- Includes Azure RM JSON templates and PowerShell automation scripts to easily build and provision your environment

## .NET Execution Environment (DNX)

The [.NET Execution Environment (DNX)](https://github.com/aspnet/dnx) is a new .NET SDK that provides a consistent development and execution environment across multiple platforms (Windows, OS X, Linux, ...), multiple CPUs (x86, x64, ...) and across different .NET flavors (.NET Framework, .NET Core and Mono). It enables you to build a single app that can work across that breadth of options and is also easy to build with either text editors or full IDEs.

DNX provides the following benefits:
- Create single application that can work on multiple operating without cross compiling (Windows, Mac, Linux)
- Create applications that can run from source without a build step enabling development with just simple text editors (Sublime, Emacs, VIM, Visual Studio Code).
- Enables debugging from source for referenced NuGet packages.
- Straightforward acquisition of .NET runtimes (e.g. .NET Core).
- Manage multiple .NET runtimes on a single machine both globally or app centric including security updates.
- Supports ASP.NET 5 and .NET Core console app workloads.

DNX is a general .NET Core concept and facility. It's the easiest way to acquire and use the new open source and cross-platform version of .NET. It started life in the ASP.NET 5 project and has gone through several renames over the past few months (was called 'KRE' before), but that's purely historical.

Note: DNX is not the only SDK for .NET Core. .NET Native, for example, is another one.

### DNX Tools and Concepts

There are several pieces to DNX:
- DNX (distribution): A distribution (a NuGet package) of the components that are the implementation of the new environment.
   - The .NET Core DNX distribution includes CoreCLR and the base parts of CoreFX.
   - The .NET Framework and Mono DNX distribution only contain the DNX components.
- DNVM: A tool for aquiring and managing DNX distributions. Not part of DNX itself, since it plays an admistrator role for DNX.
- DNU: The NuGet client for DNX. NuGet.exe is not used.
- DNX (commandline tool): A eponymously named tool that controls various app operationals, primarly launching.

### Using DNX

DNX is the easy way to both acquire and use .NET Core for development and testing. It's great to use, particularly for the scenario where you SSH into a terminal on Linux and want to quickly acquire a version of .NET and start using it within a minute.

In a typical workflow, you do the following (each of which is a simple command):
- Acquire DNVM.
- Acquire the desired runtime flavor (e.g. X64 .NET Core for OS X) with DNVM.
- Write or git clone app source, using DNX concepts (e.g. project.json).
- Restore packages for the app, using DNU (part of the DNX distribution).
- Launch app from source: dnx . run.

You can learn how to try DNX yourself, with the following instructions:
- [ASP.NET 5 apps](https://github.com/aspnet/home)
- [.NET Core console apps](https://github.com/dotnet/coreclr/blob/master/README.md#get-net-core)



