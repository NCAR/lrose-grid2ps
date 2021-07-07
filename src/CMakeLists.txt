# cmake for grid2ps src subdirs

project(grid2ps)

# compile definitions

#add_definitions(-std=c++11)

# If needed, generate TDRP Params.cc and Params.hh files
# from their associated paramdef.<app> file

#makeTdrpParams()

# includes

#include_directories(${LROSE_PREFIX}/include)
#include_directories(${EIGEN3_INCLUDE_DIR})
#include_directories(/usr/local/include)

# Link

#link_directories(${LROSE_PREFIX}/lib)
#link_directories(/usr/lib/x86_64-linux-gnu/hdf5/serial)
#link_directories(/usr/local/lib)

# location of bin as it is built

# set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR}/release/bin)

enable_language(C)
enable_language(Fortran)

# Finding pkg-config
find_package(PkgConfig REQUIRED)

find_package (NETCDF)

# build app

add_executable (
  ${PROJECT_NAME}
  ALTER.f
  ASDPMD.f
  AssignVar.f
  BLHED.f
  BLKDAT.f
  CDATE.c
  CEDERX.f
  CEDLOG.f
  CEDREAD.f
  CEDUTIL.f
  CIN.c
  CMakeLists.txt
  COUT.c
  CRTHIN.f
  Char2Int.c
  FETCHZ.f
  IMHSUM.f
  LICENSE.txt
  LOCFLDID.f
  Makefile
  PLACEPLANE.f
  PLANST.f
  README.textile
  ReadInp.c
  ReadNetCDF.f
  ReadVar.f
  SAVEARRY.f
  SHIRBL.f
  TAPMES.f
  TextRead.f
  UserSub.f
  WritePS.f
  cedric.h
  common1.h
  common2.h
  common3.h
  contour.f
  gbytes.f
  i1mach.f
  inp1
  main.f
  sbytes.f
  )

# link

#target_link_libraries(${PROJECT_NAME} ${LROSE_LIBRARIES})
#target_link_libraries(${PROJECT_NAME} bz2)

# install

#set(INSTALL_PREFIX $ENV{LROSE_INSTALL_DIR})

#if(NOT INSTALL_PREFIX)
#  set(INSTALL_PREFIX ${LROSE_PREFIX})
#endif(NOT INSTALL_PREFIX)

install(TARGETS ${PROJECT_NAME} DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)

