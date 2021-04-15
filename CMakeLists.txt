SET(NFD_SOURCES
        src/include/nfd.h
        src/nfd_common.h
        src/nfd_common.c)

SET(NFD_SOURCES_LINUX
        src/nfd_gtk.c)

SET(NFD_SOURCES_WIN32
        include/nfd_win.cpp)

if(UNIX)
    SET(NFD_SOURCES ${NFD_SOURCES} ${NFD_SOURCES_LINUX})
endif()

if(WIN32)
    SET(NFD_SOURCES ${NFD_SOURCES} ${NFD_SOURCES_WIN32})
endif()

include_directories(src/include)

add_library(nfd ${NFD_SOURCES})

target_link_libraries(nfd ${CMAKE_DL_LIBS})