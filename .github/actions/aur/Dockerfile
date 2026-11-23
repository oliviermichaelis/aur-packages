# Source: https://github.com/JamieMagee/aur-packages/blob/main/.github/actions/aur/Dockerfile
FROM docker.io/library/archlinux:base-devel@sha256:a1d4b509c51fc68dcc7ee1f88342fe26b1f65e6775c3aff26f196141e6c76a6f

RUN pacman -Syu --needed --noconfirm pacman-contrib namcap git sudo unzip && \
  useradd -m builder && \
  echo 'builder ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

WORKDIR /home/builder
USER builder

RUN git clone https://aur.archlinux.org/paru.git && \
  cd paru && makepkg -si --noconfirm && cd .. && rm -rf paru

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT [ "/entrypoint.sh" ]
