# Source: https://github.com/JamieMagee/aur-packages/blob/main/.github/actions/aur/Dockerfile
FROM docker.io/library/archlinux:base-devel@sha256:8edb44f40a0cb5d3e44ef474f02780098ce0084e591c8641bdc01f02f185cc40

RUN pacman -Syu --needed --noconfirm pacman-contrib namcap git sudo unzip && \
  useradd -m builder && \
  echo 'builder ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

WORKDIR /home/builder
USER builder

RUN git clone https://aur.archlinux.org/paru.git && \
  cd paru && makepkg -si --noconfirm && cd .. && rm -rf paru

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT [ "/entrypoint.sh" ]
