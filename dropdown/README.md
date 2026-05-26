# Dropdown

Probably the number one reason you're looking for a UI kit in the first place.

```twig {"preview":true}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Item href="/users/1">View</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/users/1/edit">Edit</twig:Dropdown:Item>
            <twig:Dropdown:Item>Delete</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Dropdown`, `Dropdown:Button`, `Dropdown:Menu`, and `Dropdown:Item` components to build a basic dropdown menu:

```twig {"preview":true}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Item href="/users/1">View</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/users/1/edit">Edit</twig:Dropdown:Item>
            <twig:Dropdown:Item>Delete</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

Use the `href` attribute for dropdown items that are links.

### Button style

The `Dropdown:Button` component is rendered as a `Button` by default and directly accepts all of the same styling props, such as `color`, `outline`, and `plain`:

```twig {"preview":true}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button color="cyan">
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Item href="#">View</twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">Edit</twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">Export as CSV&hellip;</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

### Menu placement

Use the `anchor` prop on the `Dropdown:Menu` component to position the dropdown menu relative to the trigger:

```twig {"preview":true}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-up-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu anchor="top start">
            <twig:Dropdown:Item href="#">View</twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">Edit</twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">Export as CSV&hellip;</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

Use the values `top`, `right`, `bottom`, `left` to center the menu along the appropriate edge, or combine it with `start` or `end` to align the menu to a specific corner, such as `top start` or `bottom end`.

### With disabled items

Use the `disabled` attribute on a `Dropdown:Item` to disable that item and prevent it from being selected:

```twig {"preview":true}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Item href="#">Open</twig:Dropdown:Item>
            <twig:Dropdown:Item disabled>Rename</twig:Dropdown:Item>
            <twig:Dropdown:Item>Delete</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

### With sections

Use the `Dropdown:Section`, `Dropdown:Heading`, and `Dropdown:Divider` components to group dropdown items into sections:

```twig {"preview":true}
<div style="min-height: 270px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Section aria-label="Account">
                <twig:Dropdown:Item href="/account">Account</twig:Dropdown:Item>
                <twig:Dropdown:Item href="/notifications">Notifications</twig:Dropdown:Item>
                <twig:Dropdown:Item href="/billing">Billing</twig:Dropdown:Item>
            </twig:Dropdown:Section>
            <twig:Dropdown:Divider />
            <twig:Dropdown:Section>
                <twig:Dropdown:Heading>My events</twig:Dropdown:Heading>
                <twig:Dropdown:Item href="/upcoming-events">Upcoming events</twig:Dropdown:Item>
                <twig:Dropdown:Item href="/past-events">Past events</twig:Dropdown:Item>
            </twig:Dropdown:Section>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

Headings are optional but be sure to add an `aria-label` to sections without headings for assistive technology.

### With descriptions

Use the `Dropdown:Description` component along with a `Dropdown:Label` to add a description to a dropdown item:

```twig {"preview":true}
<div style="min-height: 220px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Item href="#">
                <twig:Dropdown:Label>Open</twig:Dropdown:Label>
                <twig:Dropdown:Description>Open the file in a new tab.</twig:Dropdown:Description>
            </twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">
                <twig:Dropdown:Label>Rename</twig:Dropdown:Label>
                <twig:Dropdown:Description>Rename the file.</twig:Dropdown:Description>
            </twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">
                <twig:Dropdown:Label>Delete</twig:Dropdown:Label>
                <twig:Dropdown:Description>Move the file to the trash.</twig:Dropdown:Description>
            </twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

### With icons

Add an icon as the first child of a `Dropdown:Item` to render it alongside the `Dropdown:Label`:

```twig {"preview":true}
<div style="min-height: 250px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu anchor="bottom">
            <twig:Dropdown:Item href="#">
                <twig:ux:icon name="heroicons:user-16-solid" data-slot="icon" />
                <twig:Dropdown:Label>Account</twig:Dropdown:Label>
            </twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">
                <twig:ux:icon name="heroicons:cog-8-tooth-16-solid" data-slot="icon" />
                <twig:Dropdown:Label>Settings</twig:Dropdown:Label>
            </twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">
                <twig:ux:icon name="heroicons:information-circle-16-solid" data-slot="icon" />
                <twig:Dropdown:Label>Help center</twig:Dropdown:Label>
            </twig:Dropdown:Item>
            <twig:Dropdown:Divider />
            <twig:Dropdown:Item href="#">
                <twig:ux:icon name="heroicons:moon-16-solid" data-slot="icon" />
                <twig:Dropdown:Label>Dark mode</twig:Dropdown:Label>
            </twig:Dropdown:Item>
            <twig:Dropdown:Divider />
            <twig:Dropdown:Item href="#">
                <twig:ux:icon name="heroicons:arrow-right-start-on-rectangle-16-solid" data-slot="icon" />
                <twig:Dropdown:Label>Sign out</twig:Dropdown:Label>
            </twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

The `Dropdown:Item` component is designed to work best with 16×16 icons.

If you're using your own custom icons, make sure they include the `data-slot="icon"` attribute so they receive the correct styles.

### With keyboard shortcuts

Use the `Dropdown:Shortcut` component along with a `Dropdown:Label` to surface any keyboard shortcuts you've implemented in your application:

```twig {"preview":true}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu anchor="bottom start">
            <twig:Dropdown:Item href="#">
                <twig:Dropdown:Label>Open</twig:Dropdown:Label>
                <twig:Dropdown:Shortcut keys="⌘O" />
            </twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">
                <twig:Dropdown:Label>Rename</twig:Dropdown:Label>
                <twig:Dropdown:Shortcut keys="⌘R" />
            </twig:Dropdown:Item>
            <twig:Dropdown:Item href="#">
                <twig:Dropdown:Label>Delete</twig:Dropdown:Label>
                <twig:Dropdown:Shortcut keys="⇧⌘⌫" />
            </twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

