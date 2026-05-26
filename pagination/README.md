# Pagination

Because if anyone actually uses this app you're working on, your data isn't going to fit on a single page for long.

```twig {"preview":true}
<div class="w-full">
    <twig:Pagination>
        <twig:Pagination:Previous href="?page=2" />
        <twig:Pagination:List>
            <twig:Pagination:Page href="?page=1">1</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=2">2</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=3" :current="true">3</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=4">4</twig:Pagination:Page>
            <twig:Pagination:Gap />
            <twig:Pagination:Page href="?page=65">65</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=66">66</twig:Pagination:Page>
        </twig:Pagination:List>
        <twig:Pagination:Next href="?page=4" />
    </twig:Pagination>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Pagination`, `Pagination:Previous`, `Pagination:List`, `Pagination:Page`, `Pagination:Gap`, and `Pagination:Next` components to create a set of pagination links:

```twig {"preview":true}
<div class="w-full">
    <twig:Pagination>
        <twig:Pagination:Previous href="?page=2" />
        <twig:Pagination:List>
            <twig:Pagination:Page href="?page=1">1</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=2">2</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=3" :current="true">3</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=4">4</twig:Pagination:Page>
            <twig:Pagination:Gap />
            <twig:Pagination:Page href="?page=65">65</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=66">66</twig:Pagination:Page>
        </twig:Pagination:List>
        <twig:Pagination:Next href="?page=4" />
    </twig:Pagination>
</div>
```

### Disabling previous/next links

Omit the `href` prop on the `Pagination:Previous` or `Pagination:Next` components to disable the previous/next links when on the first or last page:

```twig {"preview":true}
<div class="w-full">
    <twig:Pagination>
        <twig:Pagination:Previous />
        <twig:Pagination:List>
            <twig:Pagination:Page href="?page=1" :current="true">1</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=2">2</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=3">3</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=4">4</twig:Pagination:Page>
            <twig:Pagination:Gap />
            <twig:Pagination:Page href="?page=65">65</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=66">66</twig:Pagination:Page>
        </twig:Pagination:List>
        <twig:Pagination:Next href="?page=2" />
    </twig:Pagination>
</div>
```

### Current page active state

Use the `current` prop on the `Pagination:Page` component to indicate the current page:

```twig {"preview":true}
<div class="w-full">
    <twig:Pagination>
        <twig:Pagination:Previous href="?page=1" />
        <twig:Pagination:List>
            <twig:Pagination:Page href="?page=1">1</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=2" :current="true">2</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=3">3</twig:Pagination:Page>
        </twig:Pagination:List>
        <twig:Pagination:Next href="?page=3" />
    </twig:Pagination>
</div>
```

### Without page links

Omit the `Pagination:List` and `Pagination:Page` components to render just the previous and next links:

```twig {"preview":true}
<div class="w-full">
    <twig:Pagination>
        <twig:Pagination:Previous />
        <twig:Pagination:Next href="?page=2" />
    </twig:Pagination>
</div>
```

## API Reference

::: api-reference
