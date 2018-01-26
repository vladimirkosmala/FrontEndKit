# FrontEndKit JS

This JS Kit contains an MVC engine to produce efficient web applications.

It uses the last powerful concepts of hyperscript, diffing algorithms and reactive programming though observable object oriented models and functional views with a minimalistic API.

### Usage

Not published on NPM yet. Just copy the JS folder in your public folder.

```html
<script type="module">
import {Observable, h, mount} from 'FrontEndKit/js/index.js'

// The model
class Model extends Observable {
  constructor() {
    super();
    this.count = 0;
  }

  increment() {
    this.count++;
    this.notify();
  }

  decrement() {
    this.count--;
    this.notify();
  }
}

// The view
function view(model) {
  return h('center', [
    h('h1', 'Hello World'),
    h('p', `counter value: ${model.count}`),
    h('div', [
      h('button', {onclick: e => model.increment()}, '++'),
      h('button', {onclick: e => model.decrement()}, '--'),
    ])
  ]);
}

// The controller
const model = new Model();
mount(document.body, view, model);
</script>
```

### Compatibility

It was made with "recent browsers" in mind, Firefox could not work (ES6 modules). See the following links:

* https://caniuse.com/#feat=es6-module
* https://caniuse.com/#feat=template-literals
* https://caniuse.com/#feat=es6-class
* https://caniuse.com/#feat=arrow-functions
* https://caniuse.com/#feat=promises
* https://caniuse.com/#feat=async-functions

### Documentation

See the [docs folder](./docs).
