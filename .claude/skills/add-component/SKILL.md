---
name: add-component
description: Add, update, or verify a Catalyst UI component (one at a time). Converts the JSX source into Twig templates, creates examples, manifest, and documentation for ux.symfony.com. Can also audit an existing component for correctness.
---

# Add, update, or verify a Catalyst UI component

This skill works on **one component at a time** for the Catalyst kit (Symfony UX Toolkit). It supports three modes:

- **Add**: Create a new component from scratch
- **Update**: Modify an existing component
- **Verify**: Audit an existing component against the JSX source and docs, report issues, and fix them

## Component list

Each component has a JSX source file and a Catalyst documentation URL:

| Component | JSX source | Doc URL |
|---|---|---|
| Alert | `components-tailwind-js/alert.jsx` | `https://catalyst.tailwindui.com/docs/alert` |
| Avatar | `components-tailwind-js/avatar.jsx` | `https://catalyst.tailwindui.com/docs/avatar` |
| Badge | `components-tailwind-js/badge.jsx` | `https://catalyst.tailwindui.com/docs/badge` |
| Button | `components-tailwind-js/button.jsx` | `https://catalyst.tailwindui.com/docs/button` |
| Checkbox | `components-tailwind-js/checkbox.jsx` | `https://catalyst.tailwindui.com/docs/checkbox` |
| Combobox | `components-tailwind-js/combobox.jsx` | `https://catalyst.tailwindui.com/docs/combobox` |
| Description list | `components-tailwind-js/description-list.jsx` | `https://catalyst.tailwindui.com/docs/description-list` |
| Dialog | `components-tailwind-js/dialog.jsx` | `https://catalyst.tailwindui.com/docs/dialog` |
| Divider | `components-tailwind-js/divider.jsx` | `https://catalyst.tailwindui.com/docs/divider` |
| Dropdown | `components-tailwind-js/dropdown.jsx` | `https://catalyst.tailwindui.com/docs/dropdown` |
| Fieldset | `components-tailwind-js/fieldset.jsx` | `https://catalyst.tailwindui.com/docs/fieldset` |
| Heading | `components-tailwind-js/heading.jsx` | `https://catalyst.tailwindui.com/docs/heading` |
| Input | `components-tailwind-js/input.jsx` | `https://catalyst.tailwindui.com/docs/input` |
| Listbox | `components-tailwind-js/listbox.jsx` | `https://catalyst.tailwindui.com/docs/listbox` |
| Navbar | `components-tailwind-js/navbar.jsx` | `https://catalyst.tailwindui.com/docs/navbar` |
| Pagination | `components-tailwind-js/pagination.jsx` | `https://catalyst.tailwindui.com/docs/pagination` |
| Radio button | `components-tailwind-js/radio.jsx` | `https://catalyst.tailwindui.com/docs/radio` |
| Select | `components-tailwind-js/select.jsx` | `https://catalyst.tailwindui.com/docs/select` |
| Sidebar | `components-tailwind-js/sidebar.jsx` | `https://catalyst.tailwindui.com/docs/sidebar` |
| Switch | `components-tailwind-js/switch.jsx` | `https://catalyst.tailwindui.com/docs/switch` |
| Table | `components-tailwind-js/table.jsx` | `https://catalyst.tailwindui.com/docs/table` |
| Text | `components-tailwind-js/text.jsx` | `https://catalyst.tailwindui.com/docs/text` |
| Textarea | `components-tailwind-js/textarea.jsx` | `https://catalyst.tailwindui.com/docs/textarea` |

## Detecting the mode

- **Add**: the component directory does not exist yet
- **Update**: the user explicitly asks to update or modify a component
- **Verify**: the user asks to verify, check, audit, or review a component — or simply names a component that already exists without asking for changes

## Workflow — Add / Update

When the user asks to add or update a component:

### Step 1 — Gather sources

