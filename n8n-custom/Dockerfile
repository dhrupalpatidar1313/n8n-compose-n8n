FROM n8nio/n8n:latest

USER root

RUN apk add --no-cache \
    python3 \
    py3-pip \
    py3-virtualenv \
    curl \
    ffmpeg \
    yt-dlp \
    git \
    bash \
    nano \
    jq \
    wget \
    unzip \
    openssh \
    libc6-compat \
    libstdc++ \
    build-base \
    ca-certificates \
    imagemagick \
    tesseract-ocr \
    nodejs \
    npm \
    chromium \
    chromium-chromedriver

# Create and activate a virtualenv for safe pip installs
RUN python3 -m venv /opt/venv && \
    . /opt/venv/bin/activate && \
    pip install --upgrade pip && \
    pip install \
        requests \
        pandas \
        beautifulsoup4 \
        lxml \
        selenium \
        opencv-python-headless

# Clean up
RUN rm -rf /var/cache/apk/*

USER node
