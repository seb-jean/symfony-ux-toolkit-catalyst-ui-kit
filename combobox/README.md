# Combobox

For when you know exactly what you want, but are too lazy to scroll for it.

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander'},
    {name: 'Michael Foster'},
    {name: 'Dries Vincent'},
    {name: 'Bonnie Green'},
    {name: 'Courtney Henry'},
] -%}
<div class="w-full max-w-56" style="min-height: 275px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Combobox id="user" name="user" value="Michael Foster">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Combobox`, `Combobox:Option`, and `Combobox:Label` components to build a basic combobox:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander'},
    {name: 'Michael Foster'},
    {name: 'Dries Vincent'},
    {name: 'Bonnie Green'},
    {name: 'Courtney Henry'},
] -%}
<div class="w-full max-w-56" style="min-height: 225px">
    <twig:Combobox name="user" ariaLabel="Assigned to" value="Michael Foster">
        {%- for user in users -%}
            <twig:Combobox:Option value="{{ user.name }}">
                <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
            </twig:Combobox:Option>
        {%- endfor -%}
    </twig:Combobox>
</div>
```

Make sure to provide an `aria-label` for assistive technology, or connect the `Combobox` to your own `<label>` element using an `id`.

### With label

Wrap a `Fieldset:Label` and `Combobox` with the `Fieldset:Field` component to automatically associate them:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander'},
    {name: 'Michael Foster'},
    {name: 'Dries Vincent'},
    {name: 'Bonnie Green'},
    {name: 'Courtney Henry'},
] -%}
<div class="w-full max-w-56" style="min-height: 275px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Combobox id="user" name="user" value="Michael Foster">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

### With description

Use the `Fieldset:Description` component to add a description above or below your `Combobox`:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander'},
    {name: 'Michael Foster'},
    {name: 'Dries Vincent'},
    {name: 'Bonnie Green'},
    {name: 'Courtney Henry'},
] -%}
<div class="w-full max-w-xs" style="min-height: 300px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Fieldset:Description>This user will have full access to the project.</twig:Fieldset:Description>
        <twig:Combobox id="user" name="user" value="Michael Foster">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

### With placeholder

Use the `placeholder` prop to add a placeholder to your `Combobox` when no value is selected:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander'},
    {name: 'Michael Foster'},
    {name: 'Dries Vincent'},
    {name: 'Bonnie Green'},
    {name: 'Courtney Henry'},
] -%}
<div class="w-full max-w-56" style="min-height: 275px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Combobox id="user" name="user" placeholder="Select user…">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

### With avatars

Add an `Avatar` to a `Combobox:Option` by inserting it before your `Combobox:Label`:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', initials: 'la', avatarUrl: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Michael Foster', initials: 'mf', avatarUrl: 'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Dries Vincent', initials: 'dv', avatarUrl: 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Tom Cook', initials: 'tc', avatarUrl: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Courtney Henry', initials: 'ch', avatarUrl: 'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
] -%}
<div class="w-full max-w-56" style="min-height: 275px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Combobox id="user" name="user" value="Tom Cook">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Avatar src="{{ user.avatarUrl }}" initials="{{ user.initials }}" class="bg-purple-500 text-white" alt="" />
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

### With flags

Add a flag icon to a `Combobox:Option` by inserting it before your `Combobox:Label`:

```twig {"preview":true}
{%- set countries = [
    {name: 'Canada', flag: 'flagpack:ca'},
    {name: 'United States', flag: 'flagpack:us'},
    {name: 'Mexico', flag: 'flagpack:mx'},
] -%}
<div class="w-full max-w-56" style="min-height: 200px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="country">Country</twig:Fieldset:Label>
        <twig:Combobox id="country" name="country" value="Canada">
            {%- for country in countries -%}
                <twig:Combobox:Option value="{{ country.name }}">
                    <twig:ux:icon name="{{ country.flag }}" class="w-5 sm:w-4" />
                    <twig:Combobox:Label>{{ country.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

We like the 16×12 flag icons from [Flagpack](https://flagpack.xyz/), a great set of open-source flag icons.

### With secondary text

Use the `Combobox:Description` component to add secondary text to a combobox option:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', role: 'Co-Founder / CEO'},
    {name: 'Michael Foster', role: 'Co-Founder / CTO'},
    {name: 'Dries Vincent', role: 'Business Relations'},
    {name: 'Tom Cook', role: 'Director of Product'},
    {name: 'Courtney Henry', role: 'Designer'},
] -%}
<div class="w-full max-w-xs" style="min-height: 275px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Combobox id="user" name="user" value="Tom Cook">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                    <twig:Combobox:Description>{{ user.role }}</twig:Combobox:Description>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

### Disabled state

Add the `disabled` prop to the `Fieldset:Field` component to disable a `Combobox` and the associated `Fieldset:Label`:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander'},
    {name: 'Michael Foster'},
    {name: 'Dries Vincent'},
    {name: 'Bonnie Green'},
    {name: 'Courtney Henry'},
] -%}
<div class="w-full max-w-56" style="min-height: 275px">
    <twig:Fieldset:Field disabled>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Combobox id="user" name="user" value="Michael Foster">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

You can also disable a combobox outside of a `Fieldset:Field` by adding the `disabled` prop directly to the `Combobox` itself.

### Validation errors

Add the `invalid` prop to the `Combobox` component to indicate a validation error, and render the error using the `Fieldset:ErrorMessage` component:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander'},
    {name: 'Michael Foster'},
    {name: 'Dries Vincent'},
    {name: 'Bonnie Green'},
    {name: 'Courtney Henry'},
] -%}
<div class="w-full max-w-56" style="min-height: 275px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="user">Assigned to</twig:Fieldset:Label>
        <twig:Combobox id="user" invalid name="user" placeholder="Select user…">
            {%- for user in users -%}
                <twig:Combobox:Option value="{{ user.name }}">
                    <twig:Combobox:Label>{{ user.name }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
        <twig:Fieldset:ErrorMessage>A user is required.</twig:Fieldset:ErrorMessage>
    </twig:Fieldset:Field>
</div>
```

### Constraining width

Use the `class` attribute on the `Combobox` component to make layout adjustments like adjusting the max-width:

```twig {"preview":true}
{%- set currencies = [
    {code: 'CAD'},
    {code: 'USD'},
    {code: 'EUR'},
    {code: 'GBP'},
] -%}
<div class="w-full max-w-40" style="min-height: 250px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label for="currency">Currency</twig:Fieldset:Label>
        <twig:Combobox id="currency" class="max-w-40" name="currency" value="CAD">
            {%- for currency in currencies -%}
                <twig:Combobox:Option value="{{ currency.code }}">
                    <twig:Combobox:Label>{{ currency.code }}</twig:Combobox:Label>
                </twig:Combobox:Option>
            {%- endfor -%}
        </twig:Combobox>
    </twig:Fieldset:Field>
</div>
```

Be aware that the `class` attribute is a sharp knife — make sure to only add classes that don't conflict with classes the component already includes or you'll get unexpected results.

## API Reference

::: api-reference
