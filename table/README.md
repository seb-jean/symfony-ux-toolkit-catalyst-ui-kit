# Table

If you can put it in a database, you can put it in a table.

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table>
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Table`, `Table:Head`, `Table:Body`, `Table:Row`, `Table:Header`, and `Table:Cell` components to build a table:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table>
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

### Responsive tables

Tables automatically become scrollable when they are wider than their container:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', handle: 'lesliealexander', role: 'Co-Founder / CEO', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', handle: 'michaelfoster', role: 'Co-Founder / CTO', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', handle: 'driesvincent', role: 'Business Relations', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', handle: 'lindsaywalton', role: 'Front-end Developer', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', handle: 'courtneyhenry', role: 'Designer', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Handle</twig:Table:Header>
                <twig:Table:Header>Role</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>@{{ user.handle }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.role }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

Set the CSS `--gutter` variable to match the padding of the containing element to make sure the table isn't cropped unnecessarily when it becomes scrollable. You can change the gutter responsively using media query variants, such as `sm:[--gutter:--spacing(4)]`.

### Full-width tables

Use the `bleed` prop and set the CSS `--gutter` variable to match the padding of the containing element to make a table full-width:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <div class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table bleed>
            <twig:Table:Head>
                <twig:Table:Row>
                    <twig:Table:Header>Name</twig:Table:Header>
                    <twig:Table:Header>Email</twig:Table:Header>
                    <twig:Table:Header>Access</twig:Table:Header>
                </twig:Table:Row>
            </twig:Table:Head>
            <twig:Table:Body>
                {%- for user in users -%}
                    <twig:Table:Row>
                        <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                        <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                        <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                    </twig:Table:Row>
                {%- endfor -%}
            </twig:Table:Body>
        </twig:Table>
    </div>
</div>
```

Full-width tables are still responsive and will become scrollable if they don't fit within the containing element.

### Rows as links

Use the `href` prop on the `Table:Row` component to treat an entire row like a link:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin', url: '#lesliealexander'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner', url: '#michaelfoster'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member', url: '#driesvincent'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member', url: '#lindsaywalton'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin', url: '#courtneyhenry'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row href="{{ user.url }}">
                    <twig:Table:Cell class="font-medium" link:tabindex="0">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

When used as a link, `Table:Row` also accepts the `target` and `title` props like a regular link.

### With condensed spacing

Use the `dense` prop to render the table with condensed spacing:

```twig {"preview":true}
{%- set players = [
    {rank: 1, name: 'Mitchell Marner', position: 'R', gamesPlayed: 80, goals: 30, assists: 69, points: 99, plusMinus: '+18'},
    {rank: 2, name: 'William Nylander', position: 'R', gamesPlayed: 82, goals: 40, assists: 47, points: 87, plusMinus: '+10'},
    {rank: 3, name: 'Auston Matthews', position: 'C', gamesPlayed: 74, goals: 40, assists: 45, points: 85, plusMinus: '+31'},
    {rank: 4, name: 'John Tavares', position: 'C', gamesPlayed: 80, goals: 36, assists: 44, points: 80, plusMinus: '-7'},
    {rank: 5, name: 'Michael Bunting', position: 'L', gamesPlayed: 82, goals: 23, assists: 26, points: 49, plusMinus: '+21'},
    {rank: 6, name: 'Morgan Rielly', position: 'D', gamesPlayed: 65, goals: 4, assists: 37, points: 41, plusMinus: '-9'},
    {rank: 7, name: 'Calle Jarnkrok', position: 'C', gamesPlayed: 73, goals: 20, assists: 19, points: 39, plusMinus: '+9'},
    {rank: 8, name: 'Alex Kerfoot', position: 'C', gamesPlayed: 82, goals: 10, assists: 22, points: 32, plusMinus: '+8'},
    {rank: 9, name: 'David Kampf', position: 'C', gamesPlayed: 82, goals: 7, assists: 20, points: 27, plusMinus: '+6'},
    {rank: 10, name: 'Mark Giordano', position: 'D', gamesPlayed: 78, goals: 4, assists: 20, points: 24, plusMinus: '+27'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table dense class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Rank</twig:Table:Header>
                <twig:Table:Header>Player</twig:Table:Header>
                <twig:Table:Header class="text-right">Pos</twig:Table:Header>
                <twig:Table:Header class="text-right">GP</twig:Table:Header>
                <twig:Table:Header class="text-right">G</twig:Table:Header>
                <twig:Table:Header class="text-right">A</twig:Table:Header>
                <twig:Table:Header class="text-right">P</twig:Table:Header>
                <twig:Table:Header class="text-right">+/-</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for player in players -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="tabular-nums">{{ player.rank }}</twig:Table:Cell>
                    <twig:Table:Cell class="font-medium">{{ player.name }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-right">{{ player.position }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-right tabular-nums">{{ player.gamesPlayed }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-right tabular-nums">{{ player.goals }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-right tabular-nums">{{ player.assists }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-right tabular-nums">{{ player.points }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-right tabular-nums">{{ player.plusMinus }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

### With grid lines

Use the `grid` prop to render the table with vertical grid lines:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table grid class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

### With striped rows

Use the `striped` prop to render the table with striped rows and no horizontal borders:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table striped class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

### With different heading color

Use the `text-{color}` utilities on the `Table:Row` component inside your `Table:Head` to change the color of table headings:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row class="text-zinc-950 dark:text-white">
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

### With complex content

Tables are unopinionated about their content and will adapt to just about anything you include:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin', online: true, avatarUrl: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner', online: true, avatarUrl: 'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member', online: false, avatarUrl: 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member', online: true, avatarUrl: 'https://images.unsplash.com/photo-1517841905240-472988babdf9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin', online: true, avatarUrl: 'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Role</twig:Table:Header>
                <twig:Table:Header>Status</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell>
                        <div class="flex items-center gap-4">
                            <twig:Avatar src="{{ user.avatarUrl }}" class="size-12" />
                            <div>
                                <div class="font-medium">{{ user.name }}</div>
                                <div class="text-zinc-500">
                                    <a href="#" class="hover:text-zinc-700">
                                        {{ user.email }}
                                    </a>
                                </div>
                            </div>
                        </div>
                    </twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                    <twig:Table:Cell>
                        {%- if user.online -%}
                            <twig:Badge color="lime">Online</twig:Badge>
                        {%- else -%}
                            <twig:Badge color="zinc">Offline</twig:Badge>
                        {%- endif -%}
                    </twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

### With pagination

Add a `Pagination` component below your table to add pagination controls:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="w-full">
    <h1 class="mb-6 text-base font-semibold text-zinc-950 dark:text-white">Users</h1>
    <twig:Table>
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
    <twig:Pagination class="mt-6">
        <twig:Pagination:Previous href="?page=2" />
        <twig:Pagination:List>
            <twig:Pagination:Page href="?page=1">1</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=2">2</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=3" current>
                3
            </twig:Pagination:Page>
            <twig:Pagination:Page href="?page=4">4</twig:Pagination:Page>
            <twig:Pagination:Gap />
            <twig:Pagination:Page href="?page=65">65</twig:Pagination:Page>
            <twig:Pagination:Page href="?page=66">66</twig:Pagination:Page>
        </twig:Pagination:List>
        <twig:Pagination:Next href="?page=4" />
    </twig:Pagination>
</div>
```

Use the `mt-*` utilities to control the space between the table and the pagination controls.

### With dropdowns

