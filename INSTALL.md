# Getting started

This kit provides ready-to-use and fully-customizable UI Twig components based on [Catalyst](https://catalyst.tailwindui.com/) components's **design**, a modern application UI kit by the Tailwind CSS team.

Please note that not every Catalyst component is available in this kit, but we are working on it!

## Requirements

This kit requires TailwindCSS to work:

- If you use Symfony AssetMapper, you can install TailwindCSS with the [TailwindBundle](https://symfony.com/bundles/TailwindBundle/current/index.html),
- If you use Webpack Encore, you can follow the [TailwindCSS installation guide for Symfony](https://tailwindcss.com/docs/installation/framework-guides/symfony)

## Installation

1. Install the Inter font family. [Download Inter](https://rsms.me/inter/download/), then put the `Inter-Regular.woff2`, `Inter-Medium.woff2` and `Inter-SemiBold.woff2` files from its `web` folder in the `assets/fonts/` directory of your project:

```text
assets/
├── fonts/
│   ├── Inter-Medium.woff2
│   ├── Inter-Regular.woff2
│   └── Inter-SemiBold.woff2
└── styles/
    ├── app.css
    └── fonts.css
```

Then create the file `assets/styles/fonts.css` with the following content:

```css
@font-face {
    font-family: Inter;
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: url("../fonts/Inter-Regular.woff2") format("woff2");
}

@font-face {
    font-family: Inter;
    font-style: normal;
    font-weight: 500;
    font-display: swap;
    src: url("../fonts/Inter-Medium.woff2") format("woff2");
}

@font-face {
    font-family: Inter;
    font-style: normal;
    font-weight: 600;
    font-display: swap;
    src: url("../fonts/Inter-SemiBold.woff2") format("woff2");
}
```

2. Modify the file `assets/styles/app.css` with the following content:

```css
@import "tailwindcss";
@import "./fonts.css";

@custom-variant dark (&:where(.dark, .dark *));

@theme {
    --font-sans: Inter, sans-serif;
    --font-sans--font-feature-settings: "cv11";
}
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
