# Marionette Js Documentation

## Contents

- driver.js
- initializer.js
- router.js
- view.js

## driver.js

Ensure that the driver has a link to the initializer.

## initializer.js

Just loads the router.

```
import MyApp from 'myapp/router';


export default function(options) {
  this.router = new MyApp(options);
}
```

## router.js

In the router, you need to do something like this:

```
import Marionette from 'backbone.marionette';

import {MyLayout} from 'myapp/views/index';
import {MyList} from 'myapp/collections/member';


const Controller = Marionette.Object.extend({
  initialize: function() {
    var links = this.getOption('links');
    const regionManager = this.getOption('regionManager');

    regionManager.addRegions({
      main: '#my-app-hook'
    });

    var collection = new MyList([], {
      urlBase: links.myapp,
      state: {
        pageSize: 10
      }
    });

    this.options.layout = new SponsorLayout({
      collection: collection,
      links: links
    });

    regionManager.get('main').show(this.options.layout);
  }
});

export const MyApp = Marionette.AppRouter.extend({
  initialize: function() {
    this.controller = new Controller(this.options);
  }
});


export default Router;
```
