AC_PREREQ(2.59)
AC_INIT(libpartialzip, 1.0)
AM_CONFIG_HEADER(config.h)

# Checks for programs.
AM_PROG_LIBTOOL
AC_PROG_INSTALL
AC_CONFIG_MACRO_DIRS([m4])

AC_PROG_MAKE_SET
AC_CANONICAL_SYSTEM
AM_INIT_AUTOMAKE(libpartialzip, 1.0)

AM_PROG_CC_C_O
AC_LANG_C

AC_HEADER_STDC
AC_CONFIG_MACRO_DIR([m4])

# Check the platform.
AC_MSG_CHECKING([whether to enable WIN32 specific flags])
case "$host_os" in
*mingw*)
        win32=true
        AC_MSG_RESULT([yes])
	AC_CHECK_TOOL(WINDRES, windres)
  ;;
*)
        win32=false
        AC_MSG_RESULT([no])
  ;;
esac
AM_CONDITIONAL(WIN32, test x$win32 = xtrue)

# Checks for libraries.
PKG_CHECK_MODULES(zlib, zlib >= 1.0)
PKG_CHECK_MODULES(curl, libcurl >= 1.0)
PKG_CHECK_MODULES(crippy, libcrippy-1.0 >= 1.0)

# Checks for header files.
AC_CHECK_HEADERS([stdio.h stdlib.h string.h])

AC_CONFIG_FILES(Makefile src/Makefile include/Makefile tools/Makefile libpartialzip-1.0.pc)

AC_OUTPUT
