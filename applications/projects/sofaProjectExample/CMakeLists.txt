cmake_minimum_required(VERSION 3.1)
project(sofaProjectExample)

find_package(SofaGui)
find_package(SofaOpenglVisual)

add_executable(${PROJECT_NAME} Main.cpp)
target_link_libraries(${PROJECT_NAME} SofaGuiMain SofaOpenglVisual)
