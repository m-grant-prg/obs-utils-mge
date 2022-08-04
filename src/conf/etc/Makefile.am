#########################################################################
#									#
# Script ID: src/conf/etc/Makefile.am					#
# Author: Copyright (C) 2022  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0-only					#
#									#
# Purpose:								#
# AutoMake script file to install obs-utils configuration files.	#
#									#
#########################################################################

#########################################################################
#									#
# Changelog								#
#									#
# Date		Author	Version	Description				#
#									#
# 04/08/2022	MG	1.0.1	Initial release.			#
#									#
#########################################################################


confdir = $(sysconfdir)


obs-utils.conf: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	test -f ./$@.in || srcdir=$(srcdir)/; \
	$(edit) $${srcdir}$(@F).in > $@.tmp
	mv $@.tmp $@
obs-utils.conf: $(srcdir)/obs-utils.conf.in

conf_DATA = obs-utils.conf

EXTRA_DIST = $(srcdir)/obs-utils.conf.in

CLEANFILES = *.tmp obs-utils.conf

