# 
#  fontconfig/fc-cat/Makefile.am
# 
#  Copyright © 2003 Keith Packard
# 
#  Permission to use, copy, modify, distribute, and sell this software and its
#  documentation for any purpose is hereby granted without fee, provided that
#  the above copyright notice appear in all copies and that both that
#  copyright notice and this permission notice appear in supporting
#  documentation, and that the name of Keith Packard not be used in
#  advertising or publicity pertaining to distribution of the software without
#  specific, written prior permission.  Keith Packard makes no
#  representations about the suitability of this software for any purpose.  It
#  is provided "as is" without express or implied warranty.
# 
#  THE AUTHOR(S) DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
#  INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS, IN NO
#  EVENT SHALL THE AUTHOR(S) BE LIABLE FOR ANY SPECIAL, INDIRECT OR
#  CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE,
#  DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER
#  TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
#  PERFORMANCE OF THIS SOFTWARE.

DOC2MAN = docbook2man

FC_CAT_SRC=${top_srcdir}/fc-cat

SGML = ${FC_CAT_SRC}/fc-cat.sgml

INCLUDES=-I${top_srcdir} $(WARN_CFLAGS)

bin_PROGRAMS=fc-cat

BUILT_MANS=fc-cat.1

if ENABLE_DOCS
man_MANS=${BUILT_MANS}
endif

EXTRA_DIST=fc-cat.sgml ${BUILT_MANS}

fc_cat_LDADD = ${top_builddir}/src/libfontconfig.la

if USEDOCBOOK

${man_MANS}: ${SGML}	
	$(RM) $@
	$(DOC2MAN) ${SGML}
	$(RM) manpage.*

all-local: $(man_MANS)

clean-local:
	$(RM) $(man_MANS)

else
all-local:
clean-local:
endif