Use the `Dropdown` component within a `Table:Cell` to add a dropdown menu:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div class="-mt-4 w-full">
    <twig:Table class="[--gutter:--spacing(6)] sm:[--gutter:--spacing(8)]">
        <twig:Table:Head>
            <twig:Table:Row>
                <twig:Table:Header>Name</twig:Table:Header>
                <twig:Table:Header>Email</twig:Table:Header>
                <twig:Table:Header>Access</twig:Table:Header>
                <twig:Table:Header class="relative w-0">
                    <span class="sr-only">Actions</span>
                </twig:Table:Header>
            </twig:Table:Row>
        </twig:Table:Head>
        <twig:Table:Body>
            {%- for user in users -%}
                <twig:Table:Row>
                    <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                    <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                    <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                    <twig:Table:Cell>
                        <div class="-mx-3 -my-1.5 sm:-mx-2.5">
                            <twig:Dropdown>
                                <twig:Dropdown:Button plain aria-label="More options">
                                    <twig:ux:icon name="heroicons:ellipsis-horizontal-16-solid" />
                                </twig:Dropdown:Button>
                                <twig:Dropdown:Menu anchor="bottom end">
                                    <twig:Dropdown:Item>View</twig:Dropdown:Item>
                                    <twig:Dropdown:Item>Edit</twig:Dropdown:Item>
                                    <twig:Dropdown:Item>Delete</twig:Dropdown:Item>
                                </twig:Dropdown:Menu>
                            </twig:Dropdown>
                        </div>
                    </twig:Table:Cell>
                </twig:Table:Row>
            {%- endfor -%}
        </twig:Table:Body>
    </twig:Table>
</div>
```

When adding elements like dropdowns to a table (especially with the `plain` style), consider using negative margins to avoid increasing the size of the table cell. For instance, in the example above we've added `-my-1.5` to make sure the dropdown only takes up 24px of vertical space in the actual layout, which matches the height of the text in the other cells.

### In dialog

Add a `Table` to your `Dialog:Body` component to include a table in a dialog:

```twig {"preview":true}
{%- set users = [
    {name: 'Leslie Alexander', email: 'leslie.alexander@example.com', access: 'Admin'},
    {name: 'Michael Foster', email: 'michael.foster@example.com', access: 'Owner'},
    {name: 'Dries Vincent', email: 'dries.vincent@example.com', access: 'Member'},
    {name: 'Lindsay Walton', email: 'lindsay.walton@example.com', access: 'Member'},
    {name: 'Courtney Henry', email: 'courtney.henry@example.com', access: 'Admin'},
] -%}
<div style="min-height: 425px">
    <twig:Dialog id="show-users" size="3xl">
        <twig:block name="button">
            <twig:Button type="button" {{ ...dialog_button_attrs }}>
                Show users
            </twig:Button>
        </twig:block>
        <twig:Dialog:Title>Users</twig:Dialog:Title>
        <twig:Dialog:Description>The follow users have access to your account.</twig:Dialog:Description>
        <twig:Dialog:Body>
            <twig:Table bleed dense>
                <twig:Table:Head>
                    <twig:Table:Row>
                        <twig:Table:Header>Name</twig:Table:Header>
                        <twig:Table:Header>Email</twig:Table:Header>
                        <twig:Table:Header>Role</twig:Table:Header>
                    </twig:Table:Row>
                </twig:Table:Head>
                <twig:Table:Body>
                    {%- for user in users -%}
                        <twig:Table:Row>
                            <twig:Table:Cell class="font-medium">{{ user.name }}</twig:Table:Cell>
                            <twig:Table:Cell>{{ user.email }}</twig:Table:Cell>
                            <twig:Table:Cell class="text-zinc-500">{{ user.access }}</twig:Table:Cell>
                        </twig:Table:Row>
                    {%- endfor -%}
                </twig:Table:Body>
            </twig:Table>
        </twig:Dialog:Body>
        <twig:Dialog:Actions>
            <twig:Button {{ ...dialog_close_attrs }}>Close</twig:Button>
        </twig:Dialog:Actions>
    </twig:Dialog>
</div>
```

When using tables within dialogs, the `--gutter` variable is automatically set to match the dialog's padding.

## API Reference

::: api-reference
