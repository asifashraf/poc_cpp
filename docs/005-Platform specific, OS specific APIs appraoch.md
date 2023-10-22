### 1. Windows:

To use the Windows API:

1. **Include Necessary Headers** : Windows APIs are available through a set of headers provided by the Windows SDK. For instance, you'd use `#include <windows.h>` for many general-purpose APIs.
2. **Linking** : Depending on what you're doing, you may need to link against specific libraries. This can be done using a directive like `#pragma comment(lib, "user32.lib")`, or specifying the library in the linking phase in your build tool.

Example: Creating a message box using Windows API:

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#<span class="hljs-keyword">include</span> <span class="hljs-string"><windows.h></span></span>

<span class="hljs-function"><span class="hljs-type">int</span> <span class="hljs-title">main</span><span class="hljs-params">()</span> </span>{
    <span class="hljs-built_in">MessageBox</span>(<span class="hljs-literal">NULL</span>, <span class="hljs-string">"Hello, World!"</span>, <span class="hljs-string">"Hello"</span>, MB_OK);
    <span class="hljs-keyword">return</span> <span class="hljs-number">0</span>;
}
</code></div></div></pre>

For COM or Windows Runtime, you'd need to initialize the COM library, use interfaces, and understand reference counting, among other things.

### 2. macOS:

To use Cocoa:

1. **Include Objective-C++** : If you're integrating Objective-C with C++, name your source files with a `.mm` extension, which indicates Objective-C++ to the compiler.
2. **Framework Linking** : Link against necessary frameworks using your build system (e.g., Xcode).

Example: Creating an alert using Cocoa from C++:

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#import <span class="hljs-string"><Cocoa/Cocoa.h></span></span>

<span class="hljs-function"><span class="hljs-type">int</span> <span class="hljs-title">main</span><span class="hljs-params">()</span> </span>{
    [NSApplication sharedApplication];
    NSAlert *alert = [[[NSAlert alloc] init] autorelease];
    [alert setMessageText:@<span class="hljs-string">"Hello, World!"</span>];
    [alert runModal];
    <span class="hljs-keyword">return</span> <span class="hljs-number">0</span>;
}
</code></div></div></pre>

### 3. Linux:

To use X11:

1. **Install Dev Package** : Install the developer package for X11, e.g., `sudo apt-get install libx11-dev` on Debian-based systems.
2. **Include & Link** : Include necessary headers and link against required libraries.

Example: Opening a simple window using X11:

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#<span class="hljs-keyword">include</span> <span class="hljs-string"><X11/Xlib.h></span></span>

<span class="hljs-function"><span class="hljs-type">int</span> <span class="hljs-title">main</span><span class="hljs-params">()</span> </span>{
    Display *display = <span class="hljs-built_in">XOpenDisplay</span>(<span class="hljs-literal">NULL</span>);
    Window window = <span class="hljs-built_in">XCreateSimpleWindow</span>(display, <span class="hljs-built_in">RootWindow</span>(display, <span class="hljs-number">0</span>), <span class="hljs-number">0</span>, <span class="hljs-number">0</span>, <span class="hljs-number">200</span>, <span class="hljs-number">200</span>, <span class="hljs-number">1</span>, <span class="hljs-built_in">BlackPixel</span>(display, <span class="hljs-number">0</span>), <span class="hljs-built_in">WhitePixel</span>(display, <span class="hljs-number">0</span>));
    <span class="hljs-built_in">XMapWindow</span>(display, window);
    <span class="hljs-built_in">XFlush</span>(display);
    <span class="hljs-built_in">sleep</span>(<span class="hljs-number">10</span>);  <span class="hljs-comment">// Keep window open for 10 seconds</span>
    <span class="hljs-keyword">return</span> <span class="hljs-number">0</span>;
}
</code></div></div></pre>

When linking, you'd need `-lX11`.

### Tips:

1. **Encapsulation** : Whenever possible, encapsulate platform-specific logic inside separate classes or functions. This keeps the majority of your codebase platform-agnostic and makes it easier to manage and extend.
2. **Documentation** : Always refer to platform-specific documentation. For instance, MSDN for Windows, Apple's developer documentation for macOS, and man pages or library-specific docs on Linux.
3. **Build Systems** : Modern build systems like CMake make it easier to handle platform-specific conditions, dependencies, and linking.

To actually perform the tasks of controlling the local OS environment, processes, running processes, and platform management, you'd dive deeper into each platform's API documentation and explore available functions, classes, and methods for the operations you're interested in. Each platform offers rich APIs to interact with system-level functionalities.
