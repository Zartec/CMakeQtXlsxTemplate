cmake_minimum_required(VERSION 3.1.0)

project(Vocabulary)

add_subdirectory(3rd_party)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5Widgets CONFIG REQUIRED)

set(helloworld_SRCS
    mainwindow.ui
    mainwindow.cpp
    main.cpp
)

add_executable(${PROJECT_NAME} ${helloworld_SRCS})
target_link_libraries(${PROJECT_NAME} Qt5::Widgets xlnt)

if(NOT INC_DEST_DIR)
  set(INC_DEST_DIR ${CMAKE_INSTALL_PREFIX}/include)
endif()

if(NOT LIB_DEST_DIR)
  set(LIB_DEST_DIR ${CMAKE_INSTALL_PREFIX}/lib)
endif()

if(NOT BIN_DEST_DIR)
   set(BIN_DEST_DIR ${CMAKE_INSTALL_PREFIX}/bin)
endif()

if(NOT MAN_DEST_DIR)
   set(MAN_DEST_DIR ${CMAKE_INSTALL_PREFIX}/share/man)
endif()

# Install library
install(TARGETS ${PROJECT_NAME}
  LIBRARY DESTINATION ${LIB_DEST_DIR}
  ARCHIVE DESTINATION ${LIB_DEST_DIR}
  RUNTIME DESTINATION ${BIN_DEST_DIR})
