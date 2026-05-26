# Select

Not a component I'd recommend using for a password field.

```twig {"preview":true}
<div class="w-full max-w-sm" style="min-height: 175px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Select name="status">
            <option value="active">Active</option>
            <option value="paused">Paused</option>
            <option value="delayed">Delayed</option>
            <option value="canceled">Canceled</option>
        </twig:Select>
    </twig:Fieldset:Field>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Select` component on its own to render a standalone select without an associated `Fieldset:Label` component:

```twig {"preview":true}
<div class="w-full max-w-sm" style="min-height: 150px">
    <twig:Select aria-label="Project status" name="status">
        <option value="active">Active</option>
        <option value="paused">Paused</option>
        <option value="delayed">Delayed</option>
        <option value="canceled">Canceled</option>
    </twig:Select>
</div>
```

Make sure to provide an `aria-label` for assistive technology, or connect the `Select` to your own `<label>` element using an `id`.

### With label

Wrap a `Fieldset:Label` and `Select` with the `Fieldset:Field` component to automatically associate them:

```twig {"preview":true}
<div class="w-full max-w-sm" style="min-height: 175px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Select name="status">
            <option value="active">Active</option>
            <option value="paused">Paused</option>
            <option value="delayed">Delayed</option>
            <option value="canceled">Canceled</option>
        </twig:Select>
    </twig:Fieldset:Field>
</div>
```

### With description

Use the `Fieldset:Description` component to add a description above or below your `Select`:

```twig {"preview":true}
<div class="w-full max-w-sm" style="min-height: 200px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Fieldset:Description>This will be visible to clients on the project.</twig:Fieldset:Description>
        <twig:Select name="status">
            <option value="active">Active</option>
            <option value="paused">Paused</option>
            <option value="delayed">Delayed</option>
            <option value="canceled">Canceled</option>
        </twig:Select>
    </twig:Fieldset:Field>
</div>
```

### Disabled state

Add the `disabled` prop to the `Fieldset:Field` component to disable a `Select` and the associated `Fieldset:Label`:

```twig {"preview":true}
<div class="w-full max-w-sm" style="min-height: 175px">
    <twig:Fieldset:Field disabled>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Select name="status">
            <option value="active">Active</option>
            <option value="paused">Paused</option>
            <option value="delayed">Delayed</option>
            <option value="canceled">Canceled</option>
        </twig:Select>
    </twig:Fieldset:Field>
</div>
```

You can also disable a select outside of a `Fieldset:Field` by adding the `disabled` prop directly to the `Select` itself.

### Validation errors

Add the `invalid` prop to the `Select` component to indicate a validation error, and render the error using the `Fieldset:ErrorMessage` component:

```twig {"preview":true}
<div class="w-full max-w-sm" style="min-height: 200px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Select name="status" invalid>
            <option value="" disabled selected>
                Select a status&hellip;
            </option>
            <option value="active">Active</option>
            <option value="paused">Paused</option>
            <option value="delayed">Delayed</option>
            <option value="canceled">Canceled</option>
        </twig:Select>
        <twig:Fieldset:ErrorMessage>A project status is required.</twig:Fieldset:ErrorMessage>
    </twig:Fieldset:Field>
</div>
```

### Constraining width

Use the `class` attribute on the `Select` component to make layout adjustments like adjusting the max-width:

```twig {"preview":true}
<div class="flex w-full max-w-sm justify-center" style="min-height: 250px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Day of the week</twig:Fieldset:Label>
        <twig:Select class="max-w-40" name="day_of_the_week">
            <option>Monday</option>
            <option>Tuesday</option>
            <option>Wednesday</option>
            <option>Thursday</option>
            <option>Friday</option>
            <option>Saturday</option>
            <option>Sunday</option>
        </twig:Select>
    </twig:Fieldset:Field>
</div>
```

## API Reference

::: api-reference
