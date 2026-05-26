# Navbar

No one ever got fired for starting a website with a horizontal navigation menu.

```twig {"preview":true}
<div style="min-height: 270px; display: flex; align-items: start; width: 100%;">
    <twig:Navbar class="px-4">
        <twig:Dropdown>
            <twig:Dropdown:Button as="Navbar:Item">
                <twig:Avatar src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                <twig:Navbar:Label>Tailwind Labs</twig:Navbar:Label>
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
        <twig:Navbar:Divider class="max-lg:hidden" />
        <twig:Navbar:Section class="max-lg:hidden">
            <twig:Navbar:Item href="/" current>Home</twig:Navbar:Item>
            <twig:Navbar:Item href="/events">Events</twig:Navbar:Item>
            <twig:Navbar:Item href="/orders">Orders</twig:Navbar:Item>
        </twig:Navbar:Section>
        <twig:Navbar:Spacer />
        <twig:Navbar:Section>
            <twig:Navbar:Item href="/search" aria-label="Search">
                <twig:ux:icon name="heroicons:magnifying-glass-20-solid" />
            </twig:Navbar:Item>
            <twig:Navbar:Item href="/inbox" aria-label="Inbox">
                <twig:ux:icon name="heroicons:inbox-20-solid" />
            </twig:Navbar:Item>
            <twig:Dropdown>
                <twig:Dropdown:Button as="Navbar:Item">
                    <twig:Avatar src="https://catalyst.tailwindui.com/profile-photo.jpg" square />
                </twig:Dropdown:Button>
                <twig:Dropdown:Menu class="min-w-64" anchor="bottom end">
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
        </twig:Navbar:Section>
    </twig:Navbar>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Navbar`, `Navbar:Section` and `Navbar:Item` components to build a basic navbar with navigation links:

```twig {"preview":true}
<twig:Navbar class="px-4">
    <twig:Navbar:Section>
        <twig:Navbar:Item href="/">Home</twig:Navbar:Item>
        <twig:Navbar:Item href="/events">Events</twig:Navbar:Item>
        <twig:Navbar:Item href="/orders">Orders</twig:Navbar:Item>
    </twig:Navbar:Section>
</twig:Navbar>
```

The `Navbar:Item` component can be used either as a link by providing an `href` prop or as a button by omitting the `href` prop.

### With logo

Add your own logo as an image or component at the beginning of your navbar:

```twig {"preview":true}
<twig:Navbar class="px-4">
    <a href="/" aria-label="Home">
        <svg class="size-10 fill-sky-500 sm:size-8" viewBox="0 0 32 32">
            <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z" />
        </svg>
    </a>
    <twig:Navbar:Section>
        <twig:Navbar:Item href="/" current>
            Home
        </twig:Navbar:Item>
        <twig:Navbar:Item href="/events">Events</twig:Navbar:Item>
        <twig:Navbar:Item href="/orders">Orders</twig:Navbar:Item>
    </twig:Navbar:Section>
</twig:Navbar>
```

To best fit the navbar design, we recommend making your logo 40px tall at mobile sizes, and 32px tall at the `sm` breakpoint above.

### With active state

Use the `current` prop to specify which `Navbar:Item` is the current navigation item:

```twig {"preview":true}
<twig:Navbar class="px-4">
    <a href="/" aria-label="Home">
        <svg class="size-10 fill-sky-500 sm:size-8" viewBox="0 0 32 32">
            <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z" />
        </svg>
    </a>
    <twig:Navbar:Section>
        <twig:Navbar:Item href="/" current>
            Home
        </twig:Navbar:Item>
        <twig:Navbar:Item href="/events">Events</twig:Navbar:Item>
        <twig:Navbar:Item href="/orders">Orders</twig:Navbar:Item>
    </twig:Navbar:Section>
</twig:Navbar>
```

### With icon links

Use an icon as the only child of a `Navbar:Item` to create icon-only links:

```twig {"preview":true}
<twig:Navbar class="px-4">
    <a href="/" aria-label="Home">
        <svg class="size-10 fill-sky-500 sm:size-8" viewBox="0 0 32 32">
            <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z" />
        </svg>
    </a>
    <twig:Navbar:Spacer />
    <twig:Navbar:Section>
        <twig:Navbar:Item href="/search" aria-label="Search">
            <twig:ux:icon name="heroicons:magnifying-glass-20-solid" />
        </twig:Navbar:Item>
        <twig:Navbar:Item href="/inbox" aria-label="Inbox">
            <twig:ux:icon name="heroicons:inbox-20-solid" />
        </twig:Navbar:Item>
    </twig:Navbar:Section>
</twig:Navbar>
```

When using icon-only links, make sure to provide an `aria-label` for assistive technology.

The `Navbar:Item` component is designed to work best with 20×20 icons.

If you're using your own custom icons, make sure they include the `data-slot="icon"` attribute so they receive the correct styles.

### With space between items

Use the `Navbar:Spacer` component to add space between items in the navbar:

```twig {"preview":true}
<twig:Navbar class="px-4">
    <a href="/" aria-label="Home">
        <svg class="size-10 fill-sky-500 sm:size-8" viewBox="0 0 32 32">
            <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z" />
        </svg>
    </a>
    <twig:Navbar:Spacer />
    <twig:Navbar:Section>
        <twig:Navbar:Item href="/search" aria-label="Search">
            <twig:ux:icon name="heroicons:magnifying-glass-20-solid" />
        </twig:Navbar:Item>
        <twig:Navbar:Item href="/inbox" aria-label="Inbox">
            <twig:ux:icon name="heroicons:inbox-20-solid" />
        </twig:Navbar:Item>
    </twig:Navbar:Section>
</twig:Navbar>
```

