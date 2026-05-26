# Getting started

This kit provides ready-to-use and fully-customizable UI Twig components based on [Catalyst](https://catalyst.tailwindui.com/) components's **design**, a modern application UI kit by the Tailwind CSS team.

Please note that not every Catalyst component is available in this kit, but we are working on it!

## Requirements

This kit requires TailwindCSS to work:

- If you use Symfony AssetMapper, you can install TailwindCSS with the [TailwindBundle](https://symfony.com/bundles/TailwindBundle/current/index.html),
- If you use Webpack Encore, you can follow the [TailwindCSS installation guide for Symfony](https://tailwindcss.com/docs/installation/framework-guides/symfony)

## Installation

1. Modify the file `assets/styles/app.css` with the following content:

```css
@import 'tailwindcss';

@theme {
    --font-sans: Inter, sans-serif;
    --font-sans--font-feature-settings: 'cv11';
}
```

2. Install the Inter font family, either with `importmap:require` for AssetMapper, or `npm` for Webpack Encore:

```bash
# With AssetMapper
php bin/console importmap:require @fontsource/inter/latin.css @fontsource/inter/latin-italic.css

# With npm
npm install @fontsource/inter
```

Then import the font in your JavaScript entrypoint (e.g. `assets/app.js`):

```js
import '@fontsource/inter/latin.css';
import '@fontsource/inter/latin-italic.css';
```

3. Configure the `heroicons` icon set to automatically add the `data-slot="icon"` attribute:

```yaml
# config/packages/ux_icons.yaml
ux_icons:
    icon_sets:
        heroicons:
            icon_attributes:
                data-slot: 'icon'
```

4. And that's it! You can now use the Catalyst Twig components in your templates!
