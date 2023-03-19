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