### With header

Use the `Dropdown:Header` component to add a custom header section to the top of a dropdown menu:

```twig {"preview":true}
<div style="min-height: 305px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Header>
                <div class="pr-6">
                    <div class="text-xs text-zinc-500 dark:text-zinc-400">Signed in as Tom Cook</div>
                    <div class="text-sm/7 font-semibold text-zinc-800 dark:text-white">tom@example.com</div>
                </div>
            </twig:Dropdown:Header>
            <twig:Dropdown:Divider />
            <twig:Dropdown:Item href="/my-profile">My profile</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/notifications">Notifications</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/security">Security</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/billing">Billing</twig:Dropdown:Item>
            <twig:Dropdown:Item>Sign out</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

It's important to note that assistive technology will not announce any content in a dropdown header, so keep this in mind when deciding what type of content to include.

### With disabled button

Use the `disabled` attribute on the `Dropdown:Button` component to disable a dropdown:

```twig {"preview":true}
<twig:Dropdown>
    <twig:Dropdown:Button outline disabled>
        Options
        <twig:ux:icon name="heroicons:chevron-down-16-solid" />
    </twig:Dropdown:Button>
    <twig:Dropdown:Menu>
        <twig:Dropdown:Item href="/users/1">View</twig:Dropdown:Item>
        <twig:Dropdown:Item href="/users/1/edit">Edit</twig:Dropdown:Item>
        <twig:Dropdown:Item>Delete</twig:Dropdown:Item>
    </twig:Dropdown:Menu>
</twig:Dropdown>
```

### With icon trigger

Use a `Dropdown:Button` with the `plain` prop in combination with an icon to make an icon-only dropdown trigger:

```twig {"preview":true}
<div style="min-height: 150px">
    <twig:Dropdown>
        <twig:Dropdown:Button plain aria-label="More options">
            <twig:ux:icon name="heroicons:ellipsis-horizontal-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu>
            <twig:Dropdown:Item href="/users/1">View</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/users/1/edit">Edit</twig:Dropdown:Item>
            <twig:Dropdown:Item>Delete</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

Be sure to include an `aria-label` so the button is announced properly to assistive technology.

### With avatar trigger

Render the `Dropdown:Button` with an `Avatar` component to use an avatar as the dropdown trigger:

```twig {"preview":true}
{%- set user = {
    avatarUrl: 'https://images.unsplash.com/photo-1595211877493-41a4e5f236b3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=3&w=256&h=256&q=80',
} -%}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button class="size-8" as="Avatar:Button" src="{{ user.avatarUrl }}" aria-label="Account options" />
        <twig:Dropdown:Menu anchor="bottom">
            <twig:Dropdown:Item href="/profile">My profile</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/settings">Settings</twig:Dropdown:Item>
            <twig:Dropdown:Divider />
            <twig:Dropdown:Item>Sign out</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

### With custom menu width

Use `min-w-*` utilities to increase the minimum width of a `Dropdown:Menu`, and `max-w-*` utilities to prevent it from getting wider than a specific size:

```twig {"preview":true}
<div style="min-height: 165px">
    <twig:Dropdown>
        <twig:Dropdown:Button outline>
            Options
            <twig:ux:icon name="heroicons:chevron-down-16-solid" />
        </twig:Dropdown:Button>
        <twig:Dropdown:Menu class="min-w-48">
            <twig:Dropdown:Item href="/account">Account</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/notifications">Notifications</twig:Dropdown:Item>
            <twig:Dropdown:Item href="/billing">Billing</twig:Dropdown:Item>
        </twig:Dropdown:Menu>
    </twig:Dropdown>
</div>
```

Dropdown menus are sized based on the width of their content by default, so this level of control can be helpful for menus that have very short or very long items.

## API Reference

::: api-reference
