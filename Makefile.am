SUBDIRS = abstract desktop nature po

dist-hook:
	@if test -d "$(srcdir)/.git"; \
	then \
		echo Creating ChangeLog && \
		( cd "$(top_srcdir)" && \
		  echo '# Generated by Makefile. Do not edit.'; echo; \
		  $(top_srcdir)/missing --run git log --stat -M -C \
		 --name-status --date=short MATE_BACKGROUNDS_2_30_0.. ) \
		 > ChangeLog.tmp \
		&& mv -f ChangeLog.tmp $(top_distdir)/ChangeLog \
		|| ( rm -f ChangeLog.tmp ; \
		     echo Failed to generate ChangeLog >&2; exit 1 ); \
	else \
		echo A git clone is required to generate a ChangeLog >&2; \
	fi


EXTRA_DIST = \
	MAINTAINERS

DISTCLEANFILES = \
	intltool-extract \
	intltool-merge \
	intltool-update

MAINTAINERCLEANFILES = \
	Makefile.in \
	aclocal.m4 \
	config.h.in \
	configure \
	depcomp \
	install-sh \
	intltool-extract.in \
	intltool-merge.in \
	intltool-update.in \
	missing \
	mkinstalldirs


-include $(top_srcdir)/git.mk
