# Changes to apply on ux.symfony.com

This directory contains the files modified or added in the `ux.symfony.com` project to integrate the Catalyst kit.
The directory structure mirrors that of the target project.

## Installation

### 1. Kit symlink

```bash
rm -rf vendor/symfony/ux-toolkit/kits/catalyst
ln -s /path/to/symfony-ux-toolkit-catalyst vendor/symfony/ux-toolkit/kits/catalyst
```

### 2. Copy files

Copy the files from this directory (except this README) into the `ux.symfony.com` project, preserving the directory structure:

- `assets/icons/toolkit/catalyst.svg` — kit icon (new)
- `assets/styles/toolkit-catalyst.css` — Tailwind stylesheet (new)
- `assets/toolkit-catalyst.js` — JS entrypoint (registers the `dropdown` Stimulus controller)
- `composer.json` — added `tailwind:build` command for catalyst
- `config/packages/symfonycasts_tailwind.yaml` — added catalyst CSS file
- `config/packages/asset_mapper.yaml` — registered the symlinked catalyst kit as its own
  mapped path so its JS assets (e.g. `dropdown_controller.js`) resolve
- `importmap.php` — added `toolkit-catalyst` entrypoint + the `dropdown` controller asset
- `src/Enum/ToolkitKitId.php` — added `Catalyst` case
- `templates/toolkit/docs/catalyst/*.md.twig` — one documentation page per component
  (alert, avatar, badge, button, checkbox, combobox, description-list, dialog, divider,
  dropdown, fieldset, heading, input, listbox, navbar, pagination, radio, select, sidebar,
  switch, table, text, textarea)
