# RyanDesk server: fork do rustdesk-server (AGPL-3.0, créditos ao projeto RustDesk).
FROM rust:1.85-bookworm AS build
RUN apt-get update && apt-get install -y --no-install-recommends libsodium-dev pkg-config && rm -rf /var/lib/apt/lists/*
WORKDIR /src
COPY . .
ENV SODIUM_USE_PKG_CONFIG=1
RUN cargo build --release --bin hbbs --bin hbbr

FROM debian:bookworm-slim
RUN apt-get update && apt-get install -y --no-install-recommends libsodium23 ca-certificates && rm -rf /var/lib/apt/lists/*
COPY --from=build /src/target/release/hbbs /src/target/release/hbbr /usr/bin/
WORKDIR /root
