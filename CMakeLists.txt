cmake_minimum_required(VERSION 3.0.0)
project(easywsclient)


set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_CXX_STANDARD 11)
set(THREADS_PREFER_PTHREAD_FLAG ON)

include_directories(/usr/include)
include_directories(include)

link_directories(/usr/lib
                 /usr/local/lib)


set(SOURCES
  easywsclient.cpp
)


add_library(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME} ${LIBS})

add_subdirectory(test)

install(TARGETS ${PROJECT_NAME} DESTINATION lib/)
install(DIRECTORY ./ DESTINATION include/easywsclient FILES_MATCHING PATTERN "*.h*")
