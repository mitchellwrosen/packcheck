## Unreleased

* For stack builds, use the same options (STACK_BUILD_OPTIONS) for install test
  as for build so that a rebuild does not occur during install.

## 0.3.0

### Enhancements
* Add cabal new-build support. Use `packcheck.sh cabal-new` to use it.
* Add knobs to disable tests or doc builds (`DISABLE_TEST`, `DISABLE_DOCS`)
* Now you can specify multiple versions of GHC in PATH and packcheck
  automatically finds the right one based on GHCVER envvar.
* Add TOOLS_DIR option to specify hvr-ghc style installation of ghc and
  cabal. A correct version of GHC is automatically picked from this directory.
* GHCVER and CABALVER variables are now optional in travis config if you
  specify the cabal and ghc PPAs under apt sources.
* Run `autoreconf` if there is a `configure.ac` in the package dir

### Deprecations
* TEST_INSTALL option is deprecated, use ENABLE_INSTALL instead

## 0.2.0

### Breaking Changes
* Make `STACK_BUILD_OPTIONS` and `CABAL_CONFIGURE_OPTIONS` append to the
  existing build/configure options instead of overriding them.
* Do not enforce specific `stack` version in CI configs - this is done to avoid
  failures due to github API limits when upgrading or downgrading.

### Bug Fixes
* Avoid build failures in cases when `cabal-install` has to be installed and
  its dependencies may conflict with the current project dependencies.

### Enhancements
* Better documentation in travis and appveyor configs
* Reduce the number of builds in default config from 11 to 6

## 0.1.1

* _Enhancement_: Nix support; fix bash location to make it work on NixOS and
  potentially on other systems.

## 0.1.0

* Initial release
