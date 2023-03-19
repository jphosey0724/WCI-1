add_executable( analyze
    ../chap2/error.c
    ../chap5/scanner.c
    symtab.c 
    decl.c 
    analyze.c
)

add_executable( syntax2
    ../chap2/error.c
    ../chap5/scanner.c 
    symtab.c 
    decl.c 
    stmt.c 
    expr.c 
    syntax2.c
)

target_include_directories( analyze 
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>
)

target_include_directories( syntax2
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>
)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	target_link_libraries(analyze PRIVATE m)
	target_link_libraries(syntax2 PRIVATE m)
endif()