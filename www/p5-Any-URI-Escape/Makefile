# $NetBSD: Makefile,v 1.7 2019/08/11 13:24:22 wiz Exp $

DISTNAME=	Any-URI-Escape-0.01
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	5
CATEGORIES=	devel
MASTER_SITES=	https://cpan.metacpan.org/authors/id/P/PH/PHRED/
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=Any/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://cpan.metacpan.org/authors/id/P/PH/PHRED/
COMMENT=	Load URI::Escape::XS preferentially over URI::Escape
LICENSE=	${PERL5_LICENSE}

DEPENDS+=	p5-URI-[0-9]*:../../www/p5-URI

PERL5_PACKLIST=	auto/Any/URI/Escape/.packlist
USE_LANGUAGES=	# none

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
