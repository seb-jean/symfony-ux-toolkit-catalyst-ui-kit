# SidebarLayout

First sidebars are cool, then they're dated, then they're cool again — I think they're cool right now though so we built you this one.

```twig {"preview":true}
<twig:SidebarLayout>
    <twig:block name="navbar">
        <twig:Navbar>
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
                <twig:Sidebar:Section class="max-lg:hidden">
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
                    <twig:Sidebar:Item href="/settings">
                        <twig:ux:icon name="heroicons:cog-6-tooth-20-solid" />
                        <twig:Sidebar:Label>Settings</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/broadcasts">
                        <twig:ux:icon name="heroicons:megaphone-20-solid" />
                        <twig:Sidebar:Label>Broadcasts</twig:Sidebar:Label>
                    </twig:Sidebar:Item>
                </twig:Sidebar:Section>
                <twig:Sidebar:Section class="max-lg:hidden">
                    <twig:Sidebar:Heading>Upcoming Events</twig:Sidebar:Heading>
                    <twig:Sidebar:Item href="/events/1">Bear Hug: Live in Concert</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events/2">Viking People</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events/3">Six Fingers — DJ Set</twig:Sidebar:Item>
                    <twig:Sidebar:Item href="/events/4">We All Look The Same</twig:Sidebar:Item>
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
            <twig:Sidebar:Footer class="max-lg:hidden">
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
    </twig:block>
    {# The page content #}
</twig:SidebarLayout>
```

## Installation

::: installation
