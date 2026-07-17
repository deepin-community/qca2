cmake_minimum_required(VERSION 3.18)

project(ciphertest LANGUAGES CXX)

if(QT_VERSION STREQUAL "6")
  find_package(Qt6Core REQUIRED)
  find_package(Qca-qt6 REQUIRED)
elseif(QT_VERSION STREQUAL "5")
  find_package(Qt5Core REQUIRED)
  find_package(Qca-qt5 REQUIRED)
elseif()
  message(FATAL_ERROR "unknown QT_VERSION: '${QT_VERSION}'")
endif()

add_executable(ciphertest ciphertest.cpp)

if(QT_VERSION STREQUAL "6")
  target_link_libraries(ciphertest Qt6::Core qca-qt6)
elseif(QT_VERSION STREQUAL "5")
  target_link_libraries(ciphertest Qt5::Core qca-qt5)
endif()
