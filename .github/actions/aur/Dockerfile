# Source: https://github.com/JamieMagee/aur-packages/blob/main/.github/actions/aur/Dockerfile
FROM docker.io/library/archlinux:base-devel@sha256:f557e49eaad9b696f0ef71cd12f2a2418407c8d4c441f311c38bd95186afd85f

RUN pacman -Syu --needed --noconfirm pacman-contrib namcap git sudo unzip && \
  useradd -m builder && \
  echo 'builder ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

WORKDIR /home/builder
USER builder

RUN git clone https://aur.archlinux.org/paru.git && \
  cd paru && makepkg -si --noconfirm && cd .. && rm -rf paru

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT [ "/entrypoint.sh" ]
