FIND_PACKAGE(TCL)
INCLUDE_DIRECTORIES(${TCL_INCLUDE_PATH})
SWIG_ADD_MODULE(cylon-tcl tcl ../cylon.i)
SWIG_LINK_LIBRARIES(cylon-tcl ${TCL_LIBRARY} cylon)

SET_TARGET_PROPERTIES(${SWIG_MODULE_cylon-tcl_REAL_NAME} PROPERTIES
	LINK_FLAGS "${CYLON_LDFLAGS}"
	COMPILE_FLAGS "${CYLON_CFLAGS}")

INSTALL(TARGETS ${SWIG_MODULE_cylon-tcl_REAL_NAME} LIBRARY DESTINATION lib/tcl)
