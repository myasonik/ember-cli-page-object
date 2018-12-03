---
layout: page
title: Property
---

{% raw %}
### Methods


<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [property](#property)

### property

**Parameters**

-   `propertyName` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Name of the property to get
-   `selector` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** CSS selector of the element to check
-   `userOptions`   (optional, default `{}`)
-   `options` **[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Additional options
    -   `options.scope` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Nests provided scope within parent's scope
    -   `options.resetScope` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Override parent's scope
    -   `options.at` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Reduce the set of matched elements to the one at the specified index
    -   `options.multiple` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** If set, the function will return an array of values

**Examples**

```javascript
// <input type="checkbox" checked="checked">

import { create, property } from 'ember-cli-page-object';

const page = create({
  isChecked: property('checked', 'input')
});

assert.ok(page.isChecked);
```

```javascript
// <input type="checkbox" checked="checked">
// <input type="checkbox" checked="">

import { create, property } from 'ember-cli-page-object';

const page = create({
  inputsChecked: property('checked', 'input', { multiple: true })
});

assert.deepEqual(page.inputsChecked, [true, false]);
```

```javascript
// <div><input></div>
// <div class="scope"><input type="checkbox" checked="checked"></div>
// <div><input></div>

import { create, property } from 'ember-cli-page-object';

const page = create({
  isChecked: property('checked', 'input', { scope: '.scope' })
});

assert.ok(page.isChecked);
```

-   Throws **any** Will throw an error if no element matches selector
-   Throws **any** Will throw an error if multiple elements are matched by selector and multiple option is not set

Returns **Descriptor** 
{% endraw %}