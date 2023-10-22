# Compiler params

- `-std=c++20`
- `-stdlib=libc++`
- `-fexperimental-library`
- `-std=c++20 -I "libraries\BigNumber" -I "libraries\cereal-1.3.0\include" -I "libraries\fmt\include" -I "libraries\GSL\include" -I "libraries/multiprecision-Boost_1_81_0/include" -I "libraries\rapidcsv"`

# Libraries

```
-std=c++20 -I "libraries\BigNumber" -I "libraries\cereal-1.3.0\include" -I "libraries\fmt\include" -I "libraries\GSL\include" -I "libraries/multiprecision-Boost_1_81_0/include" -I "libraries\rapidcsv"
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



