FROM alpine:3.20

WORKDIR /app

RUN apk add --no-cache curl

COPY mensaje.txt /app/

CMD ["cat", "/app/mensaje.txt"]      
