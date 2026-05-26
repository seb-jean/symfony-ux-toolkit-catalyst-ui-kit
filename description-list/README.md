# Description List

For when you need to take the data from just one table row and somehow turn it into its own entire table to keep the page from feeling too empty.

```twig {"preview":true}
<div class="-my-6 w-full">
    <twig:DescriptionList>
        <twig:DescriptionList:Term>Customer</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>Michael Foster</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Event</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>Bear Hug: Live in Concert</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Amount</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>$150.00 USD</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Amount after exchange rate</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>US$150.00 &rarr; CA$199.79</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Fee</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>$4.79 USD</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Net</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>$1,955.00</twig:DescriptionList:Details>
    </twig:DescriptionList>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `DescriptionList`, `DescriptionList:Term`, and `DescriptionList:Details` components to build a description list:

```twig {"preview":true}
<div class="-my-6 w-full">
    <twig:DescriptionList>
        <twig:DescriptionList:Term>Customer</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>Leslie Alexander</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Email</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>leslie.alexander@example.com</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Access</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>Admin</twig:DescriptionList:Details>
    </twig:DescriptionList>
</div>
```

### With heading

Use the `Subheading` component to add a heading to the description list:

```twig {"preview":true}
<div class="-mt-2 -mb-6 w-full">
    <twig:Subheading>Order #1011</twig:Subheading>
    <twig:DescriptionList class="mt-4">
        <twig:DescriptionList:Term>Customer</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>Michael Foster</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Event</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>Bear Hug: Live in Concert</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Amount</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>$150.00 USD</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Amount after exchange rate</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>US$150.00 &rarr; CA$199.79</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Fee</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>$4.79 USD</twig:DescriptionList:Details>

        <twig:DescriptionList:Term>Net</twig:DescriptionList:Term>
        <twig:DescriptionList:Details>$1,955.00</twig:DescriptionList:Details>
    </twig:DescriptionList>
</div>
```

## API Reference

::: api-reference
