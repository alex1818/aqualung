ACLOCAL_AMFLAGS = -I m4

SUBDIRS = doc po skin . src
EXTRA_DIST = autogen.sh gettext.h ladspa.h

all-local:
	cd src; \
	if test -e version.h; then svn1="`cat version.h`"; else svn1=""; fi; \
	if test -e ../.svn; then svn2="#define AQUALUNG_VERSION \"R-`cd ..; LC_ALL=C svn info | grep '^Revision' | awk '{print $$2}'`\""; else svn2=""; fi; \
	if test -z "$$svn2" -a -e ../../.svn; then svn2="#define AQUALUNG_VERSION \"R-`cd ../..; LC_ALL=C svn info | grep '^Revision' | awk '{print $$2}'`\""; fi; \
	if test "$$svn1" -a "$$svn2" -a "$$svn1" != "$$svn2" -o -z "$$svn1" -a "$$svn2"; then echo "$$svn2" > version.h; fi; \
	if test -z "$$svn1" -a -z "$$svn2"; then echo "#define AQUALUNG_VERSION \"R-???\"" > version.h; fi;

uninstall-local:
	rm -rf $(pkgdatadir)