1. Read the JSX source file from `components-tailwind-js/<component>.jsx`.
2. Fetch the Catalyst documentation page at the component's doc URL to understand usage examples, props, and variations.
3. If the component directory already exists, read all existing Twig templates, examples, manifest, and doc file to understand what's already in place (this is an update).

### Step 2 — Study existing patterns

Before writing anything, read at least 2-3 existing components similar in complexity to understand the conventions. Key reference files:

- **Simple component**: `divider/templates/components/Divider.html.twig`
- **Component with variants**: `button/templates/components/Button.html.twig`
- **Component with sub-components**: `alert/templates/components/Alert.html.twig` and `alert/templates/components/Alert/*.html.twig`
- **Component with provide/inject**: `table/templates/components/Table.html.twig` and `table/templates/components/Table/Row.html.twig`
- **Component with color maps**: `checkbox/templates/components/Checkbox.html.twig`
- **Component with html_cva()**: `divider/templates/components/Divider.html.twig`

### Step 3 — Convert JSX to Twig

Create or update the component directory with this structure:

```
<component>/
  manifest.json
  templates/components/<ComponentName>.html.twig
  templates/components/<ComponentName>/<SubComponent>.html.twig  (if needed)
  examples/Demo.html.twig
  examples/<Example Name>.html.twig  (one per usage example)
```

#### Conversion rules (JSX to Twig)

**Props and attributes:**
- React `function Component({ prop1, prop2 = default, className, ...props })` becomes `{%- props prop1, prop2 = default -%}` in Twig
- `className` is never a prop — it's handled via `attributes.render('class')`
- `...props` (rest/spread) is handled by `{{ attributes }}` on the root element
- React `children` becomes `{%- block content %}{% endblock -%}`

**Document props with `{# @prop ... #}` comments** above the `{% props %}` tag:
```twig
{# @prop color string The accent color. Defaults to `'dark/zinc'` #}
{# @prop outline boolean Use outline style. Defaults to `false` #}
{# @block content The button label #}
{%- props color = 'dark/zinc', outline = false -%}
```

