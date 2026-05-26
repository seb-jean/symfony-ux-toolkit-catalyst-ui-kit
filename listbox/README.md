# Listbox

A painstakingly re-engineered select menu, just so you can put a flag in it or have a placeholder.

```twig {"preview":true}
<div class="w-full max-w-56" style="min-height: 240px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Listbox name="status" defaultValue="active">
            <twig:Listbox:Option value="active">
                <twig:Listbox:Label>Active</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="paused">
                <twig:Listbox:Label>Paused</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="delayed">
                <twig:Listbox:Label>Delayed</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="canceled">
                <twig:Listbox:Label>Canceled</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Listbox`, `Listbox:Option`, and `Listbox:Label` components to build a basic listbox:

```twig {"preview":true}
<div class="w-full max-w-56" style="min-height: 200px">
    <twig:Listbox name="status" defaultValue="active" aria-label="Project status">
        <twig:Listbox:Option value="active">
            <twig:Listbox:Label>Active</twig:Listbox:Label>
        </twig:Listbox:Option>
        <twig:Listbox:Option value="paused">
            <twig:Listbox:Label>Paused</twig:Listbox:Label>
        </twig:Listbox:Option>
        <twig:Listbox:Option value="delayed">
            <twig:Listbox:Label>Delayed</twig:Listbox:Label>
        </twig:Listbox:Option>
        <twig:Listbox:Option value="canceled">
            <twig:Listbox:Label>Canceled</twig:Listbox:Label>
        </twig:Listbox:Option>
    </twig:Listbox>
</div>
```

Make sure to provide an `aria-label` for assistive technology, or connect the `Listbox` to your own `<label>` element using an `id`.

### With label

Wrap a `Fieldset:Label` and `Listbox` with the `Fieldset:Field` component to automatically associate them:

```twig {"preview":true}
<div class="w-full max-w-56" style="min-height: 240px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Listbox name="status" defaultValue="active">
            <twig:Listbox:Option value="active">
                <twig:Listbox:Label>Active</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="paused">
                <twig:Listbox:Label>Paused</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="delayed">
                <twig:Listbox:Label>Delayed</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="canceled">
                <twig:Listbox:Label>Canceled</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

### With description

Use the `Fieldset:Description` component to add a description above or below your `Listbox`:

```twig {"preview":true}
<div class="w-full max-w-xs" style="min-height: 265px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Fieldset:Description>This will be visible to clients on the project.</twig:Fieldset:Description>
        <twig:Listbox name="status" defaultValue="active">
            <twig:Listbox:Option value="active">
                <twig:Listbox:Label>Active</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="paused">
                <twig:Listbox:Label>Paused</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="delayed">
                <twig:Listbox:Label>Delayed</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="canceled">
                <twig:Listbox:Label>Canceled</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

### With placeholder

Use the `placeholder` prop to add a placeholder to your `Listbox` when no value is selected:

