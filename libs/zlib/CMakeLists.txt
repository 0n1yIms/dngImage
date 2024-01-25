cmake_minimum_required(VERSION 3.6.0)

# set(zlib_INCLUDE ${PROJECT_SOURCE_DIR}/third-party/zlib-source/zlibt/include)
# set(zlib_INCLUDE ${PROJECT_SOURCE_DIR}/third-party/zlib-source)
# set(ZLIB_ROOT ${PROJECT_SOURCE_DIR}/third-party/zlib-source)

# set(ZLIB_PUBLIC_HDRS
#         ${ZLIB_ROOT}/zconf.h
#         ${ZLIB_ROOT}/zlib.h
# )
# set(ZLIB_PRIVATE_HDRS
#         ${ZLIB_ROOT}/crc32.h
#         ${ZLIB_ROOT}/deflate.h
#         ${ZLIB_ROOT}/gzguts.h
#         ${ZLIB_ROOT}/inffast.h
#         ${ZLIB_ROOT}/inffixed.h
#         ${ZLIB_ROOT}/inflate.h
#         ${ZLIB_ROOT}/inftrees.h
#         ${ZLIB_ROOT}/trees.h
#         ${ZLIB_ROOT}/zutil.h
# )
# set(ZLIB_SRCS
#         ${ZLIB_ROOT}/adler32.c
#         ${ZLIB_ROOT}/compress.c
#         ${ZLIB_ROOT}/crc32.c
#         ${ZLIB_ROOT}/deflate.c
#         ${ZLIB_ROOT}/gzclose.c
#         ${ZLIB_ROOT}/gzlib.c
#         ${ZLIB_ROOT}/gzread.c
#         ${ZLIB_ROOT}/gzwrite.c
#         ${ZLIB_ROOT}/inflate.c
#         ${ZLIB_ROOT}/infback.c
#         ${ZLIB_ROOT}/inftrees.c
#         ${ZLIB_ROOT}/inffast.c
#         ${ZLIB_ROOT}/trees.c
#         ${ZLIB_ROOT}/uncompr.c
#         ${ZLIB_ROOT}/zutil.c
# )


file (GLOB zlib_SRCS 
        ${CMAKE_CURRENT_SOURCE_DIR}/include/*.h)
file (GLOB zlib_HDRS 
        ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)

set(zlib_INCLUDE ${CMAKE_CURRENT_SOURCE_DIR}/include)

add_library(zlib STATIC ${zlib_SRCS} ${zlib_HDRS})

target_include_directories(zlib PUBLIC
        ${zlib_INCLUDE}
        )
