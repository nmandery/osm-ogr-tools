configure_file(version.hpp.in version.hpp @ONLY)
include_directories(${CMAKE_CURRENT_BINARY_DIR}) # to make the compile find the generated version.hpp

add_executable(osm2ogr_with_tags osm2ogr_with_tags.cpp)
target_link_libraries(osm2ogr_with_tags ${OSMIUM_LIBRARIES} ${Boost_LIBRARIES})
set_pthread_on_target(osm2ogr_with_tags)
install(TARGETS osm2ogr_with_tags DESTINATION bin)

install(PROGRAMS osm_extract.py DESTINATION bin)
