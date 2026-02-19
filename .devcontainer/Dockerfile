FROM ubuntu:noble

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    cmake \
    ninja-build \
    clang \
    libstdc++-14-dev \
    python3 \
    python3-dev \
    python3-pip \
    python3-venv \
    libeigen3-dev \
    libgl1-mesa-dev \
    libglu1-mesa-dev \
    gdb \
    curl \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

ENV CC=clang CXX=clang++

# Create non-root user (ubuntu:noble ships a 'ubuntu' user at UID 1000; remove it first)
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID
RUN userdel -r ubuntu 2>/dev/null || true \
    && groupadd --gid $USER_GID $USERNAME 2>/dev/null || true \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME \
    && rm -rf /var/lib/apt/lists/*
