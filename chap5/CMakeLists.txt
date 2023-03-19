add_executable(syntax1
    ../chap2/error.c
    ../chap3/symtab.c
    scanner.c 
    stmt.c 
    expr.c 
    syntax1.c 
)

target_include_directories( syntax1 
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap3>
)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	target_link_libraries(syntax1 PRIVATE m)
endif()