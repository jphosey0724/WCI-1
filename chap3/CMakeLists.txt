add_executable(xref 
    ../chap2/scanner.c 
    ../chap2/error.c
    symtab.c
    xref.c
)

add_executable(crunch 
    ../chap2/scanner.c 
    ../chap2/error.c
    symtab.c 
    crunch.c
)

add_executable(uncrunch 
    uncrunch.c
)

target_include_directories(xref PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>)
target_include_directories(crunch PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>)
target_include_directories(uncrunch PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	target_link_libraries(xref PRIVATE m)
	target_link_libraries(crunch PRIVATE m)
    target_link_libraries(uncrunch PRIVATE m)
endif()