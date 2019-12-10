FROM verdaccio/verdaccio:4.3

USER root

ENV node_env=production

RUN apk --no-cache add python make; \
    npm i; \
    cd /verdaccio/plugins; \
    mkdir verdaccio-gitlab; \
    cd $_; \
    npm i verdaccio-gitlab

USER $VERDACCIO_USER_UID
