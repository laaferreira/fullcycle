FROM golang:alpine AS build

WORKDIR /app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
#COPY go.mod ./
#RUN go mod download && go mod verify

COPY . .

RUN go build  main.go

FROM scratch

WORKDIR /

COPY --from=build /app /

EXPOSE 8080
ENTRYPOINT [ "/main" ]
#CMD [ "./fullcycle" ]

