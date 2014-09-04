# CMakeLists.txt

# Include directories
INCLUDE_DIRECTORIES(
${GLOG_INCLUDE_DIR}
)

SET(GLOG_SRCS 
logging.cc
raw_logging.cc
utilities.cc
vlog_is_on.cc
windows/port.cc
)

SET(GLOG_HEADERS
Base/commandlineflags.h
Base/googleinit.h
Base/mutex.h
windows/glog/log_severity.h
windows/config.h
windows/glog/logging.h
windows/port.h
windows/glog/raw_logging.h
windows/glog/stl_logging.h
windows/glog/vlog_is_on.h
utilities.h
)

ADD_LIBRARY( libglog SHARED ${GLOG_HEADERS} ${GLOG_SRCS})
