# Avatar

It's more than just an image with a border radius, I promise.

```twig {"preview":true}
{%- set user = {
    avatarUrl: 'https://images.unsplash.com/photo-1595211877493-41a4e5f236b3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=3&w=256&h=256&q=80'
} -%}
<div class="flex items-end gap-8">
    <twig:Avatar class="size-6" src="{{ user.avatarUrl }}" />
    <twig:Avatar class="size-8" src="{{ user.avatarUrl }}" />
    <twig:Avatar class="size-10" src="{{ user.avatarUrl }}" />
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Avatar` component along with a `size-*` utility to render an avatar image:

```twig {"preview":true}
{%- set user = {
    avatarUrl: 'https://images.unsplash.com/photo-1595211877493-41a4e5f236b3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=3&w=256&h=256&q=80'
} -%}
<div class="flex items-end gap-8">
    <twig:Avatar class="size-6" src="{{ user.avatarUrl }}" />
    <twig:Avatar class="size-8" src="{{ user.avatarUrl }}" />
    <twig:Avatar class="size-10" src="{{ user.avatarUrl }}" />
</div>
```

### With initials

Use the `initials` prop to render an avatar with initials:

```twig {"preview":true}
<div class="flex items-end gap-8">
    <twig:Avatar initials="tw" class="size-6 bg-zinc-900 text-white dark:bg-white dark:text-black" />
    <twig:Avatar initials="tw" class="size-8 bg-zinc-900 text-white dark:bg-white dark:text-black" />
    <twig:Avatar initials="tw" class="size-10 bg-zinc-900 text-white dark:bg-white dark:text-black" />
</div>
```

Be sure to include `bg-{color}` and `text-{color}` utilities for both light mode and dark mode.

### With initials as fallback

Include both the `src` and `initials` props to show the initials as a fallback while the avatar image loads:

```twig {"preview":true}
{%- set user = {
    avatarUrl: 'https://images.unsplash.com/photo-1595211877493-41a4e5f236b3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=3&w=256&h=256&q=80',
    initials: 'tw'
} -%}
<div class="flex items-end gap-8">
    <twig:Avatar src="{{ user.avatarUrl }}" initials="{{ user.initials }}" class="size-6 bg-purple-500 text-white" />
    <twig:Avatar src="{{ user.avatarUrl }}" initials="{{ user.initials }}" class="size-8 bg-purple-500 text-white" />
    <twig:Avatar src="{{ user.avatarUrl }}" initials="{{ user.initials }}" class="size-10 bg-purple-500 text-white" />
</div>
```

### Square avatars

Use the `square` prop to render a square avatar:

```twig {"preview":true}
{%- set user = {
    avatarUrl: 'https://images.unsplash.com/photo-1595211877493-41a4e5f236b3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=3&w=256&h=256&q=80',
    initials: 'tw'
} -%}
<div class="flex items-end gap-8">
    <twig:Avatar square class="size-8" src="{{ user.avatarUrl }}" />
    <twig:Avatar square initials="{{ user.initials }}" class="size-8 bg-zinc-900 text-white dark:bg-white dark:text-black" />
</div>
```

### Avatar groups

Use utility classes to overlap a list of avatars and style them as a group:

```twig {"preview":true}
{%- set users = [
    {avatarUrl: 'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {avatarUrl: 'https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {avatarUrl: 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2.25&w=256&h=256&q=80'},
    {avatarUrl: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
] -%}
<div class="flex items-center justify-center -space-x-2">
    {%- for user in users -%}
        <twig:Avatar src="{{ user.avatarUrl }}" class="size-8 ring-2 ring-white dark:ring-zinc-900" />
    {%- endfor -%}
</div>
```

Use the `ring-{color}` and `dark:ring-{color}` utilities to match the notched area with your background color.

### Using as buttons

Use the `Avatar:Button` component to render an avatar as a button:

```twig {"preview":true}
{%- set user = {
    avatarUrl: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
} -%}
<div class="flex items-end gap-8">
    <twig:Avatar:Button class="size-8" src="{{ user.avatarUrl }}" />
    <twig:Avatar:Button square class="size-8" src="{{ user.avatarUrl }}" />
</div>
```

### Using as links

Use the `Avatar:Button` component with the `href` prop to render an avatar as a link:

```twig {"preview":true}
{%- set user = {
    url: '#',
    avatarUrl: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
} -%}
<div class="flex items-end gap-8">
    <twig:Avatar:Button href="{{ user.url }}" class="size-8" src="{{ user.avatarUrl }}" />
    <twig:Avatar:Button square href="{{ user.url }}" class="size-8" src="{{ user.avatarUrl }}" />
</div>
```

## API Reference

::: api-reference
