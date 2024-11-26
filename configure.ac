#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.
AC_PREREQ([2.69])

m4_define([ver_major], [1])
m4_define([ver_minor], [0])
m4_define([ver_release], [0])
# Set build number to commit count only if ".git" folder is present
m4_define([ver_build], m4_if(m4_esyscmd_s([ls -1 -d ".git" 2>&1]),.git,[m4_esyscmd_s([git rev-list --count HEAD])],[0]))

m4_define([swars_sfx_version],
      [ver_major.ver_minor.ver_release.ver_build])

AC_INIT([Syndicate Wars SFX], [swars_sfx_version], [mefistotelis@gmail.com], [swars_sfx])

m4_define([parent_package], [swars])
AC_DEFINE([PARENT_PACKAGE], [parent_package], [Name of the parent package, for which this one provides data files])

AC_CONFIG_SRCDIR([data/nfra-0.ani])
# We use header file as means to transfer properties to automation scripts
AC_CONFIG_HEADERS([sfx_config.h])

AC_CANONICAL_HOST
AC_CANONICAL_TARGET

AM_INIT_AUTOMAKE([foreign])
ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

# Checks for programs
AC_PROG_MKDIR_P

AC_PATH_PROG([WAWTODAT], [sndbanker], [notfound],
  [${PATH}${PATH_SEPARATOR}/usr/local/bin${PATH_SEPARATOR}${srcdir}/bin])
AS_VAR_IF([WAWTODAT], [notfound], [AC_MSG_ERROR([Tool sndbanker not found in bin dir or PATH dirs.])], [])

# Default install dir
#AC_PREFIX_DEFAULT(/usr/local)

# Flags
AC_SUBST([PARENT_PACKAGE], [parent_package])

# Prepare makefiles from `.in` templates
AC_CONFIG_FILES([Makefile])

# Done - generate and execute `config.status`
AC_OUTPUT
