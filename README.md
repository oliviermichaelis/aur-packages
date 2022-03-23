# aur-packages
Packages maintained by me

## Update instructions

* Change `pkgver` in `PKGBUILD
* Regenerate checksum with `updpkgsums`
* Update `.SRCINFO` with `makepkg --printsrcinfo > .SRCINFO`

### Test locally

* `makepkg`
* `yay -U <package>.pkg.tar.zst`

### Push changes
* After making the change and committing, just `aurpublish <package_name>`
