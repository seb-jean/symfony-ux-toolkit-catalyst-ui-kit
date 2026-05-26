# Button

You know, those things you click to do just about anything in a web application.

```twig {"preview":true}
<twig:Button>Save changes</twig:Button>
```

## Installation

::: installation

## Examples

### Button colors

Use the `color` prop to set the button color:

```twig {"preview":true}
<twig:Button color="cyan">Save changes</twig:Button>
```

### Outline buttons

Use the `outline` prop for a secondary button style with no shadows or background color:

```twig {"preview":true}
<twig:Button outline>Save draft</twig:Button>
```

### Plain buttons

Use the `plain` prop for a simple button style with no border, shadows or background color:

```twig {"preview":true}
<twig:Button plain>Save draft</twig:Button>
```

### Disabled states

Use the `disabled` prop to disable a button and apply disabled styles:

```twig {"preview":true}
<twig:Button disabled>Save changes</twig:Button>
```

The `disabled` prop is not supported when using the `href` prop.

### With icon

Icons may be place at the start or end of a button:

```twig {"preview":true}
<twig:Button>
    <twig:ux:icon name="heroicons:plus-16-solid" />
    Add item
</twig:Button>
```

The `Button` component is designed to work best with 16×16 icons.

If you're using your own custom icons, make sure they include the `data-slot="icon"` attribute so they receive the correct styles.

### Using as a link

Add the `href` prop to render a link that has the same visual styling as a button:

```twig {"preview":true}
<twig:Button href="/get-started">Get started</twig:Button>
```

Link buttons support all of the same props as regular buttons except `disabled`.

## API Reference

::: api-reference
