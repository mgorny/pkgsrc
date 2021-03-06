# $NetBSD: Makefile,v 1.64 2020/07/07 13:47:41 ryoon Exp $

DISTNAME=	vala-0.48.7
CATEGORIES=	lang gnome
MASTER_SITES=	${MASTER_SITE_GNOME:=sources/vala/${PKGVERSION_NOREV:R}/}
EXTRACT_SUFX=	.tar.xz

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://wiki.gnome.org/Projects/Vala
COMMENT=	Compiler for the GObject type system
LICENSE=	gnu-lgpl-v2.1

BUILD_DEPENDS+=		libxslt-[0-9]*:../../textproc/libxslt

GNU_CONFIGURE=		yes
USE_LIBTOOL=		yes
USE_TOOLS+=		bash:test bison flex gmake pkg-config

PKGCONFIG_OVERRIDE+=	libvala.pc.in
PKGCONFIG_OVERRIDE+=	vapigen/vapigen.pc.in

REPLACE_BASH+=		tests/testrunner.sh
REPLACE_BASH+=		valadoc/tests/testrunner.sh

# as of 0.48.6
# 43 of 910 tests failed
TEST_TARGET=		check

BUILDLINK_API_DEPENDS.glib2+=	glib2>=2.48.0
.include "../../devel/glib2/buildlink3.mk"
.include "../../devel/libltdl/buildlink3.mk"
.include "../../graphics/graphviz/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
