Building shared libraries (like `.dll`, `.dylib`, and `.so`) involves compiling your C++ code into a format that can be dynamically linked at runtime by other programs or libraries. The exact steps and compiler flags vary based on the compiler and platform you're targeting.

Here's a basic guide on how to create shared libraries for various platforms using the GCC and Clang compilers:

### 1. Linux (`.so`):

**Source Code** (`library.cpp`):

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#<span class="hljs-keyword">include</span> <span class="hljs-string">"library.h"</span></span>

<span class="hljs-function"><span class="hljs-type">int</span> <span class="hljs-title">add</span><span class="hljs-params">(<span class="hljs-type">int</span> a, <span class="hljs-type">int</span> b)</span> </span>{
    <span class="hljs-keyword">return</span> a + b;
}
</code></div></div></pre>

**Header** (`library.h`):

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#<span class="hljs-keyword">pragma</span> once</span>

<span class="hljs-function"><span class="hljs-type">int</span> <span class="hljs-title">add</span><span class="hljs-params">(<span class="hljs-type">int</span> a, <span class="hljs-type">int</span> b)</span></span>;
</code></div></div></pre>

**Compilation** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">g++ -shared -fPIC library.cpp -o libexample.so
</code></div></div></pre>

### 2. Windows (`.dll`):

**Source Code** (`library.cpp`):

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#<span class="hljs-keyword">include</span> <span class="hljs-string">"library.h"</span></span>

__declspec(dllexport) <span class="hljs-function"><span class="hljs-type">int</span> <span class="hljs-title">add</span><span class="hljs-params">(<span class="hljs-type">int</span> a, <span class="hljs-type">int</span> b)</span> </span>{
    <span class="hljs-keyword">return</span> a + b;
}
</code></div></div></pre>

**Header** (`library.h`):

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#<span class="hljs-keyword">pragma</span> once</span>

__declspec(dllexport) <span class="hljs-function"><span class="hljs-type">int</span> <span class="hljs-title">add</span><span class="hljs-params">(<span class="hljs-type">int</span> a, <span class="hljs-type">int</span> b)</span></span>;
</code></div></div></pre>

**Compilation** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">g++ -shared library.cpp -o example.dll
</code></div></div></pre>

### 3. macOS (`.dylib`):

**Source Code** (`library.cpp`):
Same as the Linux example.

**Header** (`library.h`):
Same as the Linux example.

**Compilation** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>bash</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">g++ -shared -fPIC library.cpp -o libexample.dylib
</code></div></div></pre>

### Notes:

* The`-shared` flag tells the compiler to produce a shared object.
* The`-fPIC` (Position Independent Code) flag is necessary for creating shared libraries on some platforms, particularly on Linux. It ensures the code does not rely on being loaded at a specific memory address.
* In the Windows example,`__declspec(dllexport)` is used to specify which functions or classes are exported from the DLL and can be used by other programs. When importing from the DLL in another program, you would use`__declspec(dllimport)`.

Once you've built your shared library, other programs can link against it. When distributing the shared library, ensure that it's available in the appropriate search paths at runtime, or you might encounter "library not found" errors.
