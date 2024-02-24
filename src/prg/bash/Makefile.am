#########################################################################
#									#
# Author: Copyright (C) 2022-2024  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0-only					#
#									#
# Purpose:								#
#	AutoMake script file to generate obs-utils-mge scripts from	#
# source.								#
#									#
#########################################################################


oscbuilder: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	test -f ./$@.in || srcdir=$(srcdir)/; \
	$(edit) $${srcdir}$(@F).sh.in > $@.tmp
	mv $@.tmp $@
	chmod a+x $@
oscbuilder: $(srcdir)/oscbuilder.sh.in

bin_SCRIPTS = oscbuilder

EXTRA_DIST = $(srcdir)/oscbuilder.sh.in

CLEANFILES = *.tmp oscbuilder

