ARG TARGETARCH
FROM rust:slim-bullseye AS runtime

WORKDIR /app

# Define the target architecture
ARG TARGETARCH
ARG RUST_ARCH
ENV RUST_ARCH=${TARGETARCH}

# Copy the appropriate binary based on architecture
COPY target/$RUST_ARCH-unknown-linux-gnu/release/xt /app/xt

# Create a non-root user to run the application
RUN useradd -m -u 1000 -U app && \
    chown -R app:app /app

USER app

ENTRYPOINT ["/app/xt"]
