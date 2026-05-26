# Badge

Eventually this custom CMS you're probably building is going to need tags.

```twig {"preview":true}
<div class="flex gap-3">
    <twig:Badge color="lime">documentation</twig:Badge>
    <twig:Badge color="purple">help wanted</twig:Badge>
    <twig:Badge color="rose">bug</twig:Badge>
</div>
```

## Installation

::: installation

## Examples

### Badge colors

Use the `color` prop to set the color of the badge:

```twig {"preview":true}
<div class="flex gap-3">
    <twig:Badge color="lime">documentation</twig:Badge>
    <twig:Badge color="purple">help wanted</twig:Badge>
    <twig:Badge color="rose">bug</twig:Badge>
</div>
```

### Using as buttons

Use the `Badge:Button` component to render a badge as a button:

```twig {"preview":true}
<twig:Badge:Button>documentation</twig:Badge:Button>
```

### Using as links

Use the `Badge:Button` component with the `href` prop to render a badge as a link:

```twig {"preview":true}
<twig:Badge:Button href="#">documentation</twig:Badge:Button>
```

## API Reference

::: api-reference
