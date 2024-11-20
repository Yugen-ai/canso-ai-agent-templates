FROM --platform=linux/amd64 python:3.9.18-slim

# Use ARG to declare build arguments
ARG IMAGE_VERSION
ARG BUILD_TIMESTAMP
ARG PR_NUMBER

# Set labels in the image
LABEL version=$IMAGE_VERSION \
    build_timestamp=$BUILD_TIMESTAMP \
    pr_number=$PR_NUMBER

WORKDIR /opt/ai-agent/

RUN mkdir src

COPY src ./src
COPY config.yaml ./config.yaml
COPY requirements.txt ./

RUN pip3 install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD ["uvicorn", "src.main:app", "--host", "0.0.0.0", "--port", "8000"]
