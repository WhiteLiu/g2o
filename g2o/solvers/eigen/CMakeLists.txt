ADD_LIBRARY(solver_eigen ${G2O_LIB_TYPE}
  solver_eigen.cpp
  linear_solver_eigen.h
)
SET_TARGET_PROPERTIES(solver_eigen PROPERTIES OUTPUT_NAME ${LIB_PREFIX}solver_eigen)
TARGET_LINK_LIBRARIES(solver_eigen core)

INSTALL(TARGETS solver_eigen
  RUNTIME DESTINATION ${CMAKE_INSTALL_PREFIX}/bin
  LIBRARY DESTINATION ${CMAKE_INSTALL_PREFIX}/lib
  ARCHIVE DESTINATION ${CMAKE_INSTALL_PREFIX}/lib
)
FILE(GLOB headers "${CMAKE_CURRENT_SOURCE_DIR}/*.h" "${CMAKE_CURRENT_SOURCE_DIR}/*.hpp")
INSTALL(FILES ${headers} DESTINATION ${CMAKE_INSTALL_PREFIX}/include/g2o/solvers/eigen)
