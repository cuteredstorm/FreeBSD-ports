# $FreeBSD$

PORTNAME=	opencollada
PORTVERSION=	1.2.2.20150519
CATEGORIES=	graphics devel

MAINTAINER=	mva@FreeBSD.org
COMMENT=	Library for reading and writing COLLADA files

LICENSE=	MIT

BROKEN_powerpc64=	Does not build

LIB_DEPENDS=	libpcre.so:devel/pcre

USE_GITHUB=	yes
GH_ACCOUNT=	KhronosGroup
GH_PROJECT=	OpenCOLLADA
GH_TAGNAME=	a59a438

USE_GNOME=	libxml2
USE_LDCONFIG=	${PREFIX}/lib/opencollada
USES=		cmake:outsource compiler iconv pkgconfig
CFLAGS+=	-I/${LOCALBASE}/include
CMAKE_ARGS+=	-DUSE_SHARED:BOOL=ON -DUSE_STATIC:BOOL=OFF

BROKEN_sparc64=	cannot build: runaway process

post-patch:
	@${REINPLACE_CMD} -e 's|$${OPENCOLLADA_INST_LIBRARY}/cmake|${PREFIX}/share/cmake/Modules|' \
		${WRKSRC}/CMakeLists.txt

.include <bsd.port.mk>
