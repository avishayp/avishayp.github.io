FROM alpine:3.8

ENV HUGO_VERSION 0.56.1
ENV HUGO_BINARY hugo_${HUGO_VERSION}_Linux-64bit

WORKDIR /srv

# use wget instead of ADD for better caching (we don't expect the source to change)
RUN wget https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/${HUGO_BINARY}.tar.gz

RUN tar -xvf ${HUGO_BINARY}.tar.gz \
	&& mv hugo /usr/local/bin/ \
	&& rm -f *

EXPOSE 1313
ENTRYPOINT ["hugo"]