Here's an overview of the main classes and functions in the `<format>` library:

### Classes:

1. **`std::format_error`** : This is an exception class that gets thrown in case of a formatting error.

### Functions:

1. **`std::format`** :
   * Purpose: To produce a formatted string.
   * Usage:
     <pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::string s = std::format(<span class="hljs-string">"Hello, {}!"</span>, <span class="hljs-string">"world"</span>);
     </code></div></div></pre>
2. **`std::vformat`** :
   * Purpose: Similar to`std::format`, but takes a`std::format_args` argument which allows for more advanced formatting scenarios.
3. **`std::formatted_size`** :
   * Purpose: Computes the size that the output of a format operation would have without producing the output.
   * Usage:
     <pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::<span class="hljs-type">size_t</span> size = std::formatted_size(<span class="hljs-string">"Hello, {}!"</span>, <span class="hljs-string">"world"</span>);
     </code></div></div></pre>
4. **`std::format_to`** :
   * Purpose: Writes formatted output to a provided output iterator.
   * Usage:
     <pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::string s;
     std::format_to(std::<span class="hljs-built_in">back_inserter</span>(s), <span class="hljs-string">"Hello, {}!"</span>, <span class="hljs-string">"world"</span>);
     </code></div></div></pre>
5. **`std::format_to_n`** :
   * Purpose: Writes up to a specified number of characters of theformatted output to a provided output iterator.
6. **`std::vformat_to`** and **`std::vformat_to_n`** :
   * Purpose: Similar to`std::format_to` and`std::format_to_n` but takes a`std::format_args` argument.
7. **`std::print`** :
   * Purpose: Prints formatted output to the standard output or other provided streams.
   * Usage:
     <pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::<span class="hljs-built_in">print</span>(<span class="hljs-string">"Hello, {}!\n"</span>, <span class="hljs-string">"world"</span>);
     </code></div></div></pre>
8. **`std::vprint`** :
   * Purpose: Similar to`std::print`, but takes a`std::format_args` argument.

### Format String Syntax:

The `<format>` library uses a new format string syntax that's inspired by Python's format strings. Here's a brief overview:

* **Replacement fields** : Enclosed in`{}`. E.g.,`"{}"`.
* **Field names** : Can use integer indexes or argument names. E.g.,`{0}` or`{name}`.
* **Format specifiers** : Introduced by`:`. E.g.,`{:.2f}` for floating-point numbers with 2 decimal places.
* **Fill and alignment options** : E.g.,`{:<10}` for left-aligning within 10 characters.

### Additional Structures and Utilities:

* `std::format_args`: Represents the set of format arguments.
* `std::format_context`: Represents the formatting context, including the format string, arguments, and the output iterator.
* `std::wformat_args`,`std::wformat_context`: Wide-character equivalents.

It's worth noting that `<format>` offers a significant improvement in terms of type safety and flexibility over older formatting methods. It's strongly recommended to consult the official C++ documentation or other in-depth resources for a deeper understanding of the full capabilities and nuances of the `<format>` library.

Here are examples for the primary functions in the `<format>` library:

1. **`std::format`** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::string s = std::format(<span class="hljs-string">"Hello, {}!"</span>, <span class="hljs-string">"world"</span>);
std::cout << s;  <span class="hljs-comment">// Output: Hello, world!</span>
</code></div></div></pre>

2. **`std::formatted_size`** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::<span class="hljs-type">size_t</span> size = std::formatted_size(<span class="hljs-string">"Hello, {}!"</span>, <span class="hljs-string">"world"</span>);
std::cout << size;  <span class="hljs-comment">// Output: 13 (since "Hello, world!" is 13 characters long)</span>
</code></div></div></pre>

3. **`std::format_to`** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::string result;
std::format_to(std::<span class="hljs-built_in">back_inserter</span>(result), <span class="hljs-string">"The answer is {}."</span>, <span class="hljs-number">42</span>);
std::cout << result;  <span class="hljs-comment">// Output: The answer is 42.</span>
</code></div></div></pre>

4. **`std::format_to_n`** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-type">char</span> buffer[<span class="hljs-number">20</span>];
<span class="hljs-keyword">auto</span> [end, count] = std::format_to_n(buffer, <span class="hljs-number">10</span>, <span class="hljs-string">"Pi is approx. {}"</span>, <span class="hljs-number">3.14159</span>);
*end = <span class="hljs-string">'\0'</span>;  <span class="hljs-comment">// Null terminate the string</span>
std::cout << buffer;  <span class="hljs-comment">// Output: Pi is app (because of the limit of 10 characters)</span>
</code></div></div></pre>

5. **`std::print`** :

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp">std::<span class="hljs-built_in">print</span>(<span class="hljs-string">"Pi is approx. {:.2f}\n"</span>, <span class="hljs-number">3.14159</span>);  <span class="hljs-comment">// Output: Pi is approx. 3.14</span>
</code></div></div></pre>

6. **`std::vformat`** ,**`std::vformat_to`** ,**`std::vformat_to_n`** , and**`std::vprint`** :
   These functions take a`std::format_args` argument and are typically used in more advanced scenarios when forwarding a variable number of arguments or when constructing custom formatting functions. Here's an example with`std::vformat`:

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-keyword">template</span> <<span class="hljs-keyword">typename</span>... Args>
<span class="hljs-function">std::string <span class="hljs-title">custom_format</span><span class="hljs-params">(<span class="hljs-type">const</span> std::string& fmt, Args... args)</span> </span>{
    <span class="hljs-keyword">auto</span> format_args = std::<span class="hljs-built_in">make_format_args</span>(args...);
    <span class="hljs-keyword">return</span> std::<span class="hljs-built_in">vformat</span>(fmt, format_args);
}

std::cout << <span class="hljs-built_in">custom_format</span>(<span class="hljs-string">"Hello, {}!"</span>, <span class="hljs-string">"world"</span>);  <span class="hljs-comment">// Output: Hello, world!</span>
</code></div></div></pre>

These examples provide a basic introduction to the usage of each function. The `<format>` library has numerous features, like custom format specifiers, fill and alignment options, and more. For more advanced usage or details, refer to the official documentation.


```c
cout << format("Initial principal: {:>7.2f}\n", principal)
        << format("    Interest rate: {:>7.2f}\n", rate);
```

**`{:>7.2f}`** : This is a replacement field with a format specification for the value that will replace it.

* **`{}`** : The curly braces`{}` define a placeholder for a value.
* **`:>`** : The colon`:` introduces the format specification. The`>` after it specifies right alignment.
* **`7`** : Specifies a width of 7 characters for the printed value. This means that if the value to be printed has fewer than 7 characters, spaces will be added (to the left due to right alignment) to ensure that the printed value occupies a width of 7 characters.
* **`.2f`** : Specifies that the value should be formatted as a floating-point number with 2 digits after t
