This project is a fork of the Google andonded Material Design 2 Web Components implementation.
The intent here is to enable the community to continue working on this setup.
If you are looking for a place to submit PRs for fixes and updates to the dead upstream, this is probably the place for it.

This fork intends to focus on Web Components that can be used cleanly without running NodeJS yourself, or Angular, etc.

This is a work in progress with intent to move away from depending on Google hosting for documentation so that it can all be maintained seperately by the community away from Google. Any mentions to Google hosted information ( including everything currently below ) should be considered to be potentially inaccurate as this projecct diverges from the original.

# Material Components for the web

Material Components for the web helps developers execute [Material Design](https://www.material.io).
Developed by a core team of engineers and UX designers at Google, these components enable a reliable development workflow to build beautiful and functional web projects.

Material Web strives to seamlessly incorporate into a wider range of usage contexts, from simple static websites to complex, JavaScript-heavy applications to hybrid client/server rendering systems. In short, whether you're already heavily invested in another framework or not, it should be easy to incorporate Material Components into your site in a lightweight, idiomatic fashion.

In addition to implementing the [Material Design guidelines](https://material.io/design), it provides more flexible theming customization, not only in terms of color, but also typography, shape, states, and more. It is also specifically [architected](docs/code/architecture.md) for adaptability to various [major web frameworks](docs/framework-wrappers.md).

## Important links

- [Getting Started Guide](docs/getting-started.md)
- [Demos](https://material-components.github.io/material-components-web-catalog) (external site)
- [Material Design Guidelines](https://material.io/design) (external site)
- [Supported browsers](docs/supported-browsers.md)
- [All Components](packages/)

## Quick start

### Using via CDN

```html
<!-- Required styles for Material Web -->
<link rel="stylesheet" href="https://unpkg.com/material-components-web@latest/dist/material-components-web.min.css">

<!-- Render textfield component -->
<label class="mdc-text-field mdc-text-field--filled">
  <span class="mdc-text-field__ripple"></span>
  <span class="mdc-floating-label" id="my-label">Label</span>
  <input type="text" class="mdc-text-field__input" aria-labelledby="my-label">
  <span class="mdc-line-ripple"></span>
</label>

<!-- Required Material Web JavaScript library -->
<script src="https://unpkg.com/material-components-web@latest/dist/material-components-web.min.js"></script>
<!-- Instantiate single textfield component rendered in the document -->
<script>
  mdc.textField.MDCTextField.attachTo(document.querySelector<HTMLElement>('.mdc-text-field'));
</script>
```

> Please see [quick start demo](https://codepen.io/abhiomkar/pen/gQWarJ) on codepen for full example.

### Using NPM

> This guide assumes you have webpack configured to compile Sass into CSS. To configure webpack, please see the full [getting started guide](docs/getting-started.md). You can also see the final code and result in the [Material Starter Kit](https://glitch.com/~material-starter-kit).

Install textfield node module to your project.

```
npm install @material/textfield
```

#### HTML

Sample usage of text field component. Please see [Textfield](packages/mdc-textfield) component page for more options.

```html
<label class="mdc-text-field mdc-text-field--filled">
  <span class="mdc-text-field__ripple"></span>
  <input type="text" class="mdc-text-field__input" aria-labelledby="my-label">
  <span class="mdc-floating-label" id="my-label">Label</span>
  <span class="mdc-line-ripple"></span>
</label>
```

#### CSS

Load styles required for text field component.

```scss
@use "@material/floating-label/mdc-floating-label";
@use "@material/line-ripple/mdc-line-ripple";
@use "@material/notched-outline/mdc-notched-outline";
@use "@material/textfield";

@include textfield.core-styles;

```

#### JavaScript

Import `MDCTextField` module to instantiate text field component.

```js
import {MDCTextField} from '@material/textfield';
const textField = new MDCTextField(document.querySelector<HTMLElement>('.mdc-text-field'));
```

This'll initialize text field component on a single `.mdc-text-field` element.

> Please see [quick start demo](https://glitch.com/edit/#!/remix/new-web) on glitch for full example.
