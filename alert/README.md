# Alert

You'll still get emails from people who accidentally deleted their account, but at least you tried.

```twig {"preview":true}
<div style="min-height: 150px">
    <twig:Alert id="refund-payment">
        <twig:block name="button">
            <twig:Button type="button" {{ ...alert_button_attrs }}>
                Refund payment
            </twig:Button>
        </twig:block>
        <twig:Alert:Title>Are you sure you want to refund this payment?</twig:Alert:Title>
        <twig:Alert:Description>
            The refund will be reflected in the customer's bank account 2 to 3 business days after processing.
        </twig:Alert:Description>
        <twig:Alert:Actions>
            <twig:Button plain {{ ...alert_close_attrs }}>
                Cancel
            </twig:Button>
            <twig:Button {{ ...alert_close_attrs }}>Refund</twig:Button>
        </twig:Alert:Actions>
    </twig:Alert>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Alert`, `Alert:Title`, `Alert:Description`, and `Alert:Actions` components to build an alert:

```twig {"preview":true}
<div style="min-height: 150px">
    <twig:Alert id="refund-payment">
        <twig:block name="button">
            <twig:Button type="button" {{ ...alert_button_attrs }}>
                Refund payment
            </twig:Button>
        </twig:block>
        <twig:Alert:Title>Are you sure you want to refund this payment?</twig:Alert:Title>
        <twig:Alert:Description>
            The refund will be reflected in the customer's bank account 2 to 3 business days after processing.
        </twig:Alert:Description>
        <twig:Alert:Actions>
            <twig:Button plain {{ ...alert_close_attrs }}>
                Cancel
            </twig:Button>
            <twig:Button {{ ...alert_close_attrs }}>Refund</twig:Button>
        </twig:Alert:Actions>
    </twig:Alert>
</div>
```

### Alert width

Use the `size` prop on the `Alert` component to control the max-width of the alert dialog:

```twig {"preview":true}
<div style="min-height: 150px">
    <twig:Alert id="refund-payment" size="lg">
        <twig:block name="button">
            <twig:Button type="button" {{ ...alert_button_attrs }}>
                Refund payment
            </twig:Button>
        </twig:block>
        <twig:Alert:Title>Are you sure you want to refund this payment?</twig:Alert:Title>
        <twig:Alert:Description>
            The refund will be reflected in the customer's bank account 2 to 3 business days after processing.
        </twig:Alert:Description>
        <twig:Alert:Actions>
            <twig:Button plain {{ ...alert_close_attrs }}>
                Cancel
            </twig:Button>
            <twig:Button {{ ...alert_close_attrs }}>Refund</twig:Button>
        </twig:Alert:Actions>
    </twig:Alert>
</div>
```

Available size options include `xs`, `sm`, `md`, `lg`, `xl`, `2xl`, `3xl`, `4xl`, and `5xl`.

### With body

Add content to your alert using the `Alert:Body` component:

```twig {"preview":true}
<div style="min-height: 175px">
    <twig:Alert id="delete-repository" size="sm">
        <twig:block name="button">
            <twig:Button type="button" {{ ...alert_button_attrs }}>
                Delete repository
            </twig:Button>
        </twig:block>
        <twig:Alert:Title>Verification required</twig:Alert:Title>
        <twig:Alert:Description>To continue, please enter your password.</twig:Alert:Description>
        <twig:Alert:Body>
            <twig:Input name="password" type="password" aria-label="Password" placeholder="•••••••" autofocus />
        </twig:Alert:Body>
        <twig:Alert:Actions>
            <twig:Button plain {{ ...alert_close_attrs }}>
                Cancel
            </twig:Button>
            <twig:Button {{ ...alert_close_attrs }}>Continue</twig:Button>
        </twig:Alert:Actions>
    </twig:Alert>
</div>
```

### Auto-focusing elements

Add the `autofocus` attribute to any form control or button in the alert to automatically focus it when the alert opens:

```twig {"preview":true}
<div style="min-height: 175px">
    <twig:Alert id="delete-repository" size="sm">
        <twig:block name="button">
            <twig:Button type="button" {{ ...alert_button_attrs }}>
                Delete repository
            </twig:Button>
        </twig:block>
        <twig:Alert:Title>Verification required</twig:Alert:Title>
        <twig:Alert:Description>To continue, please enter your password.</twig:Alert:Description>
        <twig:Alert:Body>
            <twig:Input name="password" type="password" aria-label="Password" placeholder="•••••••" autofocus />
        </twig:Alert:Body>
        <twig:Alert:Actions>
            <twig:Button plain {{ ...alert_close_attrs }}>
                Cancel
            </twig:Button>
            <twig:Button {{ ...alert_close_attrs }}>Continue</twig:Button>
        </twig:Alert:Actions>
    </twig:Alert>
</div>
```

## API Reference

::: api-reference
