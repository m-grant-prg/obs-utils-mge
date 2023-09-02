#########################################################################
#									#
# Script ID: ./Makefile.am						#
# Author: Copyright (C) 2022, 2023  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0-only					#
#									#
# Purpose:								#
#	AutoMake script file to generate obs-utils-mge project from	#
# source.								#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 30/05/2022	MG	1.0.1	First release.				#
# 04/08/2022	MG	1.0.2	Add new config file build.		#
# 09/08/2023	MG	1.0.3	Enable use of v1.1.1~rc1 type vesrion	#
# 02/09/2023	MG	1.1.0	Change project name to differentiate	#
#				from new openSUSE package.		#
#									#
#########################################################################


ACLOCAL_AMFLAGS = -I m4


AM_DISTCHECK_CONFIGURE_FLAGS =


SUBDIRS = src/conf/etc
SUBDIRS += src/man/1
SUBDIRS += src/prg/bash


doc_DATA = AUTHORS ChangeLog COPYING NEWS README


EXTRA_DIST = $(srcdir)/AUTHORS $(srcdir)/ChangeLog $(srcdir)/COPYING \
		$(srcdir)/NEWS $(srcdir)/README $(srcdir)/misc


srctarball:
	@cwd="$${PWD}" && \
	varg="$$(echo @PACKAGE_VERSION@ | sed -e s/\-rc/\~rc/ )" && \
	targ="$${cwd}/@PACKAGE_TARNAME@-$${varg}.tar.gz" && \
	cd @srcdir@ && \
	echo "making srctarball from @srcdir@" && \
	echo "GA	$${targ}" && \
	git archive --format=tar.gz \
		--prefix=@PACKAGE_TARNAME@-$${varg}/ \
		--output=$${targ} \
		HEAD && \
	cd -

