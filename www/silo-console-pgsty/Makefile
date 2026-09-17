PORTNAME=	silo-console
DISTVERSIONPREFIX=	v
# NOTE: Refresh _COMMIT_ID when updating.
DISTVERSION=	2.4.1
CATEGORIES=	www
PKGNAMESUFFIX=	-pgsty

MAINTAINER=	0mp@FreeBSD.org
COMMENT=	Web UI for Silo object storage
WWW=		https://silo.pgsty.com

LICENSE=	AGPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		go:modules
USE_GITHUB=	yes
GH_ACCOUNT=	pgsty

GO_MOD_DIST=	github
GO_MODULE=	${_MODULE}@${GH_TAGNAME}
GO_TARGET=	./cmd/console:${PORTNAME}
GO_BUILDFLAGS=	-ldflags=' \
		-X ${_MODULE}/cmd.Version=${DISTVERSIONFULL} \
		-X ${_MODULE}/cmd.ReleaseTag=${DISTVERSIONFULL} \
		-X ${_MODULE}/cmd.CommitID=${_COMMIT_ID} \
		-X ${_MODULE}/cmd.ShortCommitID=${_COMMIT_ID:C|(............).*|\1|} \
		-X ${_MODULE}/cmd.GOPATH=${WRKSRC} \
		${STRIP} \
		-w'

PLIST_FILES=	bin/${PORTNAME}

_COMMIT_ID=	1360e26d976d82eda395b0b2e449df8c9d49f39c
_MODULE=	github.com/pgsty/silo-console

.include <bsd.port.mk>
