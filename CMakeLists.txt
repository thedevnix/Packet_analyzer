cmake_minimum_required(VERSION 3.16)

project(PacketAnalyzer VERSION 1.0 LANGUAGES CXX)

find_package(Threads REQUIRED)

add_executable(dpi_engine
    src/dpi_mt.cpp
    src/pcap_reader.cpp
    src/packet_parser.cpp
    src/sni_extractor.cpp
    src/types.cpp
)

target_include_directories(dpi_engine PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/include")
target_compile_features(dpi_engine PRIVATE cxx_std_17)
target_link_libraries(dpi_engine PRIVATE Threads::Threads)
