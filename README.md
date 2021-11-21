# aur-packages
Packages maintained by me

## Update instructions

* Change `pkgver` in `PKGBUILD
* Regenerate checksum with `updpkgsums`
* Update `.SRCINFO` with `makepkg --printsrcinfo > .SRCINFO`

### Push changes
* `git push`
* `git push aur master`
