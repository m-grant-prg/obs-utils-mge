#########################################################################
#									#
# Script ID: src/conf/etc/Makefile.am					#
# Author: Copyright (C) 2022, 2023  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0-only					#
#									#
# Purpose:								#
# AutoMake script file to install obs-utils-mge configuration files.	#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 04/08/2022	MG	1.0.1	Initial release.			#
# 02/09/2023	MG	1.1.0	Change project name to differentiate	#
#				from new openSUSE package.		#
#									#
#########################################################################


confdir = $(sysconfdir)


obs-utils-mge.conf: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	test -f ./$@.in || srcdir=$(srcdir)/; \
	$(edit) $${srcdir}$(@F).in > $@.tmp
	mv $@.tmp $@
obs-utils-mge.conf: $(srcdir)/obs-utils-mge.conf.in

conf_DATA = obs-utils-mge.conf

EXTRA_DIST = $(srcdir)/obs-utils-mge.conf.in

CLEANFILES = *.tmp obs-utils-mge.conf

