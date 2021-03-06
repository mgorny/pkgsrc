# $NetBSD: Makefile,v 1.28 2020/01/26 17:32:03 rillig Exp $
#

DISTNAME=	john-1.8.0
CATEGORIES=	security textproc
MASTER_SITES=	http://www.openwall.com/john/j/
EXTRACT_SUFX=	.tar.xz

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://www.openwall.com/john/
COMMENT=	Unix Password Cracker
LICENSE=	gnu-gpl-v2

NO_CONFIGURE=	yes
BUILD_DIRS=	src
TEST_TARGET=	check

.include "../../mk/compiler.mk"
.include "../../mk/bsd.prefs.mk"

.if ${OPSYS} == "SunOS"
JOHN_ARCH.i386=		x86-any
JOHN_ARCH.sparc=	sparc
JOHN_ARCH.sparc64=	sparcv9
JOHN_ARCH.x86_64=	x86-64
JOHN_CC.gcc=		gcc
JOHN_CC.sunpro=		cc
BUILD_TARGET=		solaris-${JOHN_ARCH.${MACHINE_ARCH}}-${JOHN_CC.${PKGSRC_COMPILER}}
.elif ${OPSYS} == "NetBSD"
.  if ${MACHINE_ARCH} == "i386"
BUILD_TARGET=		openbsd-x86-any
.  elif ${MACHINE_ARCH} == "x86_64"
BUILD_TARGET=		openbsd-x86-64
.  elif ${MACHINE_ARCH} == "sparc64"
BUILD_TARGET=		netbsd-sparc64
.  elif ${MACHINE_ARCH} == "sparc"
BUILD_TARGET=		openbsd-sparc
.  elif ${MACHINE_ARCH} == "alpha"
BUILD_TARGET=		openbsd-alpha
.  elif ${MACHINE_ARCH} == "powerpc"
BUILD_TARGET=		openbsd-ppc32
.  elif ${MACHINE_ARCH} == "powerpc64"
BUILD_TARGET=		openbsd-ppc64
.  elif ${MACHINE_ARCH} == "vax"
BUILD_TARGET=		netbsd-vax
.  else
BUILD_TARGET=		generic
.  endif
.elif ${OPSYS} == "OpenBSD"
.  if ${MACHINE_ARCH} == "i386"
BUILD_TARGET=		openbsd-x86-any
.  elif ${MACHINE_ARCH} == "x86_64"
BUILD_TARGET=		openbsd-x86-64
.  elif ${MACHINE_ARCH} == "sparc64"
BUILD_TARGET=		openbsd-sparc64
.  elif ${MACHINE_ARCH} == "sparc"
BUILD_TARGET=		openbsd-sparc
.  elif ${MACHINE_ARCH} == "alpha"
BUILD_TARGET=		openbsd-alpha
.  elif ${MACHINE_ARCH} == "powerpc"
BUILD_TARGET=		openbsd-ppc32
.  elif ${MACHINE_ARCH} == "powerpc64"
BUILD_TARGET=		openbsd-ppc64
.  else
BUILD_TARGET=		generic
.  endif
.else
BUILD_TARGET=		generic
.endif

INSTALLATION_DIRS=	bin share/john

SUBST_CLASSES+=		john
SUBST_STAGE.john=	pre-build
SUBST_FILES.john=	src/params.h
SUBST_VARS.john=	PREFIX

do-install:
	# programs and scripts
	${INSTALL_PROGRAM} ${WRKSRC}/run/john ${DESTDIR}${PREFIX}/bin
	${INSTALL_SCRIPT} ${WRKSRC}/run/mailer ${DESTDIR}${PREFIX}/bin
	# configuration file
	${INSTALL_DATA} ${WRKSRC}/run/john.conf ${DESTDIR}${PREFIX}/share/john
	# symbolic links
.for i in unafs unique unshadow
	${LN} -sf john ${DESTDIR}${PREFIX}/bin/${i}
.endfor
	# data files
.for i in ascii.chr digits.chr lm_ascii.chr password.lst
	${INSTALL_DATA} ${WRKSRC}/run/${i} ${DESTDIR}${PREFIX}/share/john
.endfor

.include "../../mk/bsd.pkg.mk"
