ARG ARCH
FROM --platform=$TARGETPLATFORM rust:slim-bullseye as runtime

WORKDIR /app
COPY target/${ARCH}/release/xt /app/xt

# Create a non-root user to run the application
RUN useradd -m -u 1000 -U app && \
    chown -R app:app /app

USER app

ENTRYPOINT ["/app/xt"]