```twig {"preview":true}
<div class="w-full max-w-56" style="min-height: 240px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Listbox name="status" placeholder="Select status…">
            <twig:Listbox:Option value="active">
                <twig:Listbox:Label>Active</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="paused">
                <twig:Listbox:Label>Paused</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="delayed">
                <twig:Listbox:Label>Delayed</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="canceled">
                <twig:Listbox:Label>Canceled</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

### With avatars

Add an `Avatar` to a `Listbox:Option` by inserting it before your `Listbox:Label`:

```twig {"preview":true}
{% set users = [
    {id: 1, name: 'Leslie Alexander', initials: 'la', avatarUrl: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {id: 2, name: 'Michael Foster', initials: 'mf', avatarUrl: 'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {id: 3, name: 'Dries Vincent', initials: 'dv', avatarUrl: 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {id: 4, name: 'Lindsay Walton', initials: 'lw', avatarUrl: 'https://images.unsplash.com/photo-1517841905240-472988babdf9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {id: 5, name: 'Courtney Henry', initials: 'ch', avatarUrl: 'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {id: 6, name: 'Tom Cook', initials: 'tc', avatarUrl: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {id: 7, name: 'Whitney Francis', initials: 'wf', avatarUrl: 'https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {id: 8, name: 'Leonard Krasner', initials: 'lk', avatarUrl: 'https://images.unsplash.com/photo-1519345182560-3f2917c472ef?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
] %}

<div class="w-full max-w-56" style="min-height: 330px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Assigned to</twig:Fieldset:Label>
        <twig:Listbox name="user" defaultValue="1">
            {% for user in users %}
                <twig:Listbox:Option value="{{ user.id }}">
                    <twig:Avatar src="{{ user.avatarUrl }}" initials="{{ user.initials }}" class="bg-purple-500 text-white" />
                    <twig:Listbox:Label>{{ user.name }}</twig:Listbox:Label>
                </twig:Listbox:Option>
            {% endfor %}
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

### With icons

Add an icon to a `Listbox:Option` by inserting it before your `Listbox:Label`:

```twig {"preview":true}
<div class="w-full max-w-56" style="min-height: 200px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Alignment</twig:Fieldset:Label>
        <twig:Listbox name="alignment" defaultValue="left">
            <twig:Listbox:Option value="left">
                <twig:ux:icon name="heroicons:bars-3-bottom-left" />
                <twig:Listbox:Label>Left</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="right">
                <twig:ux:icon name="heroicons:bars-3-bottom-right" />
                <twig:Listbox:Label>Right</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="justified">
                <twig:ux:icon name="heroicons:bars-3" />
                <twig:Listbox:Label>Justified</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

The `Listbox:Option` component is designed to work best with 16×16 icons.

If you're using your own custom icons, make sure they include the `data-slot="icon"` attribute so they receive the correct styles.

### With flags

Add a flag icon to a `Listbox:Option` by inserting it before your `Listbox:Label`, just like any other icon:

```twig {"preview":true}
{%- set countries = [
    {name: 'Canada', code: 'CA', flag: 'flagpack:ca'},
    {name: 'United States', code: 'US', flag: 'flagpack:us'},
    {name: 'Mexico', code: 'MX', flag: 'flagpack:mx'},
] -%}

<div class="w-full max-w-56" style="min-height: 200px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Country</twig:Fieldset:Label>
        <twig:Listbox name="country" defaultValue="MX">
            {%- for country in countries -%}
                <twig:Listbox:Option value="{{ country.code }}">
                    <twig:ux:icon name="{{ country.flag }}" class="w-5 sm:w-4" />
                    <twig:Listbox:Label>{{ country.name }}</twig:Listbox:Label>
                </twig:Listbox:Option>
            {%- endfor -%}
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

We like the 16×12 flag icons from [Flagpack](https://flagpack.xyz/), a great set of open-source flag icons.

### With secondary text

Use the `Listbox:Description` component to add secondary text to a listbox option:

```twig {"preview":true}
{% set users = [
    {id: 1, name: 'Leslie Alexander', handle: 'lesliealexander'},
    {id: 2, name: 'Michael Foster', handle: 'michaelfoster'},
    {id: 3, name: 'Dries Vincent', handle: 'driesvincent'},
    {id: 4, name: 'Lindsay Walton', handle: 'lindsaywalton'},
    {id: 5, name: 'Courtney Henry', handle: 'courtneyhenry'},
    {id: 6, name: 'Tom Cook', handle: 'tomcook'},
    {id: 7, name: 'Whitney Francis', handle: 'whitneyfrancis'},
    {id: 8, name: 'Leonard Krasner', handle: 'leonardkrasner'},
    {id: 9, name: 'Floyd Miles', handle: 'floydmiles'},
    {id: 10, name: 'Emily Selman', handle: 'emilyselman'},
    {id: 11, name: 'Kristin Watson', handle: 'kristinwatson'},
    {id: 12, name: 'Emma Dorsey', handle: 'emmadorsey'},
    {id: 13, name: 'Alicia Bell', handle: 'aliciabell'},
    {id: 14, name: 'Jenny Wilson', handle: 'jennywilson'},
    {id: 15, name: 'Anna Roberts', handle: 'annaroberts'},
    {id: 16, name: 'Benjamin Russel', handle: 'benjaminrussel'},
    {id: 17, name: 'Jeffrey Webb', handle: 'jeffreywebb'},
    {id: 18, name: 'Kathryn Murphy', handle: 'kathrynmurphy'},
    {id: 19, name: 'Lawrence Hunter', handle: 'lawrencehunter'},
    {id: 20, name: 'Yvette Armstrong', handle: 'yvettearmstrong'},
    {id: 21, name: 'Angela Fisher', handle: 'angelafisher'},
    {id: 22, name: 'Blake Reid', handle: 'blakereid'},
    {id: 23, name: 'Hector Gibbons', handle: 'hectorgibbons'},
    {id: 24, name: 'Fabricio Mendes', handle: 'fabriciomendes'},
    {id: 25, name: 'Jillian Steward', handle: 'jilliansteward'},
    {id: 26, name: 'Chelsea Hagon', handle: 'chelseahagon'},
] %}

<div class="w-full max-w-xs" style="min-height: 320px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>User</twig:Fieldset:Label>
        <twig:Listbox name="user" defaultValue="3">
            {% for user in users %}
                <twig:Listbox:Option value="{{ user.id }}">
                    <twig:Listbox:Label>{{ user.name }}</twig:Listbox:Label>
                    <twig:Listbox:Description>@{{ user.handle }}</twig:Listbox:Description>
                </twig:Listbox:Option>
            {% endfor %}
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

### Disabled state

Add the `disabled` prop to the `Fieldset:Field` component to disable a `Listbox` and the associated `Fieldset:Label`:

```twig {"preview":true}
<div class="w-full max-w-56" style="min-height: 175px">
    <twig:Fieldset:Field disabled>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Listbox name="status" defaultValue="delayed">
            <twig:Listbox:Option value="active">
                <twig:Listbox:Label>Active</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="paused">
                <twig:Listbox:Label>Paused</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="delayed">
                <twig:Listbox:Label>Delayed</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="canceled">
                <twig:Listbox:Label>Canceled</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

You can also disable a listbox outside of a `Fieldset:Field` by adding the `disabled` prop directly to the `Listbox` itself.

### Validation errors

Add the `invalid` prop to the `Listbox` component to indicate a validation error, and render the error using the `Fieldset:ErrorMessage` component:

```twig {"preview":true}
<div class="w-full max-w-56" style="min-height: 240px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Project status</twig:Fieldset:Label>
        <twig:Listbox name="status" placeholder="Select status…" invalid>
            <twig:Listbox:Option value="active">
                <twig:Listbox:Label>Active</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="paused">
                <twig:Listbox:Label>Paused</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="delayed">
                <twig:Listbox:Label>Delayed</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="canceled">
                <twig:Listbox:Label>Canceled</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
        <twig:Fieldset:ErrorMessage>A project status is required.</twig:Fieldset:ErrorMessage>
    </twig:Fieldset:Field>
</div>
```

### Constraining width

Use the `class` attribute on the `Listbox` component to make layout adjustments like adjusting the max-width:

```twig {"preview":true}
<div class="w-full max-w-40" style="min-height: 320px">
    <twig:Fieldset:Field>
        <twig:Fieldset:Label>Day of the week</twig:Fieldset:Label>
        <twig:Listbox class="max-w-40" name="day_of_the_week" defaultValue="Monday">
            <twig:Listbox:Option value="Monday">
                <twig:Listbox:Label>Monday</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="Tuesday">
                <twig:Listbox:Label>Tuesday</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="Wednesday">
                <twig:Listbox:Label>Wednesday</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="Thursday">
                <twig:Listbox:Label>Thursday</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="Friday">
                <twig:Listbox:Label>Friday</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="Saturday">
                <twig:Listbox:Label>Saturday</twig:Listbox:Label>
            </twig:Listbox:Option>
            <twig:Listbox:Option value="Sunday">
                <twig:Listbox:Label>Sunday</twig:Listbox:Label>
            </twig:Listbox:Option>
        </twig:Listbox>
    </twig:Fieldset:Field>
</div>
```

Be aware that the `class` attribute is a sharp knife — make sure to only add classes that don't conflict with classes the component already includes or you'll get unexpected results.

## API Reference

::: api-reference
