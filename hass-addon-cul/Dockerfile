ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

ADD package.json /


RUN \ 
    apt-get update \
    \
    && apt-get install nodejs npm \
    && npm install -g --unsafe-perm cul2mqtt \
    && apt-get -y clean

# Copy data for add-on
COPY run.sh /
# COPY index.js /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
