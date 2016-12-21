# Copyright 2016 Declan Hoare
#
# This file is part of the RAD WINE Wrappers.
#
# The RAD WINE Wrappers are free software: you can redistribute them and/or modify
# them under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
# 
# The RAD WINE Wrappers are distributed in the hope that they will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with the RAD WINE Wrappers.  If not, see <http://www.gnu.org/licenses/>.

AC_INIT([radstudio], [10.1.2.0], [https://github.com/RogueAI42/rad-wine-wrappers/issues], [rad-wine-wrappers], [https://github.com/RogueAI42/rad-wine-wrappers])
AC_PREREQ([2.68])
AC_CONFIG_SRCDIR([src/radstudio10_1_upd2_esd.exe])
AC_CONFIG_AUX_DIR([build-aux])
AM_INIT_AUTOMAKE([1.11 -Wall -Werror foreign])
AC_CONFIG_FILES([Makefile])
AC_PATH_PROG([innoextractPath], [innoextract], [not found])
AS_IF([test "$innoextractPath" = "not found"], [AC_MSG_ERROR([Required program 'innoextract' not found.])])
AC_PATH_PROG([winePath], [wine], [not found])
AS_IF([test "$winePath" = "not found"], [AC_MSG_ERROR([Required program 'wine' not found.])])
AC_OUTPUT
