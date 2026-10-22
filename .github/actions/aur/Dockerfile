# Source: https://github.com/JamieMagee/aur-packages/blob/main/.github/actions/aur/Dockerfile
FROM docker.io/library/archlinux:base-devel@sha256:2acfa2683d458b7803b7aa4ee3c139d2ba6922cd84666fcb7496a3a02fcc4c83

RUN pacman -Syu --needed --noconfirm pacman-contrib namcap git sudo unzip && \
  useradd -m builder && \
  echo 'builder ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

WORKDIR /home/builder
USER builder

RUN git clone https://aur.archlinux.org/paru.git && \
  cd paru && makepkg -si --noconfirm && cd .. && rm -rf paru

COPY entrypoint.sh /entrypoint.sh

ENTRYPOINT [ "/entrypoint.sh" ]
