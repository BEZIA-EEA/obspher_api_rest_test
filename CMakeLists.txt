cmake_minimum_required(VERSION 3.0)
project(ServerApp)

set(CMAKE_CXX_STANDARD 17)
set(Boost_USE_STATIC_LIBS ON)
set(Boost_USE_MULTITHREADED ON)
find_package(Boost REQUIRED COMPONENTS system)

set(CMAKE_THREAD_PREFER_PTHREAD ON)                                                                                                                                                                                                           
set(THREADS_PREFER_PTHREAD_FLAG ON)                                                                                                                                                                                                           
find_package(Threads REQUIRED)                                                                                                                                                                                                                


add_executable(server main.cpp)
if(TARGET Threads::Threads)                                                                                                                                                                                                                   
  target_link_libraries(server PRIVATE Threads::Threads)                                                                                                                                                                                        
endif()

target_include_directories(server PRIVATE ${Boost_INCLUDE_DIRS})
target_link_libraries(server PRIVATE ${Boost_LIBRARIES})