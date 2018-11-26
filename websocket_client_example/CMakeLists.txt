cmake_minimum_required(VERSION 3.5.1)

project(websocket_client_example)


set(CMAKE_CXX_STANDARD 14)


find_package (Boost 1.66.0 COMPONENTS filesystem system REQUIRED)
find_package(Threads)


if(Boost_FOUND)
    message("=== Boost found ===")
    message(Boost_LIBRARY_DIR = ${Boost_LIBRARY_DIR})
    message(Boost_LIBRARY_DIR_RELEASE = ${Boost_LIBRARY_DIR_RELEASE})
    message(Boost_INCLUDE_DIRS = ${Boost_INCLUDE_DIRS})
    message(Boost_LIBRARIES = ${Boost_LIBRARIES})
    message(Boost_SYSTEM_LIBRARY = ${Boost_SYSTEM_LIBRARY})
endif()



add_executable(websocket_client_example main.cpp)



target_link_libraries(websocket_client_example
        ${Boost_LIBRARIES}
        ${CMAKE_THREAD_LIBS_INIT})

