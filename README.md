# podspawn/podfiles

Community Podfile templates and bases for [podspawn](https://github.com/podspawn/podspawn).

## What's here

- **templates/** - Full starter Podfiles for `podspawn init`. Includes comments, sensible defaults, and common services for each language.
- **bases/** - Minimal Podfiles for the `extends:` field. Meant to be extended, not used directly.
- **registry.yaml** - Machine-readable index of all templates and bases.

## Using templates

```bash
# Auto-detect your project type and scaffold a Podfile
podspawn init

# Use a specific template
podspawn init --template go

# Fetch the latest templates (updates from this repo)
podspawn init --update
```

## Using bases with extends

In your project's `podfile.yaml`:

```yaml
extends: ubuntu-dev
packages: [go@1.24, make]
on_create: go mod download
```

This inherits the base packages (git, curl, ripgrep, fzf, etc.) and adds your project-specific tools on top.

## Contributing

1. Fork this repo
2. Add or modify a template/base YAML file
3. Add a corresponding entry to `registry.yaml`
4. Open a PR

Templates should include comments explaining each field. Bases should be minimal and uncommented.

CI validates that every file has a registry entry and vice versa.

## License

AGPL-3.0 - same as podspawn.
