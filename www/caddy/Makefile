# $NetBSD: Makefile,v 1.27 2020/07/17 18:04:31 bsiegert Exp $

DISTNAME=	caddy-${GITHUB_TAG:S/v//}
PKGREVISION=	14
CATEGORIES=	www
MASTER_SITES=	${MASTER_SITE_GITHUB:=mholt/}
GITHUB_TAG=	v0.11.4

MAINTAINER=	bsiegert@NetBSD.org
HOMEPAGE=	${MASTER_SITE_GITHUB:=mholt/caddy/}
COMMENT=	General-purpose web server
LICENSE=	apache-2.0

GO_DIST_BASE=		${DISTNAME}
GO_SRCPATH=		github.com/mholt/caddy
GO_BUILD_PATTERN=	${GO_SRCPATH}/caddy

CHECK_RELRO_SKIP+=	bin/caddy

EXTRACT_USING=		bsdtar

INSTALLATION_DIRS=	bin

do-install:
	${INSTALL_PROGRAM} ${WRKDIR}/bin/caddy ${DESTDIR}${PREFIX}/bin

.include "../../lang/go/go-package.mk"
.include "../../mk/bsd.pkg.mk"
