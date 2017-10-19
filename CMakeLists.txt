CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

PROJECT(tinyplayer)

SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DNDEBUG -Os -flto -Wall -fno-asynchronous-unwind-tables -fno-stack-protector -ffunction-sections -fdata-sections -Wl,--gc-sections")
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DNDEBUG -Os -flto -Wall -fno-asynchronous-unwind-tables -fno-stack-protector -ffunction-sections -fdata-sections -Wl,--gc-sections")

SET(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/CMake)
FIND_PACKAGE(SDL2 REQUIRED)
INCLUDE_DIRECTORIES(${SDL2_INCLUDE_DIR})

ADD_EXECUTABLE(tinyplayer
    tinyplayer.cpp
    v2mplayer.cpp
    v2mconv.cpp
    synth_core.cpp
    sounddef.cpp
)

TARGET_LINK_LIBRARIES(tinyplayer
    ${SDL2_LIBRARY}
)
