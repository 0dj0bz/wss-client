cmake_minimum_required(VERSION 3.10)
project(WSS_Client)

set(CMAKE_CXX_STANDARD 11)

find_package(Boost REQUIRED COMPONENTS system)
find_package(OpenSSL REQUIRED)

add_executable(wss_client main.cpp)

#target_include_directories(wss_client PRIVATE /path/to/websocketpp)
target_include_directories(wss_client PRIVATE ${Boost_INCLUDE_DIRS})
#target_include_directories(wss_client PRIVATE ${OPENSSL_INCLUDE_DIR})

target_link_libraries(wss_client PRIVATE ${Boost_LIBRARIES})
target_link_libraries(wss_client PRIVATE ${OPENSSL_LIBRARIES})