add_executable(pprint
    ../chap2/error.c
    ../chap7/symtab.c 
    ../chap7/standard.c 
    ../chap7/decl.c 
    scanner.c
    stmt.c 
    expr.c
    routine.c
    ppdecl.c 
    ppstmt.c 
    pprint.c 
)

# Per the instructions of the book, use the following to set the 
# 'analyze' preprocessor definition in parser.h. When this is defined, 
# the analyzer routines will get compiled, otherwise they won't.
add_compile_definitions(analyze)

# Order of include directories matters.
target_include_directories( pprint
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap7>
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap6>
)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	target_link_libraries(syntax3 PRIVATE m)
endif()

