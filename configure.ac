#
# configure.ac for miLogger
#

AC_PREREQ(2.59)
AC_INIT([miLogger], [5.0.3], [diana@met.no])
AM_INIT_AUTOMAKE([foreign])
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AC_CONFIG_SRCDIR([src/logger.h])
AC_CONFIG_MACRO_DIR([m4])

METNO_SET_VERSION_INFO(6.0.0)
METNO_PROG_PKG_CONFIG

AC_SUBST([LIBTOOL_DEPS]) 

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AC_PROG_LIBTOOL


# Language stack
AC_LANG_PUSH(C++)

# Checks for libraries.
AC_CXX_HAVE_STD
AC_CXX_HAVE_STL
AC_LANG_POP([C++])


METNO_ENABLE_CONDITIONAL([SHARED_LIBRARY], [shared])

AC_ARG_ENABLE([log4cpp],
    [AS_HELP_STRING([--disable-log4cpp], [disable log4cpp])],
    [], [enable_log4cpp=yes])
AM_CONDITIONAL([WITH_LOG4CPP], [test x$enable_log4cpp = xyes])

AS_IF([test x$enable_log4cpp = xyes], [
    METNO_REQUIRE_PKG([LOG4CPP], [log4cpp])
])

AC_CONFIG_FILES([
	miLogger.pc
	Makefile
	src/Makefile
])

AC_OUTPUT
