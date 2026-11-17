FROM nvidia/cuda:11.8.0-cudnn8-devel-ubuntu22.04

ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONUNBUFFERED=1
ENV PATH="/root/.local/bin:${PATH}"

WORKDIR /app

# 1. Install System Tools, Python 3.11, C++ Toolchain, and Robotics/CV Dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    software-properties-common \
    && add-apt-repository ppa:deadsnakes/ppa -y \
    && apt-get update && apt-get install -y --no-install-recommends \
    git \
    curl \
    wget \
    build-essential \
    gdb \
    cmake \
    ninja-build \
    pkg-config \
    # Computer Vision & Image I/O
    libopencv-dev \
    ffmpeg \
    libgl1-mesa-glx \
    libglib2.0-0 \
    # Linear Algebra & Optimization for Robotics
    libeigen3-dev \
    libceres-dev \
    # GUI & Display Dependencies
    libx11-6 \
    libxext6 \
    libxrender1 \
    libxrandr2 \
    libxcursor1 \
    libxinerama1 \
    libxi6 \
    libegl1 \
    libosmesa6-dev \
    python3-tk \
    # Python Environment
    python3.11 \
    python3.11-dev \
    python3.11-venv \
    && rm -rf /var/lib/apt/lists/*

# 2. Set Python defaults and install uv
RUN ln -sf /usr/bin/python3.11 /usr/bin/python \
    && ln -sf /usr/bin/python3.11 /usr/bin/python3 \
    && curl -LsSf https://astral.sh/uv/install.sh | sh

CMD ["sleep", "infinity"]