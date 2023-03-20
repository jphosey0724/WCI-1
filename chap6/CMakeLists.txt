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

# Per the instructions of the book, use the following to set the 
# 'analyze' preprocessor definition in parser.h. When this is defined, the 
# analyzer routines will get compiled, otherwise they won't.
# For the 'analyze' target, this must be enabled. For the 'syntax2' target,
# it must be disabled, or the target won't build. 
# Not sure if CMake can set this on a target-by-target basis.
#add_compile_definitions(analyze)

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

