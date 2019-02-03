FROM jeremycurny/php-magento2:7.1-fpm-stretch

MAINTAINER "Jeremy CURNY" <jeremy.curny.pro@gmail.com>

ARG DEBIAN_FRONTEND=noninteractive

ENV MAGENTO_ARTIFACT_NAME m2-ce230.tar.gz
ENV MAGENTO_PROJECT_VERSION 2.3.0

RUN \
  docker-php-magento2-ext-create-artifact $MAGENTO_PROJECT $MAGENTO_PROJECT_VERSION $MAGENTO_ARTIFACT_NAME

COPY docker-php-magento2-entrypoint /usr/local/bin/
RUN chmod +x /usr/local/bin/docker-php-magento2-*

ENTRYPOINT ["docker-php-magento2-entrypoint"]
EXPOSE 9000
CMD ["php-fpm"]
