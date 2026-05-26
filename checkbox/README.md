# Checkbox

People need to be able to accept the terms and conditions they don't read somehow.

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Discoverability</twig:Fieldset:Legend>
        <twig:Text>Decide where your events can be found across the web.</twig:Text>
        <twig:Checkbox:Group>
            <twig:Checkbox:Field>
                <twig:Checkbox id="show_on_events_page" name="discoverability" value="show_on_events_page" checked />
                <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
                <twig:Fieldset:Description>Make this event visible on your profile.</twig:Fieldset:Description>
            </twig:Checkbox:Field>
            <twig:Checkbox:Field>
                <twig:Checkbox id="allow_embedding" name="discoverability" value="allow_embedding" />
                <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
                <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
            </twig:Checkbox:Field>
        </twig:Checkbox:Group>
    </twig:Fieldset>
</form>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Checkbox` component on its own to render a standalone checkbox without an associated `Fieldset:Label` component:

```twig {"preview":true}
<form>
    <twig:Checkbox aria-label="Allow embedding" name="allow_embedding" />
</form>
```

Make sure to provide an `aria-label` for assistive technology, or connect the `Checkbox` to your own `<label>` element using an `id`.

### With label

Wrap a `Fieldset:Label` and `Checkbox` with the `Checkbox:Field` component to automatically associate them:

```twig {"preview":true}
<form>
    <twig:Checkbox:Field>
        <twig:Checkbox id="allow_embedding" name="allow_embedding" />
        <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
    </twig:Checkbox:Field>
</form>
```

### With description

Use the `Checkbox:Field`, `Fieldset:Label`, and `Fieldset:Description` components to add a description below the checkbox:

```twig {"preview":true}
<form>
    <twig:Checkbox:Field>
        <twig:Checkbox id="allow_embedding" name="allow_embedding" />
        <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
        <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
    </twig:Checkbox:Field>
</form>
```

### With accent color

Use the `color` prop to choose a different accent color for a checkbox:

```twig {"preview":true}
<form>
    <twig:Checkbox name="accent_color" color="sky" checked />
</form>
```

### With custom value

Use the `value` attribute to specify a custom value to use when submitting a form:

```twig {"preview":true}
<form>
    <twig:Checkbox name="embed" value="allow" />
</form>
```

### Default checked state

Use the `checked` prop to set the default state of the checkbox:

```twig {"preview":true}
<form>
    <twig:Checkbox name="default_checked" checked />
</form>
```

### Indeterminate state

Use the `indeterminate` prop to indicate that the `Checkbox` is in an indeterminate state, neither toggled on nor off:

```twig {"preview":true}
<twig:Checkbox:Group role="group" aria-label="Discoverability">
    <twig:Checkbox:Field>
        <twig:Checkbox id="select_all" name="select_all" />
        <twig:Fieldset:Label for="select_all">Select all</twig:Fieldset:Label>
    </twig:Checkbox:Field>
    <twig:Checkbox:Field>
        <twig:Checkbox id="show_on_events_page" name="show_on_events_page" checked />
        <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
    </twig:Checkbox:Field>
    <twig:Checkbox:Field>
        <twig:Checkbox id="allow_embedding" name="allow_embedding" />
        <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
    </twig:Checkbox:Field>
</twig:Checkbox:Group>

<script>
    const options = ['show_on_events_page', 'allow_embedding'];
    let selected = ['show_on_events_page'];

    function render() {
        const selectAll = document.getElementById('select_all');
        selectAll.checked = selected.length > 0;
        selectAll.indeterminate = selected.length > 0 && selected.length < options.length;

        options.forEach((option) => {
            document.getElementById(option).checked = selected.includes(option);
        });
    }

    document.getElementById('select_all').addEventListener('change', (e) => {
        selected = e.target.checked ? [...options] : [];
        render();
    });

    options.forEach((option) => {
        document.getElementById(option).addEventListener('change', (e) => {
            selected = e.target.checked
                ? [...selected, option]
                : selected.filter((item) => item !== option);
            render();
        });
    });

    render();
</script>
```

### Multiple checkboxes

Use the `Checkbox:Group` component to stack multiple checkboxes together in a list:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Checkbox:Group>
        <twig:Checkbox:Field>
            <twig:Checkbox id="show_on_events_page" name="discoverability" checked />
            <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
            <twig:Fieldset:Description>Make this event visible on your profile.</twig:Fieldset:Description>
        </twig:Checkbox:Field>
        <twig:Checkbox:Field>
            <twig:Checkbox id="allow_embedding" name="discoverability" />
            <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
            <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
        </twig:Checkbox:Field>
    </twig:Checkbox:Group>
</form>
```

