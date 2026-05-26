# Catalyst Kit for Symfony UX Toolkit

Component kit based on Catalyst UI by Tailwind Plus, ported to Twig for Symfony UX Toolkit.

## Structure

- `divider/` (and future components) — each component has its own directory with:
  - `manifest.json` — metadata, dependencies
  - `templates/components/` — Twig template(s) for the component
  - `examples/` — Twig examples (Demo, Usage, and named examples)
- `ux.symfony.com/` — files to apply on the `ux.symfony.com` project to integrate the kit (see `ux.symfony.com/README.md`)
- `manifest.json` — root kit manifest

## Component conventions

- Use `html_cva()` for CSS classes with variants
- Use `attributes.defaults({...})` on the root element (allows consumers to override values)
- Use `attributes.render('class')` to merge user-provided classes
- Props are declared with `{%- props ... -%}` and documented with `{# @prop ... #}`
- Each component has a `data-slot` attribute

## Local development with ux.symfony.com

The kit is mounted via a symlink in the site's vendor directory:

```bash
vendor/symfony/ux-toolkit/kits/catalyst → /path/to/symfony-ux-toolkit-catalyst
```

The files in `ux.symfony.com/` must be copied into the site project for the integration to work.
