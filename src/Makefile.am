AM_CFLAGS = $(VARNISHAPI_CFLAGS) -Wall -Werror
AM_LDFLAGS = $(VARNISHAPI_LIBS) $(VMOD_LDFLAGS)

vmod_LTLIBRARIES = libvmod_scale.la

libvmod_scale_la_SOURCES = \
	vmod_scale.c

nodist_libvmod_scale_la_SOURCES = \
	vcc_scale_if.c \
	vcc_scale_if.h

dist_man_MANS = vmod_scale.3

@BUILD_VMOD_SCALE@

AM_TESTS_ENVIRONMENT = \
	PATH="$(VMOD_TEST_PATH)" \
	LD_LIBRARY_PATH="$(VARNISH_LIBRARY_PATH)"
TEST_EXTENSIONS = .vtc
VTC_LOG_COMPILER = varnishtest -v
AM_VTC_LOG_FLAGS = -Dvmod_scale="$(VMOD_SCALE)"

TESTS = @VMOD_TESTS@

EXTRA_DIST = \
	vmod_scale.vcc \
	$(VMOD_TESTS)
