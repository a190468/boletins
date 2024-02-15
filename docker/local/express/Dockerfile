ARG NODE_VERSION=16-alpine3.12

FROM node:${NODE_VERSION}

LABEL name="SION Boletins"
LABEL license="MIT"
LABEL description="SION Boletins image"

ENV NODE_ENV=development

ARG APP_HOME=/app

WORKDIR ${APP_HOME}

RUN addgroup --system boletins \
    && adduser --system --ingroup boletins boletins 

COPY package*.json ./

RUN npm install

COPY --chown=boletins:boletins . ${APP_HOME}

RUN chown boletins:boletins ${APP_HOME}

USER boletins

CMD [ "npm", "run", "dev" ]

