Marko + Redux
==================================

This sample illustrates how to use Marko with Redux. Redux is a general-purpose application state container. This sample app illustrates how easy it is to wire up a Marko UI component with a Redux store.

# Installation and running

```bash
git clone https://github.com/marko-js-samples/marko-redux.git
cd marko-redux
npm install
npm start
```
# More details

The partial code snippet below shows how a a Marko UI component can be connected to a Redux store using the `store.subscribe()` method and the Marko `forceUpdate()` method:

```jsx
import store from '../store';

class {
    onMount() {
        store.subscribe(() => {
            this.forceUpdate();
        });
    }
}

<div>
    <counter(store.getState()) ... />
</div>
```

In the above example, the imported store module exports a Redux store created using the following code:

```js
var redux = require('redux');
var counter = require('./reducers');

module.exports = redux.createStore(counter);
```