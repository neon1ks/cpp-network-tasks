cmake_minimum_required(VERSION 3.16)
project(boost-mpi-example LANGUAGES CXX)

find_package(Boost COMPONENTS mpi serialization REQUIRED)
find_package(MPI REQUIRED)

add_executable("${PROJECT_NAME}-messaging" messaging.cpp)
add_executable("${PROJECT_NAME}-reduce" reduce.cpp)

target_include_directories ("${PROJECT_NAME}-messaging" PUBLIC ${MPI_CXX_INCLUDE_DIRS})
target_include_directories ("${PROJECT_NAME}-reduce" PUBLIC ${MPI_CXX_INCLUDE_DIRS})

target_link_libraries("${PROJECT_NAME}-messaging" PUBLIC ${MPI_LIBRARIES} Boost::mpi)
target_link_libraries("${PROJECT_NAME}-reduce" PUBLIC ${MPI_LIBRARIES} Boost::mpi )