**CSS class handling:**
- `clsx(className, 'static-classes')` becomes `class="{{ 'static-classes ' ~ attributes.render('class') }}"`
- When variants affect classes, either:
  - Use `html_cva()` for simple boolean variants (like Divider's `soft` prop)
  - Use Twig variables/maps for complex multi-value variants (like Button's `_colors` map)
- Conditional classes: `clsx(condition && 'classes')` becomes Twig ternary `(condition ? 'classes' : '')`

**Element attributes:**
- Use `{{ attributes }}` on the root element to forward extra attributes
- Use `{{ attributes.defaults({...}) }}` to set default attributes (like `data-slot`)
- Use `{{ attributes.only('name', 'value', ...) }}` to forward specific attributes to inner elements (like checkbox input)

**Headless UI components mapping:**
- `<Headless.Dialog>` → `<el-dialog>` (custom element from `@tailwindplus/elements`)
- `<Headless.DialogBackdrop>` → `<el-dialog-backdrop>`
- `<Headless.DialogPanel>` → `<el-dialog-panel>`
- `<Headless.Popover>` / menu patterns → `<el-dropdown>`, `<el-dropdown-panel>`
- Headless transition classes (`data-closed:`, `data-enter:`, `data-leave:`) may not apply — use the simpler native approach with `<dialog>` or custom elements

**Dynamic element tags:**
- `as={Link}` or conditional element: use `{%- set element = href ? 'a' : 'button' -%}` then `<{{ element }} ...>`

**Context sharing between parent/child:**
- React context / prop drilling → Twig `provide()` / `inject()`:
  ```twig
  {# Parent #}
  {%- do provide('table.bleed', bleed) -%}
  
  {# Child #}
  {%- set _table_bleed = inject('table.bleed', false) -%}
  ```

**Trigger/close patterns (Alert, Dialog):**
- Generate a unique ID: `{%- set _dialog_id = 'alert-' ~ random(0, 2147483647) -%}`
- Expose trigger/close attributes as Twig variables:
  ```twig
  {%- set alert_trigger_attrs = { type: 'button', command: 'show-modal', commandfor: _dialog_id, 'aria-haspopup': 'dialog' } -%}
  {%- set alert_close_attrs = { type: 'button', command: 'close', commandfor: _dialog_id } -%}
  ```
- Use blocks for trigger: `{%- block trigger %}{% endblock -%}`
- In examples, spread these attrs: `<twig:Button {{ ...alert_trigger_attrs }} outline>Open</twig:Button>`

### Step 4 — Create manifest.json

```json
{
    "$schema": "../../../schema-kit-recipe-v1.json",
    "type": "component",
    "name": "<ComponentName>",
    "description": "<Description from the Catalyst docs>",
    "copy-files": {
        "templates/": "templates/"
    },
    "dependencies": {
        "composer": ["twig/extra-bundle", "twig/html-extra:^3.12.0"]
    }
}
```

Add optional dependencies as needed:
- `"npm": ["@tailwindplus/elements"]` and `"importmap": ["@tailwindplus/elements"]` — when using custom elements (`<el-dialog>`, `<el-dropdown>`, etc.)
- `"recipe": ["button"]` — when the component uses other kit components (like Alert uses Button)

### Step 5 — Create examples

- **`Demo.html.twig`**: A minimal, self-contained demo showing the component in its most basic form. This is used as the preview on the component page. Keep it very simple.
- **Named examples** (e.g., `Basic example.html.twig`, `With icon.html.twig`): One per documentation section. Each shows a specific feature or variation.

Example naming convention — match the Catalyst docs section titles:
- "Basic example" → `Basic example.html.twig`
- "With description" → `With description.html.twig`
- "Disabled state" → `Disabled state.html.twig`

Examples use `<twig:ComponentName>` syntax:
```twig
<twig:Button color="indigo">Save changes</twig:Button>
```

Sub-components use colon notation:
```twig
<twig:Alert:Title>Are you sure?</twig:Alert:Title>
```

### Step 6 — Create documentation file

Create `ux.symfony.com/templates/toolkit/docs/catalyst/<component-slug>.md.twig`:

```twig
{% extends 'toolkit/docs/_base_component.md.twig' %}

{% block demo %}
{{ toolkit_code_demo(kit_id.value, component.name, {height: '<height>px'}) }}
{% endblock %}

{% block examples %}
### <Section title>

<Brief description of the feature or usage.>

{{ toolkit_code_example(kit_id.value, component.name, '<Example Name>', {height: '<height>px'}) }}

<Optional additional notes.>
{% endblock %}
```

- The `height` value should be estimated based on the component size (simple: `99px`, buttons/inputs: `134px`, dialogs: `130px`, tables: `300px`, etc.)
- The example name in `toolkit_code_example()` must exactly match the example filename (without `.html.twig`)

### Step 7 — Verify

After creating/updating the component:
1. Confirm all files are created with consistent naming
2. Verify the manifest.json dependencies are correct (check if the component uses other components or custom elements)
3. Ensure examples reference only components that exist in the kit
4. Check that prop names, default values, and CSS classes faithfully match the JSX source

## Workflow — Verify

When the user asks to verify or check a component:

### Step V1 — Gather all sources

1. Read the JSX source file from `components-tailwind-js/<component>.jsx`.
2. Fetch the Catalyst documentation page at the component's doc URL.
3. Read **all** existing Twig templates in `<component>/templates/components/`.
4. Read **all** existing examples in `<component>/examples/`.
5. Read the `<component>/manifest.json`.
6. Read the doc file at `ux.symfony.com/templates/toolkit/docs/catalyst/<component-slug>.md.twig`.

### Step V2 — Audit checklist

Compare the existing Twig implementation against the JSX source and documentation. Check each of these points and report findings:

#### Templates
- [ ] **All exported JSX components have a matching Twig template.** Each `export function ComponentName` in the JSX must have a corresponding `.html.twig` file. Report any missing sub-components.
- [ ] **Props match.** Every prop in the JSX function signature must exist in `{%- props ... -%}` with the same default value. Report missing props, wrong defaults, or extra props not in JSX.
- [ ] **Prop documentation.** Every prop must have a `{# @prop ... #}` comment. Blocks should have `{# @block ... #}`. Report any missing doc comments.
- [ ] **CSS classes are faithful.** Compare the Tailwind classes in the Twig output against the JSX `clsx()` calls. All classes must be present and identical. Report any missing, extra, or different classes. Pay special attention to:
  - Base classes
  - Variant/conditional classes
  - Dark mode classes (`dark:`)
  - Responsive classes (`sm:`, `lg:`)
  - State classes (`hover:`, `focus:`, `disabled:`, `active:`)
  - Forced colors classes (`forced-colors:`)
  - Custom properties (`[--var:value]`)
- [ ] **HTML structure matches.** The DOM nesting and element tags must match. Report structural differences (missing wrappers, wrong elements, etc.).
- [ ] **`data-slot` attributes** are present where needed.
- [ ] **Color maps are complete.** If the JSX has a color object/map, verify the Twig `_colors` map has all the same keys with the same values.
- [ ] **Headless UI mapping is correct.** Verify custom elements (`<el-dialog>`, `<el-dropdown>`, etc.) are used correctly.
- [ ] **provide/inject usage** matches React context patterns from the JSX.
- [ ] **`attributes.defaults()`** is used on the root element where appropriate.
- [ ] **`attributes.render('class')`** is used to allow consumer class overrides.
- [ ] **`attributes.only()`** is used for forwarding specific attributes to inner elements (inputs, etc.).

#### Manifest
- [ ] **Name matches** the component name.
- [ ] **Dependencies are correct**: `composer`, `npm`/`importmap` (if custom elements are used), `recipe` (if other kit components are used).
- [ ] **Description** is present and meaningful.

#### Examples
- [ ] **Demo.html.twig exists** and shows the simplest usage.
- [ ] **All doc sections have an example.** Compare example files against the sections in the Catalyst documentation page. Report missing examples.
- [ ] **Examples use correct syntax** (`<twig:ComponentName>`, spread attrs, etc.).
- [ ] **Examples only reference components that exist** in the kit.

#### Documentation
- [ ] **Doc file exists** at `ux.symfony.com/templates/toolkit/docs/catalyst/<slug>.md.twig`.
- [ ] **All examples are referenced** in the doc file via `toolkit_code_example()`.
- [ ] **Example names match** the filenames exactly (without `.html.twig`).
- [ ] **Heights are reasonable** for the component type.

### Step V3 — Report

Present findings as a structured report:

```
## Verification report: <ComponentName>

### Status: OK / Issues found

### Issues
1. [Templates] <description of the issue>
2. [Examples] <description of the issue>
...

### Summary
- Templates: X/Y checks passed
- Manifest: OK / Issues
- Examples: X/Y present
- Documentation: OK / Issues
```

### Step V4 — Fix (if requested)

If the user asks to fix the issues (or says "fix", "correct", "repair"), apply the corrections following the same conversion rules as the Add/Update workflow. Fix one file at a time and explain each change.

## Important notes

- **One component at a time.** The user specifies which component to work on.
- **Faithful conversion.** The Twig output must produce the same HTML structure and CSS classes as the JSX original. Do not simplify or remove classes.
- **Keep all Tailwind classes.** Even long utility strings must be preserved exactly as in the JSX source. Do not shorten or reformat them.
- **No `clsx` in Twig.** Replace all `clsx()` calls with Twig string concatenation (`~`) or `html_cva()`.
- **No React imports.** Remove all `import` statements. Twig templates are standalone.
- **`data-slot` attributes** must be preserved — they are used for styling child components from parents.
