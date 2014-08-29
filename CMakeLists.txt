cmake_minimum_required(VERSION 2.6)

PROJECT( glog )

message("Source Dir:" ${glog_SOURCE_DIR})

SET(EXECUTABLE_OUTPUT_PATH ${glog_SOURCE_DIR}/bin)
SET(LIBRARY_OUTPUT_PATH ${glog_SOURCE_DIR}/lib)
SET(RUNTIME_OUTPUT_DIRECTORY ${glog_SOURCE_DIR}/bin)

IF(WIN32)
IF(MSVC12)
message("Detected MSVC12 compiler")
set(MSVC_VER VC12)
ELSEIF(MSVC11)
message("Detected MSVC11 compiler")
set(MSVC_VER VC11)
ELSEIF(MSVC10)
message("Detected MSVC10 compiler")
set(MSVC_VER VC10)
ELSE(MSVC12)
message("WARNING: Unknown/unsupported MSVC version")
ENDIF(MSVC12)
ENDIF(WIN32)

SET(GLOG_INCLUDE_DIR
${glog_SOURCE_DIR}/src
${glog_SOURCE_DIR}/src/windows
${glog_SOURCE_DIR}/src/windows/glog
)

message("glog include directories:" ${GLOG_INCLUDE_DIR})

ADD_SUBDIRECTORY( src )
