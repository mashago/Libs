#1.define project
#2.define make flags
#3.add sub dir

#define cmake version
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

#1.define project and target
SET(PROJECT_NAME liblua)
PROJECT(${PROJECT_NAME})
SET(TARGET_NAME liblua)

#2.define make flags and install path
SET(CMAKE_BUILD_TYPE "Release")
SET(CMAKE_CONFIGURATION_TYPES "Release")

#3.group source
FILE(GLOB FILES_HEAD *.h *.hpp)
AUX_SOURCE_DIRECTORY(. FILES_SOURCE)
SOURCE_GROUP("Include" FILES ${FILES_HEAD})
SOURCE_GROUP("Source" FILES ${FILES_SOURCE})

#4.create lib
ADD_LIBRARY(${TARGET_NAME} ${FILES_HEAD} ${FILES_SOURCE})