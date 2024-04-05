add_library(boost_asio_module)

target_sources(boost_asio_module
        PUBLIC
        FILE_SET CXX_MODULES FILES
        core.cpp module.cpp execution.cpp buffers.cpp properties.cpp spawn.cpp
        experimental.cpp networking.cpp timers.cpp ssl.cpp serial_port.cpp signal_set.cpp
        pipe.cpp file.cpp posix.cpp windows.cpp local.cpp
)

add_library(boost::module::asio ALIAS boost_asio_module)

target_link_libraries(boost_asio_module PUBLIC Boost::asio)