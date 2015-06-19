<properties
    pageTitle="Visual C++"
    description="Updates for Visual Studio 2015 include C++11 and C++14 standards, some C++17 features, with faster builds, code generation, and security enhancements."
    slug="languages_cpp"
    order="510"    
    keywords="visual studio, vs2015, vs, visualstudio, languages, C++"
/>

## Language Features

The following features bring the compiler closer to standard C++:

- **Resumable Functions (resume/await):** The resume and await keywords provide language-level support for asynchronous programming and enables resumable functions. Currently, this feature is only available for x64 targets. *Proposed for C++17* [N3858]
- **Generic (Polymorphic) Lambda Expressions:** Lambda function parameter types can be specified using auto; the compiler interprets auto in this context to mean that the closure's function call operator is a member function template and that each use of auto in the lambda expression corresponds to a distinct template type parameter. *C++14*
- **Generalized Lambda Capture Expressions:** Also known as init-capture. The result of an arbitrary expression can be assigned to a variable in the capture clause of a lambda. This enables move-only types to be captured by value and enables a lambda expression to define arbitrary data members in its closure object. *C++14*
- **Binary Literals:** Binary literals are prefixed with 0B or 0b and consist of only the digits 0 and 1. *C++14*
- **Return Type Deduction:** The return type of normal functions can be deduced, including functions with multiple return statements and recursive functions. Such function definitions are preceded by the auto keyword as in function definitions with a trailing return type, but the trailing return type is omitted. *C++14*
- **decltype(auto):** Type deduction using the auto keyword for initializing expressions strips ref-qualifiers and top-level cv-qualifiers from the expression. decltype(auto) preserves refand cv-qualifiers and can now be used anywhere that auto can be used, except to introduce a function with an inferred or trailing return type. *C++14*
- **Implicit Generation of Move Special Member Functions:** Move constructors and move assignment operators are implicitly generated when conditions allow, thus bringing the compiler into full conformance with C++11 rvalue references. *C++11*
- **Inheriting Constructors:** A derived class can specify that it will inherit the constructors of its base class, Base, by including the statement using Base::Base; in its definition. A deriving class can only inherit all the constructors of its base class, there is no way to inherit only specific base constructors. A deriving class cannot inherit from multiple base classes if they have constructors that have an identical signature, nor can the deriving class define a constructor that has an identical signature to any of its inherited constructors. *C++11*
- **Alignment Query and Control:** The alignment of a variable can be queried by using the alignof() operator and controlled by using the alignas() specifier. alignof() returns the byte boundary on which instances of the type must be allocated; for references it returns the alignment of the referenced type, and for arrays it returns the alignment of the element type. alignas() controls the alignment of a variable; it takes a constant or a type, where a type is shorthand for alignas (alignof(type)). *C++11*
- **Extended sizeof:** The size of a class or struct member variable can be determined without an instance of the class or struct by using sizeof(). *C++11*
- **constexpr:** Partial support for C++11 constexpr. *C++11* (partial)
- **User-Defined Literals (UDLs):** Meaningful suffixes can be appended to numeric and string literals to give them specific semantics. The compiler interprets suffixed literals as calls to the appropriate UDL-operator. *C++11*
- **Thread-Safe "Magic" Statics:** Static local variables are initialized in a thread-safe way, eliminating the need for manual synchronization. Only initialization is thread-safe, use of static local variables by multiple threads must still be manually synchronized. The thread-safe statics feature can be disabled by using the /Zc:threadSafeInitflag to avoid taking a dependency on the CRT. *C++11*
- **Thread-Local Storage:** Use the thread_local keyword to declare that an independent object should be created for each thread. *C++11*
- **noexcept:** The noexcept operator can be used to check whether an expression might throw an exception. The noexcept specifier can be used to specify that a function does not throw exceptions. *C++11*
- **Inline Namespaces:** A namespace can be specified as inline to hoist its contents into the enclosing namespace. Inline namespaces can be used to create versioned libraries that expose their most-recent version by default, while still making previous API versions available explicitly. *C++11*
- **Unrestricted Unions:** A Union type can contain types with non-trivial constructors. Constructors for such unions must be defined. *C++11*
- **New Character Types and Unicode Literals:** Character and string literals in UTF-8, UTF-16, and UTF-32 are supported and new character types char16_t and char32_t have been introduced. Character literals can be prefixed with u8 (UTF-8), u (UTF-16), or U (UTF-32) as in U'a', while string literals can additionally be prefixed with raw-string equivalents u8R (UTF-8 raw-string), uR (UTF-16 raw-string), or UR (UTF-32 raw-string). Universal character names can be freely used in unicode literals as in u'\u00EF', u8"\u00EF is i", and u"\U000000ef is I". *C++11*
- **__func__:** The predefined identifier __func__ is implicitly defined as a string that contains the unqualified and unadorned name of the enclosing function. *C++11*
- **__restrict:**  __restrict can be applied to references.
- **Typename keyword:** Users can write typename instead of class in a template template parameter. *C++14*
- The globals **void operator delete(void *, std::size_t) noexcept** and **void operator delete[](void *, std::size_t) noexcept** can be overloaded. *C++14*
- **Digit separators:** You can intersperse numerical literals with single quotes to make them more readable. For example, int x = 1'000'000;. *C++14*
- **Universal character names in literals:** You can write basic characters, like 'A' and the line feed character, as code points in literals. For example, const char *s = "\u0041\u000A";. *C++11*

