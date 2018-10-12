# Copyright (c) 2013, Ruslan Baratov
# All rights reserved.

cmake_minimum_required(VERSION 3.0)
include("cmake/HunterGate.cmake")

HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.23.34.tar.gz"
    SHA1 "70287b1ffa810ee4e952052a9adff9b4856d0d54"
)

project(download-boost)

hunter_add_package(Boost COMPONENTS context fiber)
find_package(Boost CONFIG REQUIRED context fiber)

add_executable(foo foo.cpp)
target_link_libraries(foo PUBLIC Boost::context Boost::fiber)
