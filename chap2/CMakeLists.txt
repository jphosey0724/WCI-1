
add_executable(token1 token1.c)
add_executable(token2 token2.c scanner.c error.c)
add_executable(compact compact.c scanner.c error.c)

if (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	target_link_libraries(token1 PRIVATE m)
	target_link_libraries(token2 PRIVATE m)
    target_link_libraries(compact PRIVATE m)
endif()


