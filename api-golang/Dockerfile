FROM golang:1.19-bullseye AS build

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN go build \
  -ldflags="-linkmode external -extldflags -static" \
  -tags netgo \
  -o api-golang

FROM scratch

WORKDIR /

COPY --from=build /app/api-golang api-golang

CMD ["/api-golang"]
