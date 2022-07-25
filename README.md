# Scorpion HTML
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)

Scorpion-core support pack.

### Installation

```console
$ npm install @dbservices/scorpion-html
```

### Features, Usage, and Examples

- **Use tagged template literals as an HTML template engine.** For example:

  ```typescript
  import html from "@dbservices/scorpion-html";

  console.log(html`<p>${"Scorpion HTML"}</p>`); // => <p>Scorpion HTML</p>
  ```

- **Safe by default.** For example:

  ```typescript
  console.log(html`<p>${`<script>alert(1);</script>`}</p>`); // => <p>&#x3C;script&#x3E;alert(1);&#x3C;/script&#x3E;</p>
  ```

- **Unsafely interpolate trusted HTML with `$${...}`.** For example:

  ```typescript
  console.log(html`<p>$${`<span>Scorpion HTML</span>`}</p>`); // => <p><span>Scorpion HTML</span></p>
  ```

- **Join interpolated arrays.** For example:

  ```typescript
  console.log(html`<p>${["Scorpion", " ", "HTML"]}</p>`); // => <p>Scorpion HTML</p>
  ```

  Array interpolations are safe by default; if you wish to unsafely interpolate an array of trusted HTML use `$${[...]}`.