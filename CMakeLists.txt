cmake_minimum_required(VERSION 3.0.0)
project(snmppp VERSION 0.1.0)


file(GLOB allfiles
    "src/*.cpp"
)

#add_subdirectory("./../libdes/" "./build-dep/libdes")

add_compile_definitions(
    _LIB
    HAVE_CONFIG_H
    _CRT_SECURE_NO_WARNINGS
    _WINSOCK_DEPRECATED_NO_WARNINGS)

add_library(snmppp STATIC "${allfiles}")


target_include_directories(snmppp PUBLIC "./include/")
#target_include_directories(snmppp PUBLIC "./../libdes/src/")
target_include_directories(snmppp PUBLIC "./../vs2013/SNMP++/include/")

target_link_libraries(snmppp PUBLIC libdes)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})