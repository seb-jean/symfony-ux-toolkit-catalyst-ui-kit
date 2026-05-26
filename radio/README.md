# Radio

With multiple choice, you've always got a chance at getting the right answer.

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Resale and transfers</twig:Fieldset:Legend>
        <twig:Text>Decide if people buy tickets from you or from scalpers.</twig:Text>
        <twig:Radio:Group>
            <twig:Radio:Field>
                <twig:Radio id="permit" name="resale" value="permit" checked />
                <twig:Fieldset:Label for="permit">Allow tickets to be resold</twig:Fieldset:Label>
                <twig:Fieldset:Description>Customers can resell or transfer their tickets if they can't make it to the event.</twig:Fieldset:Description>
            </twig:Radio:Field>
            <twig:Radio:Field>
                <twig:Radio id="forbid" name="resale" value="forbid" />
                <twig:Fieldset:Label for="forbid">Don't allow tickets to be resold</twig:Fieldset:Label>
                <twig:Fieldset:Description>Tickets cannot be resold or transferred to another person.</twig:Fieldset:Description>
            </twig:Radio:Field>
        </twig:Radio:Group>
    </twig:Fieldset>
</form>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Radio:Group`, `Radio:Field`, `Radio`, and `Fieldset:Label` components to create a simple radio group:

```twig {"preview":true}
<form>
    <twig:Radio:Group aria-label="Resale and transfers">
        <twig:Radio:Field>
            <twig:Radio id="permit" name="resale" value="permit" checked />
            <twig:Fieldset:Label for="permit">Allow tickets to be resold</twig:Fieldset:Label>
        </twig:Radio:Field>
        <twig:Radio:Field>
            <twig:Radio id="forbid" name="resale" value="forbid" />
            <twig:Fieldset:Label for="forbid">Don't allow tickets to be resold</twig:Fieldset:Label>
        </twig:Radio:Field>
    </twig:Radio:Group>
</form>
```

We recommend adding an `aria-label` for assistive technology, or connecting the `Radio:Group` to your own label using `aria-labelledby`.

### With description

Use the `Radio:Field`, `Fieldset:Label`, and `Fieldset:Description` components to add a description below the radio:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Radio:Group aria-label="Resale and transfers">
        <twig:Radio:Field>
            <twig:Radio id="permit" name="resale" value="permit" checked />
            <twig:Fieldset:Label for="permit">Allow tickets to be resold</twig:Fieldset:Label>
            <twig:Fieldset:Description>Customers can resell or transfer their tickets if they can't make it to the event.</twig:Fieldset:Description>
        </twig:Radio:Field>
        <twig:Radio:Field>
            <twig:Radio id="forbid" name="resale" value="forbid" />
            <twig:Fieldset:Label for="forbid">Don't allow tickets to be resold</twig:Fieldset:Label>
            <twig:Fieldset:Description>Tickets cannot be resold or transferred to another person.</twig:Fieldset:Description>
        </twig:Radio:Field>
    </twig:Radio:Group>
</form>
```

### With accent color

Use the `color` prop to choose a different accent color for a radio:

```twig {"preview":true}
<form>
    <twig:Radio:Group aria-label="Resale and transfers">
        <twig:Radio:Field>
            <twig:Radio id="permit" name="resale" value="permit" color="sky" checked />
            <twig:Fieldset:Label for="permit">Allow tickets to be resold</twig:Fieldset:Label>
        </twig:Radio:Field>
        <twig:Radio:Field>
            <twig:Radio id="forbid" name="resale" value="forbid" color="sky" />
            <twig:Fieldset:Label for="forbid">Don't allow tickets to be resold</twig:Fieldset:Label>
        </twig:Radio:Field>
    </twig:Radio:Group>
</form>
```

### Default selected state

Use the `checked` prop to set the default selected radio:

```twig {"preview":true}
<form>
    <twig:Radio:Group aria-label="Resale and transfers">
        <twig:Radio:Field>
            <twig:Radio id="permit" name="resale" value="permit" checked />
            <twig:Fieldset:Label for="permit">Allow tickets to be resold</twig:Fieldset:Label>
        </twig:Radio:Field>
        <twig:Radio:Field>
            <twig:Radio id="forbid" name="resale" value="forbid" />
            <twig:Fieldset:Label for="forbid">Don't allow tickets to be resold</twig:Fieldset:Label>
        </twig:Radio:Field>
    </twig:Radio:Group>
</form>
```

### With fieldset

Use the `Fieldset`, `Fieldset:Legend`, and `Text` components to add a title and description to a radio group:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Resale and transfers</twig:Fieldset:Legend>
        <twig:Text>Decide if people buy tickets from you or from scalpers.</twig:Text>
        <twig:Radio:Group>
            <twig:Radio:Field>
                <twig:Radio id="permit" name="resale" value="permit" checked />
                <twig:Fieldset:Label for="permit">Allow tickets to be resold</twig:Fieldset:Label>
                <twig:Fieldset:Description>Customers can resell or transfer their tickets if they can't make it to the event.</twig:Fieldset:Description>
            </twig:Radio:Field>
            <twig:Radio:Field>
                <twig:Radio id="forbid" name="resale" value="forbid" />
                <twig:Fieldset:Label for="forbid">Don't allow tickets to be resold</twig:Fieldset:Label>
                <twig:Fieldset:Description>Tickets cannot be resold or transferred to another person.</twig:Fieldset:Description>
            </twig:Radio:Field>
        </twig:Radio:Group>
    </twig:Fieldset>
</form>
```

When used with a `Fieldset` and `Fieldset:Legend`, you don't need to add a separate `aria-label` to the `Radio:Group` itself.

### Disabled state

Add the `disabled` prop to a `Radio` or `Radio:Field` component to disable it:

```twig {"preview":true}
<form class="w-full max-w-sm">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Resale and transfers</twig:Fieldset:Legend>
        <twig:Text>Decide if people buy tickets from you or from scalpers.</twig:Text>
        <twig:Radio:Group>
            <twig:Radio:Field>
                <twig:Radio id="permit" name="resale" value="permit" checked />
                <twig:Fieldset:Label for="permit">Allow tickets to be resold</twig:Fieldset:Label>
                <twig:Fieldset:Description>Customers can resell or transfer their tickets if they can't make it to the event.</twig:Fieldset:Description>
            </twig:Radio:Field>
            <twig:Radio:Field disabled>
                <twig:Radio id="forbid" name="resale" value="forbid" />
                <twig:Fieldset:Label for="forbid">Don't allow tickets to be resold</twig:Fieldset:Label>
                <twig:Fieldset:Description>Tickets cannot be resold or transferred to another person.</twig:Fieldset:Description>
            </twig:Radio:Field>
        </twig:Radio:Group>
    </twig:Fieldset>
</form>
```

You can also add the `disabled` prop to a `Radio:Group` or `Fieldset` to disable all of the radio buttons in that group.

## API Reference

::: api-reference
