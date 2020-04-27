cmake_minimum_required(VERSION 3.10)
project(lua)

set(CMAKE_CXX_STANDARD 98)

add_library(lua STATIC
        src/lapi.cpp
        src/lapi.h
        src/lauxlib.cpp
        src/lauxlib.h
        src/lbaselib.cpp
        src/lbitlib.cpp
        src/lcode.cpp
        src/lcode.h
        src/lcorolib.cpp
        src/lctype.cpp
        src/lctype.h
        src/ldblib.cpp
        src/ldebug.cpp
        src/ldebug.h
        src/ldo.cpp
        src/ldo.h
        src/ldump.cpp
        src/lfunc.cpp
        src/lfunc.h
        src/lgc.cpp
        src/lgc.h
        src/linit.cpp
        src/liolib.cpp
        src/llex.cpp
        src/llex.h
        src/llimits.h
        src/lmathlib.cpp
        src/lmem.cpp
        src/lmem.h
        src/loadlib.cpp
        src/lobject.cpp
        src/lobject.h
        src/lopcodes.cpp
        src/lopcodes.h
        src/loslib.cpp
        src/lparser.cpp
        src/lparser.h
        src/lprefix.h
        src/lstate.cpp
        src/lstate.h
        src/lstring.cpp
        src/lstring.h
        src/lstrlib.cpp
        src/ltable.cpp
        src/ltable.h
        src/ltablib.cpp
        src/ltm.cpp
        src/ltm.h
        src/lua.h
        src/luaconf.h
        src/lualib.h
        src/lundump.cpp
        src/lundump.h
        src/lutf8lib.cpp
        src/lvm.cpp
        src/lvm.h
        src/lzio.cpp
        src/lzio.h
        )

target_include_directories(lua PUBLIC include)

if (APPLE)
    target_compile_definitions(lua PRIVATE LUA_USE_MACOSX)
elseif (UNIX)
    target_compile_definitions(lua PRIVATE LUA_USE_LINUX)
    target_link_libraries(dl)
endif()