## Library Features

- **User-Defined Literals (UDLs) for Standard Library Types:** The <chrono>, <string>, and <complex> headers  provide UDL-operators for your convenience. For example, 123ms means std::chrono::milliseconds(123), "hello"s means std::string("hello"), and 3.14i means std::complex(0.0, 3.14).
- **Creation of null forward iterators:** These are forward iterators that do not refer to a container instance. Such iterators are value-initialized and compare equal for a particular container type. Comparing a value-initialized iterator to one that is not value-initialized is undefined. *C++14*
- **quoted():** The quoted() function makes working with quoted string values and I/O easier. With quoted(), an entire quoted string is treated as a single entity (as strings of non-whitespace characters are in I/O streams); in addition, escape sequences are preserved through I/O operations. *C++14*
- **Heterogeneous associative lookup functions for associative containers:** Such functions enable lookup by types other than the key_type as long as the type is comparable to key_type. *C++14*
- **Compile-time integer_sequence type:** Represents a sequence of integer values that can be evaluated at compile time to make working with parameter packs easier and to simplify certain template programming patterns. *C++14*
- **std::exchange():** This utility funciton assigns a new value to an object and returns its old value. For complex types, exchange() avoids copying the old value when a move constructor is available, avoids copying the new value if it’s a temporary or is moved, and accepts any type as the new value taking advantage of any converting assignment operator. *C++14*
- **Dual-Range overloads for equal(), is_permutation(), mismatch():** These overloads check that the two sequences are the same length, which removes this responsibility from the calling code; for sequences that don't support the requirements of a random iterator, these overloads check the length while comparing elements, which is more efficient. *C++14*
- **get<T>() template function:** Allows tuple elements to be addressed by their type. If a tuple contains two or more elements of the same type get<T>() the tuple can't be addressed by that type, but other uniquely-typed elements can still be addressed. *C++14*
- **tuple_element_t<I, T> type alias:** This is an alias for typename tuple_element<I, T>::type, providing some convenience for template programmers similar to the other metafunction type aliases in <type_traits>.  *C++14*
- **File System "V3" Technical Specification:** The included implementation of the File System Technical Specification has been updated to version 3 of the specification. [N3940]
- **Minimal allocator interface throughout:** Notable fixes include std::function, shared_ptr, allocate_shared(), and basic_string. *C++11*
- **<chrono>:** The chrono types high_resolution_clock and steady_clock have been fixed. *C++11*

## Faster Builds
 
- **Incremental Link-Time Code Generation (LTCG):** Incremental linking can be used together with LTCG to decrease link times of applications using LTCG. Activate this feature by using the /LTCG:incremental and /LTCG:incremental_rebuild linker switches
- **Incremental Linking for Static Libraries:** Changes to static libraries that are referenced by other code modules link incrementally.
- **/Debug:FastLink** substantially decreases link times by using new PDB creation techniques.
- **Algorithmic improvements** decrease link times. 
- **Faster builds for template-heavy code**
- **Fast Profile Guided Optimization (PGO) Instrumentation** A lightweight instrumentation mode for games and real-time systems has been introduced in PGO. Together with other  features made available through the /GENPROFILE and /FASTGETPROFILE linker switches you can now balance code quality and build speed when using PGO.
- **Object file size reduction Compiler and C++ standard library enhancements** result in significantly smaller object files and static libraries. These enhancements do not affect the size of dynamically-linked libraries (DLLs) or executables (EXEs) because the redundant code has historically been removed by the linker.

## Performance and Code Quality

- **Improvements to automatic vectorization:** Visual Studio 2015 improves vectorization of control flow (if-then-else), vectorization when compiling under /O1 (Minimize size), and improves the vector code quality overall, including support for the Parallel STL, vectorizing more range-based for loops, and support for #pragma loop(ivdep).
- **Improvements to scalar optimization:** Results in better code generation of bit-test operations, control flow merging and optimizations (loop-if switching), and other scalar optimizations (for example, better code generation for std::min and std::max).
- **Profile Guided Optimization (PGO):** Enhancements to PGO include improved reference sets, better data layout capabilities, and the ability to reuse previously made inlining, speed vs. size, and layout decisions.
- **Control Flow Guard (CFG):** By adding a new option to your project, the Visual C++ compiler injects extra security checks into your binaries to help detect attempts to hijack your code. When the check fires, it stops execution of your code before a hijacker can do damage to your data or PC.
- **Updated command options:** Instead of using the /d2guard4 switch as you did in earlier releases, you should use /guard:cf. 


