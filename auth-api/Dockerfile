FROM golang:stretch

EXPOSE 8081

WORKDIR /go/src/app
RUN apt-get install curl git && \
    curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh

COPY . .
#RUN dep ensure

RUN go get -u go.elastic.co/apm
RUN go get -u github.com/dgrijalva/jwt-go
RUN go get -u github.com/labstack/echo

RUN go build -o auth-api

CMD /go/src/app/auth-api
