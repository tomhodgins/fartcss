# fartcss

Inspired by TailwindCSS

`fart.css` is a small set of utility classes to help with responsive web design that leverage [EQCSS](https://github.com/eqcss/eqcss) to allow authors to set element-based breakpoints (using element queries and container queries).

The framework introduces a number of HTML attributes that can be used anywhere which are composed of three parts:

- min or max
- condition being queried
- breakpoint

This means when writing styles for a breakpoint you want to have happen when an element reaches a width of at least 500px, you could add the attribute `min-width-500=""` to your element. Any CSS properties set to the value of this attribute will apply when the breakpoint is true. In the following example, our div element would turn blue when it was wider than 500px:

```html
<div min-width-500="background: blue">fart.css demo</div>
```

This is because in our `fart.css` stylesheet there's the following EQCSS element query:

```css
@element [min-width-500] and (min-width: 500px) {
  $this { eval('getAttribute("min-width-500")') }
}
```

This means whenever the `(min-width: 500px)` breakpoint is true for any element in the page with a `[min-width-500]` attribute, the value of that attribute `eval('getAttribute("min-width-500")')` gets used as the content of a rule for `$this`, which refers to each individual element matching the breakpoint separately.

## Available Attributes

### Width-based

- `min-width-100`
- `min-width-200`
- `min-width-300`
- `min-width-400`
- `min-width-500`
- `min-width-600`
- `min-width-700`
- `min-width-800`
- `min-width-900`
- `min-width-1000`
- `max-width-100`
- `max-width-200`
- `max-width-300`
- `max-width-400`
- `max-width-500`
- `max-width-600`
- `max-width-700`
- `max-width-800`
- `max-width-900`
- `max-width-1000`

### Height-based

- `min-height-100`
- `min-height-200`
- `min-height-300`
- `min-height-400`
- `min-height-500`
- `min-height-600`
- `min-height-700`
- `min-height-800`
- `min-height-900`
- `min-height-1000`
- `max-height-100`
- `max-height-200`
- `max-height-300`
- `max-height-400`
- `max-height-500`
- `max-height-600`
- `max-height-700`
- `max-height-800`
- `max-height-900`
- `max-height-1000`

### Children-based

- `min-children-1`
- `min-children-2`
- `min-children-3`
- `min-children-4`
- `min-children-5`
- `min-children-6`
- `min-children-7`
- `min-children-8`
- `min-children-9`
- `min-children-10`
- `max-children-1`
- `max-children-2`
- `max-children-3`
- `max-children-4`
- `max-children-5`
- `max-children-6`
- `max-children-7`
- `max-children-8`
- `max-children-9`
- `max-children-10`

## Links

- Demo: https://tomhodgins.github.io/fartcss/demo.html
- Website: https://tomhodgins.github.io/fartcss