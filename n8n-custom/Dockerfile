FROM n8nio/n8n:latest

USER root

RUN apk add --no-cache \
    python3 \
    py3-pip \
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

# Upgrade pip and install some Python packages globally
RUN pip3 install --upgrade pip && \
    pip3 install \
    requests \
    pandas \
    beautifulsoup4 \
    lxml \
    selenium \
    opencv-python-headless

# Clean up to reduce image size
RUN rm -rf /var/cache/apk/*

USER node
