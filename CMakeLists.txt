cmake_minimum_required(VERSION 3.0.0)
project(new_project VERSION 0.1.0)
include(CTest)
enable_testing()

file(GLOB TARGET_SRC "./src/*.cpp" )

add_executable(main ${TARGET_SRC})

#---------------------------------------------------------------------------#

include_directories(include)
find_package(SFML 2 COMPONENTS graphics window system REQUIRED)
target_link_libraries(main PUBLIC sfml-system sfml-window sfml-graphics)

#---------------------------------------------------------------------------#

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
