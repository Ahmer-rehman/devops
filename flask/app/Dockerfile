# Stage 1: Build the application
FROM python:3.10-alpine AS builder

WORKDIR /app

# Copy and install requirements
COPY requirements.txt /app
RUN --mount=type=cache,target=/root/.cache/pip \
    pip install -r requirements.txt

# Copy the rest of the application
COPY . /app

# Set the entry point
ENTRYPOINT ["python3"]
CMD ["app.py"]

# # Stage 2: Development environment
# FROM builder as dev-envs

# # Install required packages
# RUN apk update && \
#     apk add git

# # Create a group and user
# RUN addgroup -S docker && \
#     adduser -S --shell /bin/bash --ingroup docker vscode

# # Install Docker tools (cli, buildx, compose)
# # Note: The following line might not work as expected in a multi-stage build.
# # You may need to adapt it depending on your specific needs.
# COPY --from=gloursdocker/docker / /

# # Note: Multi-platform builds are typically used for building images that can run on multiple platforms.
# # If you don't need multi-platform support, you can simplify the Dockerfile.
