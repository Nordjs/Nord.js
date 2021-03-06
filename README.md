# Nord.js
Nord.js brings together all the required Nord libraries to get the next generation backend framework up and running

## Getting Started

Create an `index.js` or `server.js` in your project root:
```js
const NordServer = require('nord').Server;
const server = new NordServer('./app'); // same as const server = new NordServer();
server.start();
```

Then create an `app` folder and within that folder a js file. That file should export an ES6 Class which extends Nord's Resource class with functions named after the HTTP Request methods (get, post, patch, etc) you want to cater for.

E.g. Create `app/cards.js`
```js
import {Resource} from 'nord';

export default class Cards extends Resource {
  get() {
    return this.res.json({text: 'woohhooo get!'});
  }
}
```

That's it. Happy coding.

*Note: This uses [Nord's simple router](https://github.com/Nordjs/nord-simple-router) and will support more complex app strutures with the upcoming advanced router.*
