PORTNAME=	silo
DISTVERSION=	${GH_TAGNAME:S/RELEASE.//:C/[-ZT.]//g}.0.0
CATEGORIES=	www
PKGNAMESUFFIX=	-pgsty

MAINTAINER=	0mp@FreeBSD.org
COMMENT=	Object storage comaptible with MinIO and S3
WWW=		https://silo.pgsty.com

LICENSE=	AGPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		compiler go:modules
USE_GITHUB=	yes
GH_ACCOUNT=	pgsty
# NOTE: Refresh _COMMIT_ID when updating.
GH_TAGNAME=	RELEASE.2026-09-16T00-00-00Z
USE_RC_SUBR=	${PORTNAME}

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

SUB_LIST=	DBDIR=${_DBDIR} \
		GROUP="${GROUPS}" \
		LOGFILE="${_LOGFILE}" \
		ROOT_PASSWORD="${_ROOT_PASSWORD}" \
		ROOT_USER="${_ROOT_USER}" \
		USER="${USERS}"

USERS=		${_NAME}
GROUPS=		${_NAME}

PLIST_FILES=	bin/${PORTNAME}

_COMMIT_ID=	2a4d51406b7ed87af5fe6fe0f801f3290f96eb3c
_DBDIR=		/var/db/${_NAME}
_LOGFILE=	/var/log/${_NAME}.log
_MODULE=	github.com/pgsty/silo
_NAME=		${PORTNAME}
_ROOT_PASSWORD=	${_NAME}
_ROOT_USER=	${_NAME}

.include <bsd.port.mk>
