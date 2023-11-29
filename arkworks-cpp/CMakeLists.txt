
add_library(arkworks-cpp
    ./arkworks.cpp
)
add_dependencies(arkworks-cpp
    cargo_build
)

target_include_directories(arkworks-cpp PRIVATE
    $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
)

install(
    TARGETS arkworks-cpp EXPORT arkworks_crust_targets
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
    INCLUDES DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/arkworks-cpp
)
