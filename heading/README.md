# Heading

You get two — we're building applications here, not authoring medical journals.

```twig {"preview":true}
<div class="flex w-full flex-wrap items-end justify-between gap-4 border-b border-zinc-950/10 pb-6 dark:border-white/10">
    <twig:Heading>Order #1011</twig:Heading>
    <div class="flex gap-4">
        <twig:Button outline>Refund</twig:Button>
        <twig:Button>Resend invoice</twig:Button>
    </div>
</div>
```

## Installation

::: installation

## Examples

### Basic heading example

Use the `Heading` component to add a primary heading to a page:

```twig {"preview":true}
<div class="w-full">
    <twig:Heading>Recent orders</twig:Heading>
</div>
```

The `Heading` component renders an `h1` by default, which you can customize with the `level` prop.

### Basic subheading example

Use the `Subheading` component to add a subheading to a page:

```twig {"preview":true}
<div class="w-full">
    <twig:Subheading>Recent orders</twig:Subheading>
</div>
```

The `Subheading` component renders an `h2` by default, which you can customize with the `level` prop.

### With custom level

Use the `level` prop to render a different heading element for semantic purposes while still maintaining the same visual styles:

```twig {"preview":true}
<div class="w-full">
    <twig:Heading level="2">Recent orders</twig:Heading>
</div>
```

## API Reference

::: api-reference
