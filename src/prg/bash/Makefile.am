#########################################################################
#									#
# Script ID: src/prg/bash/Makefile.am					#
# Author: Copyright (C) 2022  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0-only					#
#									#
# Purpose:								#
#	AutoMake script file to generate obs-utils scripts from		#
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
#									#
#########################################################################


oscbuilder.sh: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	test -f ./$@.in || srcdir=$(srcdir)/; \
	$(edit) $${srcdir}$(@F).in > $@.tmp

	mv $@.tmp $@

	chmod a+x $@

oscbuilder.sh: $(srcdir)/oscbuilder.sh.in

bin_SCRIPTS = oscbuilder.sh

EXTRA_DIST = $(srcdir)/oscbuilder.sh.in

CLEANFILES = *.tmp oscbuilder.sh

