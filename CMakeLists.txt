set (CMAKE_CXX_STANDARD 20)
cmake_minimum_required(VERSION 3.27)
project(lab57)

find_package(cppzmq)

add_compile_options(-pthread)

add_executable(client ./src/client.cpp ./src/tree.cpp)
add_executable(server ./src/main.cpp ./src/tree.cpp)

target_link_libraries(client PRIVATE cppzmq)
target_link_libraries(server PRIVATE cppzmq)