cmake_minimum_required(VERSION 3.6)

PROJECT (tinygltf)

SET(CMAKE_CXX_STANDARD 11)

add_library(tinygltf STATIC src/tiny_gltf.cpp)

target_compile_definitions(tinygltf
        PUBLIC -DTINYGLTF_USE_RAPIDJSON)

target_include_directories(tinygltf
        PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        ${RapidJSON_INCLUDE_DIRS})

INSTALL ( FILES
  json.hpp
  include/stb_image.h
  include/stb_image_write.h
  include/tiny_gltf.h
  DESTINATION
  include
  )

INSTALL ( FILES
  cmake/TinyGLTFConfig.cmake
  DESTINATION
  cmake
  )
