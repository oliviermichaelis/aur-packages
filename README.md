# aur-packages

Packages maintained by myself

## Create new package

```bash
mkdir <pkgname>
touch ${pkgname}/PKGDIR ${pkgname}/.SRCINFO
git commit
aurpublish ${pkgname}
```

## Update instructions

* Change `pkgver` in `PKGBUILD`
* Regenerate checksum with `updpkgsums`
* Update `.SRCINFO` with `makepkg --printsrcinfo > .SRCINFO`

### Test locally

* `makepkg`
* `yay -U <package>.pkg.tar.zst`

### Push changes

* After making the change and committing, just `aurpublish <package_name>`
