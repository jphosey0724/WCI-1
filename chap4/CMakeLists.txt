add_executable(postfix 
    ../chap2/scanner.c 
    ../chap2/error.c
    postfix.c
)

add_executable(calc 
    ../chap3/symtab.c
    ../chap2/scanner.c 
    ../chap2/error.c
    calc.c
)

target_include_directories( postfix 
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap3>
)

target_include_directories( calc
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap2>
    PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../chap3>
)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	target_link_libraries(calc PRIVATE m)
	target_link_libraries(postfix PRIVATE m)
endif()