You can optionally add `role="group"` and an `aria-label` to the `Checkbox:Group` if all of the checkboxes are related and you want them announced to assistive technology as a group.

### With fieldset

Use the `Fieldset`, `Fieldset:Legend`, and `Text` components to add a title and description to a group of checkboxes:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Discoverability</twig:Fieldset:Legend>
        <twig:Text>Decide where your events can be found across the web.</twig:Text>
        <twig:Checkbox:Group>
            <twig:Checkbox:Field>
                <twig:Checkbox id="show_on_events_page" name="discoverability" value="show_on_events_page" checked />
                <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
                <twig:Fieldset:Description>Make this event visible on your profile.</twig:Fieldset:Description>
            </twig:Checkbox:Field>
            <twig:Checkbox:Field>
                <twig:Checkbox id="allow_embedding" name="discoverability" value="allow_embedding" />
                <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
                <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
            </twig:Checkbox:Field>
        </twig:Checkbox:Group>
    </twig:Fieldset>
</form>
```

### Disabled state

Add the `disabled` prop to a `Checkbox` or `Checkbox:Field` component to disable it:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Discoverability</twig:Fieldset:Legend>
        <twig:Text>Decide where your events can be found across the web.</twig:Text>
        <twig:Checkbox:Group>
            <twig:Checkbox:Field>
                <twig:Checkbox id="show_on_events_page" name="discoverability" value="show_on_events_page" />
                <twig:Fieldset:Label for="show_on_events_page">Show on events page</twig:Fieldset:Label>
                <twig:Fieldset:Description>Make this event visible on your profile.</twig:Fieldset:Description>
            </twig:Checkbox:Field>
            <twig:Checkbox:Field disabled>
                <twig:Checkbox id="allow_embedding" name="discoverability" value="allow_embedding" />
                <twig:Fieldset:Label for="allow_embedding">Allow embedding</twig:Fieldset:Label>
                <twig:Fieldset:Description>Allow others to embed your event details on their own site.</twig:Fieldset:Description>
            </twig:Checkbox:Field>
        </twig:Checkbox:Group>
    </twig:Fieldset>
</form>
```

You can also add the `disabled` prop to a `Fieldset` to disable the entire fieldset.

## Appendix

### Color reference

By default, Catalyst includes two adaptive color variants that automatically change color between light and dark modes to maintain a consistent level of contrast:

```twig {"preview":true}
{%- set colors = ['dark/zinc', 'dark/white'] -%}
<div class="-mt-4 w-full">
    <twig:Table class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row class="text-zinc-950 dark:text-white">
                <twig:Table:Header align="left" class="w-1/3">Color</twig:Table:Header>
                <twig:Table:Header align="center" class="w-2/3">Example</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for color in colors -%}
                <twig:Table:Row>
                    <twig:Table:Cell align="left" class="w-1/3">`{{ color }}`</twig:Table:Cell>
                    <twig:Table:Cell align="center" class="w-2/3">
                        <div class="justify-center flex">
                            <twig:Checkbox color="{{ color }}" name="{{ color }}" checked />
                        </div>
                    </twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

Catalyst also includes 20 solid colors that don't change outside of subtle global changes we make to all checkboxes in dark mode:

```twig {"preview":true}
{%- set colors = [
    'dark',
    'zinc',
    'white',
    'red',
    'orange',
    'amber',
    'yellow',
    'lime',
    'green',
    'emerald',
    'teal',
    'cyan',
    'sky',
    'blue',
    'indigo',
    'violet',
    'purple',
    'fuchsia',
    'pink',
    'rose',
] -%}
<div class="-mt-4 w-full">
    <twig:Table class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row class="text-zinc-950 dark:text-white">
                <twig:Table:Header align="left" class="w-1/3">Color</twig:Table:Header>
                <twig:Table:Header align="center" class="w-2/3">Example</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for color in colors -%}
                <twig:Table:Row>
                    <twig:Table:Cell align="left" class="w-1/3">`{{ color }}`</twig:Table:Cell>
                    <twig:Table:Cell align="center" class="w-2/3">
                        <div class="justify-center flex">
                            <twig:Checkbox color="{{ color }}" name="{{ color }}" checked />
                        </div>
                    </twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

## API Reference

::: api-reference
