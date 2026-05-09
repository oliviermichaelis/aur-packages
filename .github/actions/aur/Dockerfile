# Source: https://github.com/JamieMagee/aur-packages/blob/main/.github/actions/aur/Dockerfile
FROM docker.io/library/archlinux:base-devel

RUN pacman -Syu --needed --noconfirm pacman-contrib namcap git sudo unzip && \
  useradd -m builder && \
  echo 'builder ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

WORKDIR /home/builder
USER builder

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT [ "/entrypoint.sh" ]
