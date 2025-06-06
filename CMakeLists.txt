cmake_minimum_required(VERSION 3.10)
project(learn_cpp_sandbox)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY \${CMAKE_BINARYDIR}/bin)

file(GLOB CHAPTER_DIRS RELATIVE \${CMAKE_SOURCE_DIR}/chapters
     chapters/*)

foreach(dir \${CHAPTER_DIRS})
    if (EXISTS "\${CMAKE_SOURCE_DIR}/chapters/\${dir}/CMakeLists.txt")
        add_subdirectory(chapters/\${dir})
    endif()
endforeach()