plugin_name = sharing

libexec_PROGRAMS = csd-sharing
csd_sharing_SOURCES =					\
	csd-sharing-manager.c				\
	csd-sharing-manager.h				\
	csd-sharing-enums.h				\
	main.c

csd_sharing_CFLAGS =			\
	-I$(top_srcdir)/plugins/common	\
	$(SHARING_CFLAGS)		\
	$(PLUGIN_CFLAGS)		\
	$(SETTINGS_PLUGIN_CFLAGS)	\
	$(AM_CFLAGS)
csd_sharing_CPPFLAGS =						\
	-I$(top_srcdir)/cinnamon-settings-daemon			\
	-I$(top_builddir)/cinnamon-settings-daemon			\
	-DCINNAMON_SETTINGS_LOCALEDIR=\""$(datadir)/locale"\"	\
	$(AM_CPPFLAGS)
csd_sharing_LDADD =					\
	$(top_builddir)/cinnamon-settings-daemon/libcsd.la \
	$(SHARING_LIBS)					\
	$(SETTINGS_PLUGIN_LIBS)

desktopdir = $(sysconfdir)/xdg/autostart
desktop_in_files = cinnamon-settings-daemon-sharing.desktop.in
desktop_DATA = $(desktop_in_files:.desktop.in=.desktop)

cinnamon-settings-daemon-sharing.desktop: $(desktop_in_files) Makefile
	$(AM_V_GEN) sed -e "s|\@libexecdir\@|$(libexecdir)|" $< > $@

EXTRA_DIST = $(desktop_in_files)
CLEANFILES = $(desktop_DATA)
DISTCLEANFILES = $(desktop_DATA)
