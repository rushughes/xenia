FROM ubuntu:18.04

RUN apt-get update && apt-get install -y \
	varnish

RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV VCL_CONFIG      /etc/varnish/default.vcl
ENV SECRET_FILE     /etc/varnish/secret
ENV CACHE_SIZE      64m
ENV VARNISHD_PARAMS -p default_ttl=3600 -p default_grace=3600 -T 0.0.0.0:6082

COPY    default.vcl /etc/varnish/default.vcl

EXPOSE 80 6082

CMD varnishd -F -f $VCL_CONFIG -S $SECRET_FILE -s malloc,$CACHE_SIZE $VARNISHD_PARAMS
