# StackedLayout

You don't have enough features to fill a sidebar anyway, plus they aren't going to be cool forever.

```twig {"preview":true}
{% set nav_items = [
    {label: 'Home', url: '/'},
    {label: 'Events', url: '/events'},
    {label: 'Orders', url: '/orders'},
    {label: 'Broadcasts', url: '/broadcasts'},
    {label: 'Settings', url: '/settings'},
] %}

<twig:StackedLayout>
    <twig:block name="navbar">
        <twig:Navbar>
            <twig:Dropdown>
                <twig:Dropdown:Button as="Navbar:Item" class="max-lg:hidden">
                    <twig:Avatar src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                    <twig:Navbar:Label>Tailwind Labs</twig:Navbar:Label>
                    <twig:ux:icon name="heroicons:chevron-down-16-solid" />
                </twig:Dropdown:Button>
                <twig:Dropdown:Menu class="min-w-80 lg:min-w-64" anchor="bottom start">
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
                {% for item in nav_items %}
                    <twig:Navbar:Item href="{{ item.url }}">{{ item.label }}</twig:Navbar:Item>
                {% endfor %}
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
            </twig:Navbar:Section>
        </twig:Navbar>
    </twig:block>
    <twig:block name="sidebar">
        <twig:Sidebar>
            <twig:Sidebar:Header>
                <twig:Dropdown>
                    <twig:Dropdown:Button as="Sidebar:Item" class="lg:mb-2.5">
                        <twig:Avatar src="https://catalyst.tailwindui.com/tailwind-logo.svg" />
                        <twig:Sidebar:Label>Tailwind Labs</twig:Sidebar:Label>
                        <twig:ux:icon name="heroicons:chevron-down-16-solid" />
                    </twig:Dropdown:Button>
                    <twig:Dropdown:Menu class="min-w-80 lg:min-w-64" anchor="bottom start">
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
                    {% for item in nav_items %}
                        <twig:Sidebar:Item href="{{ item.url }}">{{ item.label }}</twig:Sidebar:Item>
                    {% endfor %}
                </twig:Sidebar:Section>
            </twig:Sidebar:Body>
        </twig:Sidebar>
    </twig:block>
    {# The page content #}
</twig:StackedLayout>
```

## Installation

::: installation
