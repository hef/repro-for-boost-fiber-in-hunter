[![Build Status](https://travis-ci.org/hef/repro-for-boost-fiber-in-hunter.svg?branch=master)](https://travis-ci.org/hef/repro-for-boost-fiber-in-hunter)


Repro case for bug reported at: https://github.com/ruslo/hunter/issues/1582


The Problem
===========

when trying to use [hunter](https://github.com/ruslo/hunter) to install boost::fiber  cmake returt

> CMake Error at /Users/travis/.hunter/_Base/Download/Hunter/0.23.34/70287b1/Unpacked/cmake/find/FindBoost.cmake:1247 (message):
>   Unable to find the requested Boost libraries.
> 
>   Boost version: 1.68.0
> 
>   Boost include path:
>   /Users/hef/.hunter/_Base/acbf4b9/9a57913/b499eae/Install/include> 
> 
>   Could not find the following static Boost libraries:
> 
>           boost_fiber
> 
>   Some (but not all) of the required Boost libraries were found.  You may
>   need to install these additional Boost libraries.  Alternatively, set
>   BOOST_LIBRARYDIR to the directory containing Boost libraries or BOOST_ROOT
>   to the location of Boost.
> 

The Solution
============

Add a cmake toolchain file that specifies `set(CMAKE_CXX_STANDARD 11)` or later.

https://docs.hunter.sh/en/latest/overview/customization/toolchain-id.html#simple-toolchains
