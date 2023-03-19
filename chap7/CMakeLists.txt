add_executable( syntax3
    ../chap5/scanner.c 
    ../chap2/error.c
    routine.c 
    standard.c 
    decl.c
    stmt.c 
    expr.c 
    symtab.c 
    syntax3.c 
)

target_include_directories( syntax3
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap6>
)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	target_link_libraries(syntax3 PRIVATE m)
endif()