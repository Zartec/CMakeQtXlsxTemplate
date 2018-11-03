set(STATIC ON CACHE BOOL "Build xlnt static" FORCE)
set(TESTS OFF CACHE BOOL "Build xlnt tests" FORCE)
add_subdirectory(xlnt EXCLUDE_FROM_ALL)
