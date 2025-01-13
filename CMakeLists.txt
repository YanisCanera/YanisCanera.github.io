cmake_minimum_required(VERSION 3.31)
project ("CMakeNinja")

find_package(SFML COMPONENTS system window graphics audio CONFIG REQUIRED)

file(GLOB SRC_DIR "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")

file(GLOB ALL_HEADERS "include/*.h")
file(GLOB ALL_SRC "src/*.cpp")


add_executable(${PROJECT_NAME} ${ALL_SRC})
# add_executable(${PROJECT_NAME} ${SRC_DIR})

target_compile_features(${PROJECT_NAME} INTERFACE cxx_std_20)

target_include_directories(${PROJECT_NAME} PUBLIC ${ALL_HEADERS})

#target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR}/include)

target_link_libraries(${PROJECT_NAME} PRIVATE 
sfml-system 
sfml-window 
sfml-graphics 
sfml-audio
)


