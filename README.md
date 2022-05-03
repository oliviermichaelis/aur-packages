# aur-packages
Packages maintained by me

## Create new package

```bash
mkdir <pkgname>
touch PKGDIR .SRCINFO
```

## Update instructions

* Change `pkgver` in `PKGBUILD
* Regenerate checksum with `updpkgsums`
* Update `.SRCINFO` with `makepkg --printsrcinfo > .SRCINFO`

### Test locally

* `makepkg`
* `yay -U <package>.pkg.tar.zst`

### Push changes
* After making the change and committing, just `aurpublish <package_name>`
