cmake_minimum_required(VERSION 3.20)
project(order_book LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# the order book itself, built as a library
add_library(orderbook src/order_book.cpp)
target_include_directories(orderbook PUBLIC include)

# the demo program, which uses the library
add_executable(demo src/main.cpp)
target_link_libraries(demo PRIVATE orderbook)