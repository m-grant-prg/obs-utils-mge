#########################################################################
#									#
# Author: Copyright (C) 2022-2024  Mark Grant				#
#									#
# Released under the GPLv3 only.					#
# SPDX-License-Identifier: GPL-3.0-only					#
#									#
# Purpose:								#
#	AutoMake script file to generate obs-utils-mge manual pages	#
# from source.								#
#									#
#########################################################################


oscbuilder.sh.1: Makefile
	mkdir -p $(@D)
	rm -f $@ $@.tmp
	$(edit) $(srcdir)/$(@F).man.in > $@.tmp
	targfile=$(@F);	\
	if [[ $$targfile == *"."* ]]; then \
		if [[ $${targfile##*.} == "" ]]; then \
			echo "Source file suffix used as section but empty."; \
			exit 1; \
		else \
			section=$${targfile##*.}; \
		fi; \
	else \
		echo "Source file suffix used as section but no dot & empty."; \
		exit 1; \
	fi; \
	txt2manwrap $(@F) $$section "OBS Utilities Manual" $@.tmp $@
	rm -f $@.tmp

oscbuilder.sh.1: $(srcdir)/oscbuilder.sh.1.man.in

man_MANS = oscbuilder.sh.1

EXTRA_DIST = $(srcdir)/oscbuilder.sh.1.man.in

CLEANFILES = *.tmp oscbuilder.sh.1

