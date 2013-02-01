dnl -*- Autoconf -*-

AC_INIT(json, 0.0.1)
AC_CONFIG_SRCDIR(src/json-reader.scm)
AC_CONFIG_AUX_DIR([build-aux])
AM_INIT_AUTOMAKE([-Wall -Wno-portability foreign])

GUILE_PROGS

if $GUILE_TOOLS | grep -q compile; then
   # everything cool
   true
else
   AC_MSG_ERROR([Guile 2.0 required.])
fi

# Additional parameters
DEFAULT_GUILELIBDIR="$(guile-config info sitedir)"
AC_ARG_VAR([GUILELIBDIR], [Where to install guile modules [wherever guile-config says]])
AS_IF([test "x$GUILELIBDIR" = x], [if test -n "$DEFAULT_GUILELIBDIR"; then GUILELIBDIR="$DEFAULT_GUILELIBDIR"; else exit 1; fi])

AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([src/Makefile])
AC_CONFIG_FILES([env], [chmod +x env])

AC_OUTPUT
