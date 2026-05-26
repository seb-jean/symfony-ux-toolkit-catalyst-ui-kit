# Textarea

For the times when you really just have a lot to say.

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="description">Description</twig:Fieldset:Label>
        <twig:Textarea id="description" name="description" />
    </twig:Fieldset:Field>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Textarea` component on its own to render a standalone textarea without an associated `Fieldset:Label` component:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Textarea aria-label="Description" name="description" />
</div>
```

Make sure to provide an `aria-label` for assistive technology, or connect the `Textarea` to your own `<label>` element using an `id`.

### With label

Wrap a `Fieldset:Label` and `Textarea` with the `Fieldset:Field` component to automatically associate them:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="description">Description</twig:Fieldset:Label>
        <twig:Textarea id="description" name="description" />
    </twig:Fieldset:Field>
</div>
```

### With description

Use the `Fieldset:Description` component to add a description above or below your `Textarea`:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="description">Description</twig:Fieldset:Label>
        <twig:Fieldset:Description>This will be shown under the product title.</twig:Fieldset:Description>
        <twig:Textarea id="description" name="description" />
    </twig:Fieldset:Field>
</div>
```

### Disabled state

Add the `disabled` prop to the `Fieldset:Field` component to disable the `Textarea` and the associated `Fieldset:Label`:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset:Field disabled>
        <twig:Fieldset:Label for="description">Description</twig:Fieldset:Label>
        <twig:Textarea id="description" name="description" />
    </twig:Fieldset:Field>
</div>
```

You can also disable a textarea outside of a `Fieldset:Field` by adding the `disabled` prop directly to the `Textarea` itself.

### Validation errors

Add the `invalid` prop to the `Fieldset:Field` component to indicate a validation error, and render the error using the `Fieldset:ErrorMessage` component:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="description">Description</twig:Fieldset:Label>
        <twig:Textarea id="description" name="description" invalid />
        <twig:Fieldset:ErrorMessage>This field is required.</twig:Fieldset:ErrorMessage>
    </twig:Fieldset:Field>
</div>
```

## API Reference

::: api-reference
