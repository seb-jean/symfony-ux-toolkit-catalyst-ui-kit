# Input

If web applications didn't need inputs, computers wouldn't have keyboards.

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="full_name">Full name</twig:Fieldset:Label>
        <twig:Input id="full_name" name="full_name" />
    </twig:Fieldset:Field>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Input` component on its own to render a standalone input without an associated `Fieldset:Label` component:

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Input aria-label="Full name" name="full_name" />
</div>
```

Make sure to provide an `aria-label` for assistive technology, or connect the `Input` to your own `<label>` element using an `id`.

### With label

Wrap a `Fieldset:Label` and `Input` with the `Fieldset:Field` component to automatically associate them:

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="full_name">Full name</twig:Fieldset:Label>
        <twig:Input id="full_name" name="full_name" />
    </twig:Fieldset:Field>
</div>
```

### With description

Use the `Fieldset:Description` component to add a description above or below your `Input`:

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="product_name">Product name</twig:Fieldset:Label>
        <twig:Fieldset:Description>Use the name you'd like people to see in their cart.</twig:Fieldset:Description>
        <twig:Input id="product_name" name="product_name" />
    </twig:Fieldset:Field>
</div>
```

### With icon

Wrap an icon and `Input` with the `Input:Group` component to render an input with an icon:

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Input:Group>
        <twig:ux:icon name="heroicons:magnifying-glass-16-solid" />
        <twig:Input name="search" placeholder="Search…" aria-label="Search" />
    </twig:Input:Group>
</div>
```

The `Input:Group` component is designed to work best with 16×16 icons.

If you're using your own custom icons, make sure they include the `data-slot="icon"` attribute so they receive the correct styles.

### Setting the type

Use the `type` prop to set the input type to any supported text input type:

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="url">Your website</twig:Fieldset:Label>
        <twig:Input id="url" type="url" name="url" />
    </twig:Fieldset:Field>
</div>
```

The supported types are `email`, `number`, `password`, `search`, `tel`, `text`, `url`, `date`, `datetime-local`, `month`, `time`, and `week`.

### Disabled state

Add the `disabled` prop to the `Fieldset:Field` component to disable an `Input` and the associated `Fieldset:Label`:

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Fieldset:Field disabled>
        <twig:Fieldset:Label for="full_name">Full name</twig:Fieldset:Label>
        <twig:Input id="full_name" name="full_name" disabled />
    </twig:Fieldset:Field>
</div>
```

You can also disable an input outside of a `Fieldset:Field` by adding the `disabled` attribute directly to the `Input` itself.

### Validation errors

Add the `invalid` prop to the `Input` component to indicate a validation error, and render the error using the `Fieldset:ErrorMessage` component:

```twig {"preview":true}
<div class="w-full max-w-sm">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="full_name">Full name</twig:Fieldset:Label>
        <twig:Input id="full_name" name="full_name" invalid />
        <twig:Fieldset:ErrorMessage>This field is required.</twig:Fieldset:ErrorMessage>
    </twig:Fieldset:Field>
</div>
```

### Constraining width

Use the `class` attribute on the `Input` component to make layout adjustments like adjusting the max-width:

```twig {"preview":true}
<div class="flex w-full max-w-sm justify-center">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="cvc">CVC</twig:Fieldset:Label>
        <twig:Input id="cvc" class="max-w-24" name="cvc" pattern="[0-9]*" />
    </twig:Fieldset:Field>
</div>
```

Be aware that the `class` attribute is a sharp knife — make sure to only add classes that don't conflict with classes the component already includes or you'll get unexpected results.

## API Reference

::: api-reference
