cmake_minimum_required(VERSION 3.20)
project(EzorsiaV2)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Force 32-bit build
set(CMAKE_GENERATOR_PLATFORM Win32)

# Add source files
set(SOURCES
    ezorsia/Client.cpp
    ezorsia/dinput8.cpp
    ezorsia/dllmain.cpp
    ezorsia/MainMain.cpp
    ezorsia/Memory.cpp
    ezorsia/stdafx.cpp
    ezorsia/ZAllocEx.cpp
    ezorsia/Resource.rc
)

# Add header files
set(HEADERS
    ezorsia/Client.h
    ezorsia/codecaves.h
    ezorsia/detours.h
    ezorsia/detver.h
    ezorsia/dinput8.h
    ezorsia/MainMain.h
    ezorsia/Memory.h
    ezorsia/ReplacementFuncs.h
    ezorsia/stdafx.h
    ezorsia/syelog.h
    ezorsia/targetver.h
    ezorsia/AddyLocations.h
    ezorsia/AutoTypes.h
    ezorsia/INIReader.h
    ezorsia/resource.h
)

# Create DLL target
add_library(dinput8 SHARED ${SOURCES} ${HEADERS})

# Set output directory
set_target_properties(dinput8 PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/out"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/out"
)

# Add include directories
target_include_directories(dinput8 PRIVATE
    ${CMAKE_SOURCE_DIR}
    ${CMAKE_SOURCE_DIR}/ezorsia
    ${CMAKE_SOURCE_DIR}/detours
)

# Link libraries
target_link_libraries(dinput8 PRIVATE
    detours
    Winmm
    Ws2_32
) 