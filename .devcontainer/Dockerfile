# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.134.0/containers/rust/.devcontainer/base.Dockerfile
FROM mcr.microsoft.com/vscode/devcontainers/rust:0-1

# Install QEMU
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
      qemu-system

# Install rust tools
RUN rustup toolchain install nightly-x86_64-unknown-linux-gnu \
    && rustup component add --toolchain nightly-x86_64-unknown-linux-gnu \
        # VSCode
        rust-analysis rls rust-src \
        # for bootimage
        llvm-tools-preview \
    && cargo install bootimage
