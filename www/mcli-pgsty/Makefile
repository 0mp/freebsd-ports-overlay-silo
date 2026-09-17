PORTNAME=	mcli
DISTVERSION=	${GH_TAGNAME:S/RELEASE.//:C/[-ZT.]//g}.0.0
CATEGORIES=	www
PKGNAMESUFFIX=	-pgsty

MAINTAINER=	0mp@FreeBSD.org
COMMENT=	Silo object storage client
WWW=		https://silo.pgsty.com

LICENSE=	AGPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		go:modules
USE_GITHUB=	yes
GH_ACCOUNT=	pgsty
GH_PROJECT=	mc
# NOTE: Refresh _COMMIT_ID when updating.
GH_TAGNAME=	RELEASE.2026-09-16T00-00-00Z

GO_MOD_DIST=	github
GO_MODULE=	${_MODULE}@${GH_TAGNAME}
GO_BUILDFLAGS=	-ldflags=' \
		-X ${_MODULE}/cmd.Version=${GH_TAGNAME:C/RELEASE\.//:C|(..)-(..)-(..)Z|\1:\2:\3Z|} \
		-X ${_MODULE}/cmd.ReleaseTag=${GH_TAGNAME} \
		-X ${_MODULE}/cmd.CommitID=${_COMMIT_ID} \
		-X ${_MODULE}/cmd.ShortCommitID=${_COMMIT_ID:C|(............).*|\1|} \
		-X ${_MODULE}/cmd.GOPATH=${WRKSRC} \
		${STRIP} \
		-w'

PLIST_FILES=	bin/mcli

_COMMIT_ID=	e952aa78f10a2b77dd525a2b7e3143bcda0cd377
_MODULE=	github.com/pgsty/mc

.include <bsd.port.mk>
