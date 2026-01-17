# Fork: Directory-Based Theme Structure

This is a fork of [tinted-theming/schemes](https://github.com/tinted-theming/schemes) restructured for [vogix16](https://github.com/i-am-logger/vogix16).

## Why This Fork?

The upstream repository stores each theme variant as a separate file (e.g., `solarized-dark.yaml`, `solarized-light.yaml`). This makes it difficult to programmatically identify which files belong to the same theme family.

This fork restructures themes into a **directory-based format** where:
- **Directory name** = theme name
- **File name** = variant name

## Structure

```
base16/
├── solarized/
│   ├── dark.yaml
│   └── light.yaml
├── catppuccin/
│   ├── frappe.yaml
│   ├── latte.yaml
│   ├── macchiato.yaml
│   └── mocha.yaml
├── gruvbox/
│   ├── dark.yaml
│   ├── dark-hard.yaml
│   ├── dark-medium.yaml
│   ├── dark-pale.yaml
│   ├── dark-soft.yaml
│   ├── light.yaml
│   ├── light-hard.yaml
│   ├── light-medium.yaml
│   └── light-soft.yaml
├── dracula/
│   └── default.yaml      # single-variant themes use default.yaml
└── ...

base24/
└── (same structure)
```

## Conventions

1. **Theme grouping**: Themes from the same author/project with a shared color palette are grouped together
2. **Separate themes**: Different authors or distinct palettes get separate directories (e.g., `gruvbox/` vs `gruvbox-material/`)
3. **Single-variant themes**: Use `default.yaml` as the filename
4. **Variant naming**: Derived from original filename by removing the theme prefix

## Adding New Themes

1. Create a directory with your theme name: `base16/my-theme/`
2. Add variant files: `dark.yaml`, `light.yaml`, or `default.yaml` for single-variant
3. Follow the [base16 spec](https://github.com/tinted-theming/home/blob/main/styling.md)

## Syncing with Upstream

To pull new themes from upstream:

```bash
git fetch upstream spec-0.11
git merge upstream/spec-0.11
# Restructure any new flat files into directory format
```

## Statistics

- **base16**: 180 theme directories (from 303 files)
- **base24**: 159 theme directories (from 184 files)
