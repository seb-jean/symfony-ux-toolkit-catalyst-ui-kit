# Fieldset

Something has to hold all these form controls together.

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Shipping details</twig:Fieldset:Legend>
        <twig:Text>Without this your odds of getting your order are low.</twig:Text>
        <twig:Fieldset:FieldGroup>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="street_address">Street address</twig:Fieldset:Label>
                <twig:Input id="street_address" name="street_address" />
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="country">Country</twig:Fieldset:Label>
                <twig:Select id="country" name="country">
                    <option>Canada</option>
                    <option>Mexico</option>
                    <option>United States</option>
                </twig:Select>
                <twig:Fieldset:Description>We currently only ship to North America.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="notes">Delivery notes</twig:Fieldset:Label>
                <twig:Textarea id="notes" name="notes" />
                <twig:Fieldset:Description>If you have a tiger, we'd like to know about it.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
        </twig:Fieldset:FieldGroup>
    </twig:Fieldset>
</div>
```

## Installation

::: installation

## Examples

### Basic example

Use the `Fieldset`, `Fieldset:Legend`, `Text`, and `Fieldset:FieldGroup` components to group a subset of form controls together:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Shipping details</twig:Fieldset:Legend>
        <twig:Text>Without this your odds of getting your order are low.</twig:Text>
        <twig:Fieldset:FieldGroup>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="street_address">Street address</twig:Fieldset:Label>
                <twig:Input id="street_address" name="street_address" />
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="country">Country</twig:Fieldset:Label>
                <twig:Select id="country" name="country">
                    <option>Canada</option>
                    <option>Mexico</option>
                    <option>United States</option>
                </twig:Select>
                <twig:Fieldset:Description>We currently only ship to North America.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="notes">Delivery notes</twig:Fieldset:Label>
                <twig:Textarea id="notes" name="notes" />
                <twig:Fieldset:Description>If you have a tiger, we'd like to know about it.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
        </twig:Fieldset:FieldGroup>
    </twig:Fieldset>
</div>
```

### Without legend

Use a `Fieldset` with `aria-label` to group a set of form controls together without a `Fieldset:Legend`:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset aria-label="Shipping details">
        <twig:Fieldset:FieldGroup>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="street_address">Street address</twig:Fieldset:Label>
                <twig:Input id="street_address" name="street_address" />
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="country">Country</twig:Fieldset:Label>
                <twig:Select id="country" name="country">
                    <option>Canada</option>
                    <option>Mexico</option>
                    <option>United States</option>
                </twig:Select>
                <twig:Fieldset:Description>We currently only ship to North America.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="notes">Delivery notes</twig:Fieldset:Label>
                <twig:Textarea id="notes" name="notes" />
                <twig:Fieldset:Description>If you have a tiger, we'd like to know about it.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
        </twig:Fieldset:FieldGroup>
    </twig:Fieldset>
</div>
```

### Without role

Use the `Fieldset:FieldGroup` component on its own to use it solely for layout, without adding `role="group"` and announcing it to assistive technology like a traditional fieldset:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset:FieldGroup>
        <twig:Fieldset:Field>
            <twig:Fieldset:Label>Street address</twig:Fieldset:Label>
            <twig:Input name="street_address" />
        </twig:Fieldset:Field>
        <twig:Fieldset:Field>
            <twig:Fieldset:Label>Country</twig:Fieldset:Label>
            <twig:Select name="country">
                <option>Canada</option>
                <option>Mexico</option>
                <option>United States</option>
            </twig:Select>
            <twig:Fieldset:Description>We currently only ship to North America.</twig:Fieldset:Description>
        </twig:Fieldset:Field>
        <twig:Fieldset:Field>
            <twig:Fieldset:Label>Delivery notes</twig:Fieldset:Label>
            <twig:Textarea name="notes" />
            <twig:Fieldset:Description>If you have a tiger, we'd like to know about it.</twig:Fieldset:Description>
        </twig:Fieldset:Field>
    </twig:Fieldset:FieldGroup>
</div>
```

### With grid layout

For more complex layouts like grids, use wrapper elements to create nested form control groups and style them yourself with utility classes:

```twig {"preview":true}
<div class="w-full max-w-md h-fit">
    <twig:Fieldset>
        <twig:Fieldset:Legend>Shipping details</twig:Fieldset:Legend>
        <twig:Text>Without this your odds of getting your order are low.</twig:Text>
        <twig:Fieldset:FieldGroup>
            <div class="grid grid-cols-1 gap-8 sm:grid-cols-2 sm:gap-4">
                <twig:Fieldset:Field>
                    <twig:Fieldset:Label for="first_name">First name</twig:Fieldset:Label>
                    <twig:Input id="first_name" name="first_name" />
                </twig:Fieldset:Field>
                <twig:Fieldset:Field>
                    <twig:Fieldset:Label for="last_name">Last name</twig:Fieldset:Label>
                    <twig:Input id="last_name" name="last_name" />
                </twig:Fieldset:Field>
            </div>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="street_address">Street address</twig:Fieldset:Label>
                <twig:Input id="street_address" name="street_address" />
            </twig:Fieldset:Field>
            <div class="grid grid-cols-1 gap-8 sm:grid-cols-3 sm:gap-4">
                <twig:Fieldset:Field class="sm:col-span-2">
                    <twig:Fieldset:Label for="country">Country</twig:Fieldset:Label>
                    <twig:Select id="country" name="country">
                        <option>Canada</option>
                        <option>Mexico</option>
                        <option>United States</option>
                    </twig:Select>
                </twig:Fieldset:Field>
                <twig:Fieldset:Field>
                    <twig:Fieldset:Label for="postal_code">Postal code</twig:Fieldset:Label>
                    <twig:Input id="postal_code" name="postal_code" />
                </twig:Fieldset:Field>
            </div>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="notes">Delivery notes</twig:Fieldset:Label>
                <twig:Textarea id="notes" name="notes" />
                <twig:Fieldset:Description>If you have a tiger, we'd like to know about it.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
        </twig:Fieldset:FieldGroup>
    </twig:Fieldset>
</div>
```

### Disabled state

Add the `disabled` prop to a `Fieldset` component to disable the entire fieldset:

```twig {"preview":true}
<div class="w-full max-w-sm h-fit">
    <twig:Fieldset disabled>
        <twig:Fieldset:Legend>Shipping details</twig:Fieldset:Legend>
        <twig:Text>Without this your odds of getting your order are low.</twig:Text>
        <twig:Fieldset:FieldGroup>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="street_address">Street address</twig:Fieldset:Label>
                <twig:Input id="street_address" name="street_address" />
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="country">Country</twig:Fieldset:Label>
                <twig:Select id="country" name="country">
                    <option>Canada</option>
                    <option>Mexico</option>
                    <option>United States</option>
                </twig:Select>
                <twig:Fieldset:Description>We currently only ship to North America.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
            <twig:Fieldset:Field>
                <twig:Fieldset:Label for="notes">Delivery notes</twig:Fieldset:Label>
                <twig:Textarea id="notes" name="notes" />
                <twig:Fieldset:Description>If you have a tiger, we'd like to know about it.</twig:Fieldset:Description>
            </twig:Fieldset:Field>
        </twig:Fieldset:FieldGroup>
    </twig:Fieldset>
</div>
```

## API Reference

::: api-reference
