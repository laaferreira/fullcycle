FROM golang:alpine AS build

WORKDIR /app

COPY . .

RUN go build  main.go

FROM scratch

WORKDIR /

COPY --from=build /app /

EXPOSE 8080
ENTRYPOINT [ "/main" ]