## Productivity, Debugging, and Diagnostics

- ** Refactoring support:** 
   - *Rename Symbol:* Changes all occurrences of a symbol to a new name.
   - *Function Extraction:* Move selected code into its own function. This refactoring is available as an extension to Visual Studio on the Visual Studio Gallery.
   - *Implement Pure Virtuals:* Generates function definitions for pure virtual functions inherited by a class or structure. Multiple and recursive inheritance are supported. Activate this refactoring from the inheriting class definition to implement all inherited pure virtual functions, or from a base class specifier to implement pure virtual functions from that base class only.
   - *Create Declaration or Definition:* Generates a declaration from an existing definition or a default definition from an existing declaration. Access this refactoring from the existing declaration or definition, or from the LightBulb indicator.
   - *Move Function Definition:* Moves the body of a function between the source code and header files. Activate this refactoring from the function's signature.
   - *Convert to Raw String Literal:* Converts a string containing escape sequences into a raw-string literal. Supported escape sequences are \n (new line), \t (tab), \' (single quote), \" (double quote), and \? (question mark). Activate this feature by right-clicking anywhere inside a string.
- **Program Database (PDB) enhancements:**
   - *Improved solution Scanning speed*, especially for large solutions. 
   - Operations like Go To Definition are not blocked during solution scan except during the initial solution scan when a new solution is opened for the first time. 
- **Find in Files** enables subsequent results to be appended to previous results; accumulated results can be deleted.
- **IntelliSense Readability Improvements:** Complex template instantiations and typedefs are simplified in parameter help and quickinfo to make them easier to read.
- **Debugger Visualizations in C++:** Add Natvis debugger visualizations to your Visual Studio project for easy management and source control integration. Natvis files added to a project take evaluation precedence over Natvis visualizers outside the project. For more information, see Create custom views of native objects in the debugger. You can also use Natvis files while debugging C++ on Android. The debugger includes visualizations for many common templates, and supports loading custom files that are added to the C++ project.
- **Native Memory Diagnostics:** 
   - *Memory diagnostic sessions* (Alt+F2) enable you to monitor the live memory use of your native application.
   - *Memory snapshots* capture a momentary image of your application's heap contents. Differences in heap state can be examined by comparing two memory snapshots. View object types, instance values, and allocation call stacks for each instance after stopping the application.
- **Improved deadlock detection and recovery** when calling C++ functions from the Watch and Immediate windows.
- **Improved compiler diagnostics:** The compiler provides enhanced warnings about suspicious code. New warnings have been added (for example, shadowed variables and mismatched printf format-strings). Existing warning messages have been made clearer.
- **The /Wv flag:** Warnings introduced after a specific compiler version XX.YY.ZZZZ can be disabled by using the /Wv:XX.YY.ZZZZ flag. Other warnings can be specifically disabled in addition to those specified through the /Wv flag.
- **Improved Support for Debugging Optimized Code:** Debug code with the /Zi, /Zo, or /Z7 flags enabled.
- **Graphics Diagnostics:** 
   - *Consecutive Capture:* Capture up to 30 consecutive frames with one capture.
   - *Programmatic Capture:* Initiate frame capture programmatically. Programmatic capture is especially useful for debugging compute shaders in programs that never call Present, or when a rendering problem is difficult to capture manually but can be predicted programmatically from the state of the app at runtime.
   - *Enhanced Graphics:* Event List A new Draw Calls view is added which displays captured events and their state in a hierarchy organized by Draw Calls. You can expand draw calls to display the device state that was current at the time of the draw call and you can further expand each kind of state to display the events that set their values.
   - *Support for Windows Phone 8.1:* Graphics Diagnostics now fully supports debugging Windows-apps in Phone emulator or on tethered Phone.
   - Graphics Frame Analysis This tool collects performance measurements on captured frames; in addition it also performs a set of pre-defined experiments which provides insights into how performance would be affected when various texture techniques are applied. Frame Analysis also collects performance counters from hardware.
   - *Dedicated UI for Graphics Analysis:* The new Visual Studio Graphics Analyzer window is a dedicated workspace for analyzing graphics frames.
   - *Shader Edit and Apply:* View the impact of shader code changes in a captured log without re-running the app.
   - *Configure capture options* in Tools->Options->Graphics Diagnostics.
   - Command-line tool for *capturing and playing back frames*.
   - *Graphics Diagnostics support for DirectX 12:* Supports debugging rendering problems in DirectX 12 applications.
- **New GPU Usage tool:** Helps you understand GPU usage of DirectX applications. Frame Time, Frame Rate, and GPU Utilization graphs are available while the applications are running live. In addition, by collecting and analyzing detailed GPU usage data, this tool can provide insights into the CPU and GPU execution time of individual DirectX events, and therefore can be useful to determine whether the CPU or GPU is the performance bottleneck. 
