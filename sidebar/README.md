# Sidebar

When you need to move from a horizontal nav to a sidebar, you know your app is all grown up.

```twig {"preview":true}
<div class="h-152 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Header>
                <twig:Dropdown>
                    <twig:Dropdown:Button as="Sidebar:Item" class="mb-2.5">
                        <twig:Avatar src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                        <twig:Sidebar:Label>Tailwind Labs</twig:Sidebar:Label>
                        <twig:ux:icon name="heroicons:chevron-down-16-solid" />
                    </twig:Dropdown:Button>
                    <twig:Dropdown:Menu class="min-w-64" anchor="bottom start">
                        <twig:Dropdown:Item href="/teams/1/settings">
                            <twig:ux:icon name="heroicons:cog-8-tooth-16-solid" />
                            <twig:Dropdown:Label>Settings</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Divider />
                        <twig:Dropdown:Item href="/teams/1">
                            <twig:Avatar slot="icon" src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                            <twig:Dropdown:Label>Tailwind Labs</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Item href="/teams/2">
                            <twig:Avatar slot="icon" initials="WC" class="bg-purple-500 text-white" />
                            <twig:Dropdown:Label>Workcation</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Divider />
                        <twig:Dropdown:Item href="/teams/create">
                            <twig:ux:icon name="heroicons:plus-16-solid" />
                            <twig:Dropdown:Label>New team&hellip;</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                    </twig:Dropdown:Menu>
                </twig:Dropdown>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/search">
                        <twig:ux:icon name="heroicons:magnifying-glass-20-solid" />
                        <twig:Sidebar:Label>Search</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/inbox">
                        <twig:ux:icon name="heroicons:inbox-20-solid" />
                        <twig:Sidebar:Label>Inbox</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Header>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/" :current="true">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
                <twig:Sidebar:Spacer />
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/support">
                        <twig:ux:icon name="heroicons:question-mark-circle-20-solid" />
                        <twig:Sidebar:Label>Support</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/changelog">
                        <twig:ux:icon name="heroicons:sparkles-20-solid" />
                        <twig:Sidebar:Label>Changelog</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
            <twig:Sidebar:Footer>
                <twig:Dropdown>
                    <twig:Dropdown:Button as="Sidebar:Item">
                        <span class="flex min-w-0 items-center gap-3">
                            <twig:Avatar src="https://catalyst-demo.tailwindui.com/users/erica.jpg" class="size-10" square />
                            <span class="min-w-0">
                                <span class="block truncate text-sm/5 font-medium text-zinc-950 dark:text-white">Erica</span>
                                <span class="block truncate text-xs/5 font-normal text-zinc-500 dark:text-zinc-400">erica@example.com</span>
                            </span>
                        </span>
                        <twig:ux:icon name="heroicons:chevron-up-16-solid" />
                    </twig:Dropdown:Button>
                    <twig:Dropdown:Menu class="min-w-64" anchor="top start">
                        <twig:Dropdown:Item href="/my-profile">
                            <twig:ux:icon name="heroicons:user-16-solid" />
                            <twig:Dropdown:Label>My profile</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Item href="/settings">
                            <twig:ux:icon name="heroicons:cog-8-tooth-16-solid" />
                            <twig:Dropdown:Label>Settings</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Divider />
                        <twig:Dropdown:Item href="/privacy-policy">
                            <twig:ux:icon name="heroicons:shield-check-16-solid" />
                            <twig:Dropdown:Label>Privacy policy</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Item href="/share-feedback">
                            <twig:ux:icon name="heroicons:light-bulb-16-solid" />
                            <twig:Dropdown:Label>Share feedback</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Divider />
                        <twig:Dropdown:Item href="/logout">
                            <twig:ux:icon name="heroicons:arrow-right-start-on-rectangle-16-solid" />
                            <twig:Dropdown:Label>Sign out</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                    </twig:Dropdown:Menu>
                </twig:Dropdown>
            </twig:Sidebar:Footer>
        </twig:Sidebar>
    </div>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Sidebar`, `Sidebar:Body`, `Sidebar:Section`, and `Sidebar:Item` components to build a basic sidebar:

```twig {"preview":true}
<div class="h-96 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">Home</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">Events</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">Orders</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">Broadcasts</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">Settings</twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

### With logo

Add your own logo as an image or component to your sidebar, using utility classes to fine-tune the layout to suit your logo:

```twig {"preview":true}
<div class="h-96 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <div class="mb-2 flex">
                    <a href="#" aria-label="Home">
                        <svg class="size-11 fill-sky-500 sm:size-10" viewBox="0 0 32 32">
                            <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z" />
                        </svg>
                    </a>
                </div>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">Home</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">Events</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">Orders</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">Broadcasts</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">Settings</twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

### With icons

Add an icon as the first child of a `Sidebar:Item` to render it next to the link text:

```twig {"preview":true}
<div class="h-96 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

The `Sidebar:Item` component is designed to work best with 20×20 icons.

If you're using your own custom icons, make sure they include the `data-slot="icon"` attribute so they receive the correct styles.

### With active state

Use the `current` prop to specify which `Sidebar:Item` is the current navigation item:

```twig {"preview":true}
<div class="h-96 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/" current>
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

