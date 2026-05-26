# Text

For all the lorem ipsum in your Figma designs that you're definitely going to replace with real copy before launch.

```twig {"preview":true}
<div class="w-full max-w-md">
    <twig:Text>
        This feature is only available to users on the <twig:Strong>Business Plan</twig:Strong>. To upgrade, visit your
        <twig:Text:Link href="#">billing settings</twig:Text:Link>.
    </twig:Text>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Text` component for any custom paragraph text that should match the style of the text built in to your other components:

```twig {"preview":true}
<div class="w-full max-w-md">
    <twig:Text>Deleting your account is permanent, and your data will not be able to be recovered.</twig:Text>
</div>
```

Paragraphs using `Text` are responsive and automatically adapt to dark mode.

### With link

Use the `Text:Link` component for any links within a `Text` component:

```twig {"preview":true}
<div class="w-full max-w-md">
    <twig:Text>
        Deleting your account is permanent, and your data will not be able to be recovered. If you still want to use this
        account in the future, learn about <twig:Text:Link href="#">pausing your subscription</twig:Text:Link> instead.
    </twig:Text>
</div>
```

### With strong

Use the `Strong` component for any text you want to emphasize within a `Text` component:

```twig {"preview":true}
<div class="w-full max-w-md">
    <twig:Text>
        Deleting your account is permanent, and <twig:Strong>your account data cannot be recovered</twig:Strong>.
    </twig:Text>
</div>
```

### With code

Use the `Code` component for any inline code symbols within a `Text` component:

```twig {"preview":true}
<div class="w-full max-w-md">
    <twig:Text>
        Your new API token is <twig:Code>BaVrRKpRMS_ndKU</twig:Code>. Store this token somewhere safe as it will only be displayed
        once.
    </twig:Text>
</div>
```

## API Reference

::: api-reference
