FROM fluent/fluentd:latest

WORKDIR /home/fluent
ENV PATH /home/fluent/.gem/ruby/2.4.0/bin:$PATH
RUN apk --no-cache --update add build-base ruby-dev geoip geoip-dev libmaxminddb libmaxminddb-dev snappy-dev ruby-bundler \
    && gem install \
    fluent-plugin-prometheus \
    zookeeper \
    snappy \
    fluent-plugin-kafka \
    fluent-plugin-s3 \
    fluent-plugin-sentry \
    fluent-plugin-elasticsearch \
    strptime \
    geoip2_c \
    geoip2_compat \
    fluent-plugin-multi-format-parser \
    fluent-plugin-genhashvalue \
    fluent-plugin-geoip \
    && rm -rf /home/fluent/.gem/ruby/2.4.0/cache/*.gem && gem sources -c \
    && apk del build-base ruby-dev geoip-dev libmaxminddb-dev ruby-bundler && rm -rf /var/cache/apk/*