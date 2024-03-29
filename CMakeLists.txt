# check the minimum requirements
cmake_minimum_required(VERSION 3.1...3.24)


# define the project
project(jojoloop VERSION 0.1 LANGUAGES CXX)
set(CMAKE_BUILD_TYPE Debug)


# check dependencies
find_package(ALSA REQUIRED)                                    
if (NOT ${ALSA_FOUND})                                                
    message(FATAL_ERROR "can not find ALSO package")
endif()


# define all source and include files
set(sources 
)
set(headers
)


# define the main project
add_executable(jojoloop
    ${sources}
)
target_include_directories(jojoloop
    PRIVATE ./include
)
target_link_libraries(jojoloop
    pthread 
    ${ALSA_LIBRARIES}
)      


