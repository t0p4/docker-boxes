FROM inetsoftware/alpine-tesseract:4.0.0-beta4-tess4j as builder

# dummy 

FROM inetsoftware/alpine-java-gradle
LABEL maintainer contact@inetsoftware.de

ENV LC_ALL C

RUN mkdir -p /usr/share/tessdata
ADD https://github.com/tesseract-ocr/tessdata/raw/master/eng.traineddata /usr/share/tessdata/eng.traineddata
ADD https://github.com/tesseract-ocr/tessdata/raw/master/deu.traineddata /usr/share/tessdata/deu.traineddata

COPY --from=builder /tesseract/tesseract-git-4.* /tesseract/

RUN set -x \
    && echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories \
    && apk add --update --allow-untrusted /tesseract/tesseract-git-* \
    && rm  -rf /tesseract \
    && echo "done"
