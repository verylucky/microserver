CMAKE_MINIMUM_REQUIRED (VERSION 2.6)
PROJECT (TEST)

MESSAGE("START BUILD TEST...")
ADD_DEFINITIONS(-g -DTIXML_USE_STL)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/../test)
#INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/)

AUX_SOURCE_DIRECTORY(${PROJECT_SOURCE_DIR} SRC_LIST)

#链接外部库
#ADD_LIBRARY(testepoll_lib STATIC IMPORTED)
#SET_PROPERTY(TARGET testepoll_lib PROPERTY IMPORTED_LOCATION ${PROJECT_SOURCE_DIR}/../../lib/libutil.a)

#ADD_EXECUTABLE(TEST test.c)
#ADD_EXECUTABLE(TESTCORO testcoro.c) 
#ADD_EXECUTABLE(TESTJMP testjmp.c) 
ADD_EXECUTABLE(SERVER server.cpp coro.cpp handler.cpp) 
ADD_EXECUTABLE(CLIENT client.cpp) 
#ADD_EXECUTABLE(CORO coro.cpp handler.cpp) 

TARGET_LINK_LIBRARIES(SERVER util)


