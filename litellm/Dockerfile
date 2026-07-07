FROM ghcr.io/berriai/litellm:main-latest

# Install pip into the existing venv (no curl/uv in base image)
RUN /app/.venv/bin/python3 -m ensurepip --upgrade

# Install MLflow for integration
RUN /app/.venv/bin/pip3 install mlflow

# Copy any additional config if needed
WORKDIR /app