cmake_minimum_required(VERSION 3.13)
project(wtdbg2)

set(CMAKE_C_COMPILER /usr/bin/gcc)

include_directories(.)

if (CMAKE_COMPILER_IS_GNUCC)
    set(CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS} -lm -lrt -lpthread -lz")
endif ()

add_executable(wtdbg2 wtdbg.c ksw.c)
add_executable(kbm2 kbm.c ksw.c)
add_executable(wtdbg-cns wtdbg-cns.c ksw.c)
add_executable(wtpoa-cns wtpoa-cns.c ksw.c)
add_executable(pgzf pgzf.c)

target_link_libraries(wtdbg2 -lm -lrt -lpthread -lz)
target_link_libraries(kbm2 -lm -lrt -lpthread -lz)
target_link_libraries(wtdbg-cns -lm -lrt -lpthread -lz)
target_link_libraries(wtpoa-cns -lm -lrt -lpthread -lz)
target_link_libraries(pgzf -lm -lrt -lpthread -lz)
