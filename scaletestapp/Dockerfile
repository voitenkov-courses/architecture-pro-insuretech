FROM golang:1.23-alpine AS build

WORKDIR /src
COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -o /bin/app

FROM scratch
COPY --from=build /bin/app /bin/app

CMD ["/bin/app"]