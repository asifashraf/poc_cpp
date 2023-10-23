# Windows setup 

Download mingw64 place in c:\tools\mingw64

 then in clion go to Clion > Settings > Build Execution ... > ToolChains >

Then add a new System compiler from + symbol, select mingw

select path and it will automatically detect 

# mac setup

`brew install gcc`

list brew packages

`brew list`

check detail 

`brew ls gcc`

this will show you the compiler path

`/opt/homebrew/Cellar/gcc/13.2.0/bin/c++-13`

then in clion go to Clion > Settings > Build Execution ... > ToolChains > 

Then add a new System compiler from + symbol, give it a name custom

Add new cpp and c compiler , last time path was

`/opt/homebrew/Cellar/gcc/13.2.0/bin/c++-13`

Use regular -I paths and `-std=c++20`

Don't use with mac gcc 
- `-stdlib=libc++`
- `-fexperimental-library`

then run a file > Go to build config , select custom config, -std=c++20 , then add inputs -I in compiler opts

setup working dir to root of project, select file to run. 

# Compiler params

- `-std=c++20`
- `-stdlib=libc++`
- `-fexperimental-library`
- `-I "libraries\BigNumber" -I "libraries\cereal-1.3.0\include" -I "libraries\fmt\include" -I "libraries\GSL\include" -I "libraries/multiprecision-Boost_1_81_0/include" -I "libraries\rapidcsv"`

# Libraries

```
-std=c++20 -I "libraries\BigNumber" -I "libraries\cereal-1.3.0\include" -I "libraries\fmt\include" -I "libraries\GSL\include" -I "libraries/multiprecision-Boost_1_81_0/include" -I "libraries\rapidcsv"
-std=c++20 -stdlib=libc++ -fexperimental-library -I "libraries/BigNumber" -I "libraries/cereal-1.3.0/include" -I "libraries/fmt/include" -I "libraries/GSL/include" -I "libraries/multiprecision-Boost_1_81_0/include" -I "libraries/rapidcsv"
```



# Docker setup 
Start with `start.bat`
, Start interactive with `it.bat`
, Then run `source src.sh`


cl is alias to : `clang++ -std=c++20 -stdlib=libc++ -fexperimental-library -I ../libraries/multiprecision-Boost_1_81_0/include` 

This is how you use it.

```bash

# Compile
cl GeneralNumber.cpp
# Run executable
./a.out  

# Compile, custom output file name
cl GeneralNumber.cpp -o run


```


How to run

```bash

clang++ -std=c++20

```

## VS Include Lib
project -> props -> c/c++ -> general -> additional include dirs



## clion config -> compiler options

Working directory is repo root

-std=c++20 -I "libraries\fmt\include" -I "libraries/multiprecision-Boost_1_81_0/include"

then it will look like  


g++.exe C:\git\poc_cpp\lesson03\fig03_05.cpp -std=c++20 -I C:\git\poc_cpp\libraries\multiprecision-Boost_1_81_0\include -o fig03_05 -g2



