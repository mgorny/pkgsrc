# $NetBSD: Makefile,v 1.17 2019/08/11 13:17:55 wiz Exp $

DISTNAME=	CDDB-File-1.05
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	11
CATEGORIES=	audio perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=CDDB/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://metacpan.org/release/CDDB-File
COMMENT=	Parses a CDDB/freedb data file
LICENSE=	gnu-gpl-v2

PERL5_PACKLIST=	auto/CDDB/File/.packlist

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