### With sticky header

Use the `Sidebar:Header` component before the `Sidebar:Body` component to add a sticky header to the sidebar:

```twig {"preview":true}
<div class="h-120 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Header>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/search">
                        <twig:ux:icon name="heroicons:magnifying-glass-20-solid" />
                        <twig:Sidebar:Label>Search</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/inbox">
                        <twig:ux:icon name="heroicons:inbox-20-solid" />
                        <twig:Sidebar:Label>Inbox</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Header>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

### With sticky footer

Use the `Sidebar:Footer` component after the `Sidebar:Body` component to add a sticky footer to the sidebar:

```twig {"preview":true}
<div class="h-120 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
            <twig:Sidebar:Footer>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item>
                        <twig:Avatar src="https://catalyst-demo.tailwindui.com/users/erica.jpg" />
                        <twig:Sidebar:Label>Erica</twig:Sidebar:Label>
                        <twig:ux:icon name="heroicons:chevron-right-16-solid" />
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Footer>
        </twig:Sidebar>
    </div>
</div>
```

### With section headings

Use the `Sidebar:Heading` component to add a heading to a section:

```twig {"preview":true}
<div class="h-120 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Heading>Resources</twig:Sidebar:Heading>
                    <twig:Sidebar:Item href="/resources">
                        <twig:ux:icon name="heroicons:question-mark-circle-20-solid" />
                        <twig:Sidebar:Label>Support</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/changelog">
                        <twig:ux:icon name="heroicons:sparkles-20-solid" />
                        <twig:Sidebar:Label>Changelog</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

### With space between sections

Use the `Sidebar:Spacer` component to space out sections in a sidebar:

```twig {"preview":true}
<div class="h-120 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
                <twig:Sidebar:Spacer />
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/logout">
                        <twig:ux:icon name="heroicons:arrow-right-start-on-rectangle-20-solid" />
                        <twig:Sidebar:Label>Sign out</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

### With divider

Use the `Sidebar:Divider` component to add a dividing line between sections in a sidebar:

```twig {"preview":true}
<div class="h-120 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
                <twig:Sidebar:Divider />
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/support">
                        <twig:ux:icon name="heroicons:question-mark-circle-20-solid" />
                        <twig:Sidebar:Label>Support</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/changelog">
                        <twig:ux:icon name="heroicons:sparkles-20-solid" />
                        <twig:Sidebar:Label>Changelog</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

### With dropdown

Use the `Dropdown` component add a dropdown menu to a sidebar by rendering the `Dropdown:Button` as a `Sidebar:Item`:

```twig {"preview":true}
<div class="h-120 w-full">
    <div class="h-full w-64 border-r border-zinc-950/5 bg-zinc-100 dark:bg-zinc-950">
        <twig:Sidebar>
            <twig:Sidebar:Header>
                <twig:Dropdown>
                    <twig:Dropdown:Button as="Sidebar:Item">
                        <twig:Avatar src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                        <twig:Sidebar:Label>Tailwind Labs</twig:Sidebar:Label>
                        <twig:ux:icon name="heroicons:chevron-down-16-solid" />
                    </twig:Dropdown:Button>
                    <twig:Dropdown:Menu class="min-w-64" anchor="bottom start">
                        <twig:Dropdown:Item href="/teams/1/settings">
                            <twig:ux:icon name="heroicons:cog-8-tooth-16-solid" />
                            <twig:Dropdown:Label>Settings</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Divider />
                        <twig:Dropdown:Item href="/teams/1">
                            <twig:Avatar slot="icon" src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                            <twig:Dropdown:Label>Tailwind Labs</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Item href="/teams/2">
                            <twig:Avatar slot="icon" initials="WC" class="bg-purple-500 text-white" />
                            <twig:Dropdown:Label>Workcation</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                        <twig:Dropdown:Divider />
                        <twig:Dropdown:Item href="/teams/create">
                            <twig:ux:icon name="heroicons:plus-16-solid" />
                            <twig:Dropdown:Label>New team&hellip;</twig:Dropdown:Label>
                        </twig:Dropdown:Item>
                    </twig:Dropdown:Menu>
                </twig:Dropdown>
            </twig:Sidebar:Header>
            <twig:Sidebar:Body>
                <twig:Sidebar:Section>
                    <twig:Sidebar:Item href="/">
                        <twig:ux:icon name="heroicons:home-20-solid" />
                        <twig:Sidebar:Label>Home</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events">
                        <twig:ux:icon name="heroicons:square-2-stack-20-solid" />
                        <twig:Sidebar:Label>Events</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/orders">
                        <twig:ux:icon name="heroicons:ticket-20-solid" />
                        <twig:Sidebar:Label>Orders</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </div>
</div>
```

See the [Dropdown docs](/toolkit/kits/catalyst/components/dropdown) for more information on building dropdown menus.

## API Reference

::: api-reference
