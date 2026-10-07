TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build an ioc application
# Use PROD_IOC_RTEMS for RTEMS only
# Use PROD_IOC_Linux for Linux only
PROD_IOC = gsd

# gsd.dbd will be created and installed
DBD += gsd.dbd

# gsd.dbd will be made up from these files:
gsd_DBD += base.dbd
gsd_DBD += iocAdmin.dbd
gsd_DBD += asSupport.dbd
gsd_DBD += asyn.dbd
gsd_DBD += drvAsynSerialPort.dbd
gsd_DBD += drvAsynIPPort.dbd
gsd_DBD += stream.dbd
gsd_DBD += caPutLog.dbd

# <name>_registerRecordDeviceDriver.cpp will be created from <name>.dbd
gsd_SRCS += gsd_registerRecordDeviceDriver.cpp
gsd_SRCS_DEFAULT += gsdMain.cpp

# Add locally compiled object code
#gsd_SRCS += dbSubExample.c

gsd_LIBS += devIocStats
gsd_LIBS += autosave
gsd_LIBS += asyn
gsd_LIBS += stream
gsd_LIBS += caPutLog
gsd_LIBS += $(EPICS_BASE_IOC_LIBS)

ifneq '$(T_A)' 'RTEMS-beatnik'
PROD_SYS_LIBS_DEFAULT += pcre
SHRLIB_DEPLIB_DIRS += $(PCRE_LIB)
endif

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

