# cmake for grid2ps src subdirs

project(grid2ps)

# languages

enable_language(C)
enable_language(Fortran)

# compile

set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -fPIC -std=legacy ")

# includes

include_directories(/usr//include)
include_directories(/usr/local/include)

# libs

link_directories(/usr/lib)
link_directories(/usr/local/lib)

# Finding pkg-config
find_package(PkgConfig REQUIRED)

# find NetCDF
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

target_link_libraries(${PROJECT_NAME} ${NETCDF_LIBRARIES})
target_link_libraries(${PROJECT_NAME} netcdff)

# install

install(TARGETS ${PROJECT_NAME} DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)

