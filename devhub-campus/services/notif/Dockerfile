# ---- Stage 1 : build du binaire Go ----
FROM golang:1.26.4-alpine AS build

WORKDIR /src

COPY go.mod ./
RUN go mod download

COPY cmd ./cmd
RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w" -o /out/notif ./cmd

# ---- Stage 2 : runtime minimal non-root ----
FROM gcr.io/distroless/static:nonroot AS runtime

LABEL org.opencontainers.image.source="https://github.com/PepMama/esgi-tp-argoCD"

COPY --from=build /out/notif /notif

ENV PORT=8080 \
    LOG_LEVEL=info

EXPOSE 8080

USER nonroot:nonroot
ENTRYPOINT ["/notif"]
