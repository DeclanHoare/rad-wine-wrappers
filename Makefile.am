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

noinst_SCRIPTS = generatewrapper generatewrappers extractfiles
filelist = brc32.exe brcc32.exe cgrc.exe convert.exe CppLibTransform.exe GenTLB.exe GetItCmd.exe grep.exe ico2icns.exe impdef.exe implib.exe make.exe mkexp.exe rc.exe reFind.exe rmtdbg240.exe tasm32.exe tdump.exe tlib.exe tlibimp.exe touch.exe tregsvr.exe WSDLImp.exe RcDLL.dll rw32core.dll
radlist = convert grep make rc touch
installerexe = radstudio10_1_upd2_esd.exe

all: radstudio wrappers

extractfiles: src/extractfiles.in Makefile
	sed -e "s|FILELIST|$(filelist)|g" -e "s|INNOEXTRACTPATH|$(innoextractPath)|g" -e "s|SRCDIR|$(srcdir)|g" -e "s|INSTALLEREXE|$(installerexe)|g" < $(srcdir)/src/extractfiles.in > extractfiles
	chmod +x extractfiles

radstudio: extractfiles Makefile
	./extractfiles 
	mv app/bin radstudio
	rmdir app

generatewrapper: src/generatewrapper.in Makefile
	sed -e "s|RADLIST|$(radlist)|g" -e "s|DATAROOTDIR|$(datarootdir)|g" -e "s|WINEPATH|$(winePath)|g" < $(srcdir)/src/generatewrapper.in > generatewrapper
	chmod +x generatewrapper

generatewrappers: src/generatewrappers.in Makefile
	sed -e "s|FILELIST|$(filelist)|g" -e "s|RADLIST|$(radlist)|g" < $(srcdir)/src/generatewrappers.in > generatewrappers
	chmod +x generatewrappers

wrappers: generatewrapper generatewrappers Makefile
	./generatewrappers

install-exec-local: wrappers
	mkdir -p $(DESTDIR)/$(bindir)
	cp wrappers/* $(DESTDIR)/$(bindir)

install-data-local: radstudio
	mkdir -p $(DESTDIR)/$(datarootdir)
	cp -r radstudio $(DESTDIR)/$(datarootdir)/radstudio