### With divider

Use the `Navbar:Divider` component to add a dividing line between items in the navbar:

```twig {"preview":true}
<twig:Navbar class="px-4">
    <a href="/" aria-label="Home">
        <svg class="size-10 fill-sky-500 sm:size-8" viewBox="0 0 32 32">
            <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z" />
        </svg>
    </a>
    <twig:Navbar:Divider />
    <twig:Navbar:Section>
        <twig:Navbar:Item href="/">Home</twig:Navbar:Item>
        <twig:Navbar:Item href="/events">Events</twig:Navbar:Item>
        <twig:Navbar:Item href="/orders">Orders</twig:Navbar:Item>
    </twig:Navbar:Section>
</twig:Navbar>
```

### With dropdown

Use the `Dropdown` component to add a dropdown menu to a navbar by rendering the `Dropdown:Button` as a `Navbar:Item`:

```twig {"preview":true}
<div style="min-height: 235px; display: flex; align-items: start; width: 100%;">
    <twig:Navbar>
        <twig:Dropdown>
            <twig:Dropdown:Button as="Navbar:Item" aria-label="Account menu">
                <twig:Avatar src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                <twig:Navbar:Label>Tailwind Labs</twig:Navbar:Label>
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
        <twig:Navbar:Spacer />
        <twig:Navbar:Section>
            <twig:Navbar:Item href="/search" aria-label="Search">
                <twig:ux:icon name="heroicons:magnifying-glass-20-solid" />
            </twig:Navbar:Item>
            <twig:Navbar:Item href="/inbox" aria-label="Inbox">
                <twig:ux:icon name="heroicons:inbox-20-solid" />
            </twig:Navbar:Item>
        </twig:Navbar:Section>
    </twig:Navbar>
</div>
```

See the [Dropdown docs](/toolkit/kits/catalyst/components/dropdown) for more information on building dropdown menus.

### With avatar dropdown

Use the `Dropdown` component with an `Avatar` to add an avatar-only dropdown to a navbar:

```twig {"preview":true}
<div style="min-height: 275px; display: flex; align-items: start; width: 100%;">
    <twig:Navbar>
        <a href="/" aria-label="Home">
            <svg class="size-10 fill-sky-500 sm:size-8" viewBox="0 0 32 32">
                <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z"></path>
            </svg>
        </a>
        <twig:Navbar:Spacer />
        <twig:Dropdown>
            <twig:Dropdown:Button as="Navbar:Item" aria-label="Account menu">
                <twig:Avatar src="https://catalyst-demo.tailwindui.com/users/erica.jpg" square />
            </twig:Dropdown:Button>
            <twig:Dropdown:Menu class="min-w-64" anchor="bottom end">
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
    </twig:Navbar>
</div>
```

Make sure to provide an `aria-label` for assistive technology when using avatar-only dropdowns. See the [Dropdown docs](/toolkit/kits/catalyst/components/dropdown) for more information on how to build a dropdown menu.

### Hiding items on mobile

Use utility classes like `max-lg:hidden` to hide certain navbar items at different screen sizes:

```twig {"preview":true}
<twig:Navbar class="px-4">
    <a href="/" aria-label="Home">
        <svg class="size-10 fill-sky-500 sm:size-8" viewBox="0 0 32 32">
            <path d="M16.1455 9.14258C13.2019 9.14258 11.361 10.6666 10.6255 13.7139C11.7295 12.1906 13.017 11.6186 14.4895 12.0006C15.3301 12.2172 15.9295 12.8479 16.5943 13.5459C17.6763 14.6832 18.9295 15.9999 21.6661 15.9999C24.6103 15.9999 26.4505 14.4759 27.1861 11.4286C26.0828 12.9526 24.7945 13.5239 23.3221 13.1426C22.4828 12.9259 21.8821 12.2946 21.2173 11.5959C20.1353 10.4592 18.8821 9.14258 16.1455 9.14258ZM10.6255 15.9999C7.68125 15.9999 5.84104 17.5239 5.10547 20.5712C6.20882 19.0472 7.49704 18.4759 8.96947 18.8572C9.80882 19.0739 10.4095 19.7052 11.0743 20.4039C12.1563 21.5406 13.4095 22.8572 16.1455 22.8572C19.0903 22.8572 20.9305 21.3332 21.6661 18.2859C20.5621 19.8099 19.2739 20.3812 17.8021 19.9999C16.9621 19.7826 16.3621 19.1519 15.6973 18.4532C14.6147 17.3166 13.3628 15.9999 10.6255 15.9999Z" />
        </svg>
    </a>
    <twig:Navbar:Divider class="max-lg:hidden" />
    <twig:Navbar:Section class="max-lg:hidden">
        <twig:Navbar:Item href="/">Home</twig:Navbar:Item>
        <twig:Navbar:Item href="/events">Events</twig:Navbar:Item>
        <twig:Navbar:Item href="/orders">Orders</twig:Navbar:Item>
    </twig:Navbar:Section>
</twig:Navbar>
```

## API Reference

::: api-reference
