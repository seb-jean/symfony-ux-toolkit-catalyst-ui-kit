# Switch

It's basically just a fancy checkbox, let's not kid ourselves.

```twig {"preview":true}
<form>
    <twig:Switch:Field>
        <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
        <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
        <twig:Switch id="allow_embedding" name="allow_embedding" checked />
    </twig:Switch:Field>
</form>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Switch` component on its own to render a standalone switch without an associated `Fieldset:Label` component:

```twig {"preview":true}
<form>
    <twig:Switch aria-label="Allow embedding" name="allow_embedding" />
</form>
```

Make sure to provide an `aria-label` for assistive technology, or connect the `Switch` to your own `<label>` element using an `id`.

### With label

Wrap a `Fieldset:Label` and `Switch` with the `Switch:Field` component to automatically associate them:

```twig {"preview":true}
<form class="w-full max-w-64">
    <twig:Switch:Field>
        <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
        <twig:Switch id="allow_embedding" name="allow_embedding" />
    </twig:Switch:Field>
</form>
```

### With description

Use the `Switch:Field`, `Fieldset:Label`, and `Fieldset:Description` components to add a label and description to a switch:

```twig {"preview":true}
<form>
    <twig:Switch:Field>
        <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
        <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
        <twig:Switch id="allow_embedding" name="allow_embedding" />
    </twig:Switch:Field>
</form>
```

### With accent color

Use the `color` prop to choose a different accent color for a switch:

```twig {"preview":true}
<form>
    <twig:Switch name="accent_color" color="sky" checked />
</form>
```

### With custom value

Use the `value` attribute to specify a custom value to use when submitting a form:

```twig {"preview":true}
<form>
    <twig:Switch name="embed" value="allow" />
</form>
```

### Default checked state

Use the `checked` prop to set the default state of the switch:

```twig {"preview":true}
<form>
    <twig:Switch name="default_checked" checked />
</form>
```

### Multiple switches

Use the `Switch:Group` component to stack multiple switches together in a list:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Switch:Group>
        <twig:Switch:Field>
            <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
            <twig:Fieldset:Description>Make this event visible on your profile.</twig:Fieldset:Description>
            <twig:Switch id="show_on_events_page" name="discoverability" checked />
        </twig:Switch:Field>
        <twig:Switch:Field>
            <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
            <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
            <twig:Switch id="allow_embedding" name="discoverability" />
        </twig:Switch:Field>
    </twig:Switch:Group>
</form>
```

You can optionally add `role="group"` and an `aria-label` to the `Switch:Group` if all of the switches are related and you want them announced to assistive technology as a group.

### With fieldset

Use the `Fieldset`, `Fieldset:Legend`, and `Text` components to add a title and description to a group of switches:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Discoverability</twig:Fieldset:Legend>
        <twig:Text>Decide where your events can be found across the web.</twig:Text>
        <twig:Switch:Group>
            <twig:Switch:Field>
                <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
                <twig:Fieldset:Description>Make this event visible on your profile.</twig:Fieldset:Description>
                <twig:Switch id="show_on_events_page" name="discoverability" checked />
            </twig:Switch:Field>
            <twig:Switch:Field>
                <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
                <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
                <twig:Switch id="allow_embedding" name="discoverability" />
            </twig:Switch:Field>
        </twig:Switch:Group>
    </twig:Fieldset>
</form>
```

### Disabled state

Add the `disabled` prop to a `Switch` or `Switch:Field` component to disable it:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Discoverability</twig:Fieldset:Legend>
        <twig:Text>Decide where your events can be found across the web.</twig:Text>
        <twig:Switch:Group>
            <twig:Switch:Field>
                <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
                <twig:Fieldset:Description>Make this event visible on your profile.</twig:Fieldset:Description>
                <twig:Switch id="show_on_events_page" name="discoverability" value="show_on_events_page" />
            </twig:Switch:Field>
            <twig:Switch:Field disabled>
                <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
                <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
                <twig:Switch id="allow_embedding" name="discoverability" value="allow_embedding" />
            </twig:Switch:Field>
        </twig:Switch:Group>
    </twig:Fieldset>
</form>
```

You can also add the `disabled` prop to a `Fieldset` to disable the entire fieldset.

## API Reference

::: api-reference
