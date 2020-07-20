# $NetBSD: Makefile,v 1.4 2015/02/16 10:15:47 jperkin Exp $

PKGNAME=	suse_webkitgtk-${SUSE_VERSION}
CATEGORIES=	emulators
RPMPKGS+=	libwebkitgtk-1_0-0-2.2.1-1.1.${SUSE_ARCH}.rpm

MAINTAINER=	pkgsrc-users@NetBSD.org
COMMENT=	Linux compatibility package for expat

EMUL_MODULES.linux=	base

.include "../../emulators/suse131_linux/Makefile.common"
.include "../../mk/bsd.pkg.mk"
