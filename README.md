# pac
pac, or simply `p`, is a package manager for macOS, Windows and Linux.

This repo is just an idea of how this could work.

## pac.yml
```yml
name: Example
version: ~1.0.0
registries: pac, go
subregistry: true
scripts:
  start: some kinda go command
  test: idk
dependencies:
  node/example: ^1.0.0
dev_dependencies:
  go: ^1.0.0
  go/gorm: ^1.0.0
```

## pac-stack.yml
A file for managing multiple pac packages. You would be able to run one command to spin up a database, server and frontend package. It should let you run all your tests, builds and deployments too.

## Subregistry
If the `subregistry` option is true, a package will have it's own subregistry. Install a package from a subregistry:
```
p install registry/package
```

Packages can be listed in multiple registries, including the official `pac` registry. This would allow both `p install node/example` `p install example` to work.

### Closed registries
If a subregistry package is closed, only users you authorize, can create child packages.
