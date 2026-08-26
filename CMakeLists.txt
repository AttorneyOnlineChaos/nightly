cmake_minimum_required(VERSION 3.19)

project("Chaos" LANGUAGES CXX C)

file(GLOB ENTRIES RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "${CMAKE_CURRENT_SOURCE_DIR}/*")
list(SORT ENTRIES)

foreach(entry IN LISTS ENTRIES)
  if(IS_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/${entry}" AND EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/${entry}/CMakeLists.txt")
    add_subdirectory(${entry})
  endif()
endforeach()
