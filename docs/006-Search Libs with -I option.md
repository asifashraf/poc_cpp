The `-I` option in `g++` (and many other compilers) specifies directories where the compiler should look for header files. This is a way to add search paths beyond the default ones.

When you provide an `-I` followed by a directory, you're telling the compiler to add that directory to the list of directories it searches when it encounters an `#include` directive in the code.

For example, if you have:

<pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>cpp</span><button class="flex ml-auto gizmo:ml-0 gap-2 items-center"><svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" class="icon-sm" height="1em" width="1em" xmlns="http://www.w3.org/2000/svg"><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path><rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect></svg>Copy code</button></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-cpp"><span class="hljs-meta">#<span class="hljs-keyword">include</span> <span class="hljs-string">"fmt/core.h"</span></span>
</code></div></div></pre>

And you've specified `-I libs/fmt/include`, the compiler will look for `core.h` in `libs/fmt/include/fmt/`.

However, here are some nuances and rules:

1. **Relative vs. Absolute Paths** : You can provide either relative paths (relative to the directory from which you're invoking the compiler) or absolute paths.
2. **No Recursive Search** : The compiler does not search recursively inside deep subfolders. You would have to specify additional `-I` flags for each directory you want to be searched.
3. **Order Matters** : If there are multiple directories specified using multiple `-I` options, the compiler searches them in the order they're provided. This is important if there are header files with the same name in multiple directories.
4. **Angle Brackets vs. Double Quotes** :
   * When you use`#include "header.h"`, the compiler first looks in the directory of the file containing the directive, and then in the directories of any files that include that file, and so forth. If it doesn't find the header using this approach, it then searches in the directories specified by`-I` options.
   * When you use`#include <header.h>`, the compiler searches only in the standard system directories and the directories specified by`-I` options. It doesn't look in the directory of the current source file.

In conclusion, the `-I` option is a way to extend the list of directories the compiler checks when it looks for header files. If you're organizing your project or using third-party libraries that aren't installed in standard system directories, the `<msreadoutspan class="msreadout-line-highlight msreadout-inactive-highlight">-I</msreadoutspan>` option becomes essential.
