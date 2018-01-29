# Front-End Kit

Web applications made maintainable. Served hot with a CSS Bootstrap and a React-like template engine.

Compared to other frameworks:
* small API to learn
* small code base to audit
* future proof as much as possible

This comes from the main usage of this framework at CERN to build applications that must be running for 10 years with little or no maintenance. So the tools can't change like the rest of the web industry. No JSX, no webpack or any preprocessor but only the minimal packages completed by the large toolbox which is the web standards.

### Example

```html
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
}

// The view
function view(model) {
  return h('.fill-parent.flex-column.items-center.justify-center', [
    h('h1', 'Hello World'),
    h('p', `counter value: ${model.count}`),
    h('div', [
      h('button.btn', {onclick: e => model.increment()}, '++'),
    ])
  ]);
}

// The controller
mount(document.body, view, new Model());
```

### Reference

The reference is split in half: CSS and JS.

- [CSS for designing a web page or application](./css)
- [JS for a dynamic web application](./js)

### Tutorials

Create mini applications step by step with explanations.

- [Pasta Timer using CSS + JS](./docs/tutorials/pasta-timer.md)

### Guides

- [Async calls with fetch (ajax) and websocket](./docs/guides/fetch-websocket.md)
- [Scale the code of your application (architecture)](./docs/guides/scale-app.md)
- [From imperative to reactive programming (jQuery to React)](./docs/guides/reactive-programming.md)

### Compatibility

- Chrome 62 (end 2017)
- Firefox 57 (end 2017 - [must activate modules](./js/docs/firefox-modules.md))
- EDGE 16 (end 2017)
- Safari 10.1 (2017)
- iOS Safari (2017)
- Chrome Android 62
