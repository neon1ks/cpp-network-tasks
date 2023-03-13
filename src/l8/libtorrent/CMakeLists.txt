project(libtorrent-examples)

if(CMAKE_CXX_COMPILER_ID MATCHES Clang)
	add_compile_options(-Wno-implicit-int-float-conversion)
endif()

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread")

# LibtorrentRasterbar
find_package(LibtorrentRasterbar CONFIG REQUIRED)

add_executable(magnet "magnet.cpp")
target_link_libraries(magnet PRIVATE LibtorrentRasterbar::torrent-rasterbar)

add_executable(torrent-client "client.cpp")
target_link_libraries(torrent-client PRIVATE LibtorrentRasterbar::torrent-rasterbar)

