PROJECT(rpc)
CMAKE_MINIMUM_REQUIRED (VERSION 2.6)
SET(CMAKE_CXX_FLAGS "-g -Wall -Werror -std=c++14")

ADD_SUBDIRECTORY(proto)

find_package(Protobuf REQUIRED)
include_directories(${PROTOBUF_INCLUDE_DIRS})

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR})

ADD_EXECUTABLE(main main.cpp ArchonErrorCollector.h draft.h ProtobufParser.h)
TARGET_LINK_LIBRARIES(main proto ${PROTOBUF_LIBRARY})
