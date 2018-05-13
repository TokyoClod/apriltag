cmake_minimum_required(VERSION 2.8.3)
project(test)

find_package(VISP)
find_package(OpenCV REQUIRED)
find_package(PkgConfig)
pkg_check_modules(APRIL REQUIRED apriltag)
include_directories(${OpenCV_INCLUDE_DIRS})

include_directories(${APRIL_INCLUDE_DIRS}/${APRIL_LIBRARIES})
link_directories(${APRIL_LIBRARY_DIRS})


add_executable(test opencv_demo.cc)


target_link_libraries(${PROJECT_NAME}
  ${OpenCV_LIBS} 
  ${APRIL_LIBRARIES}
)
