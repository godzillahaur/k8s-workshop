FROM fluent/fluentd:v0.12
USER root
RUN apk add --update --virtual .build-deps sudo build-base ruby-dev \
    && sudo gem install fluent-plugin-mongo \
    && sudo gem sources --clear-all \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* /home/fluent/.gem/ruby/2.3.0/cache/*.gem
# RUN fluent-gem install fluent-plugin-mongo
COPY fluent.conf /fluentd/etc/