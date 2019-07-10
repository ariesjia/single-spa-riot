# single-spa-riot

Generic lifecycle hooks for Riot.js applications that are registered as [applications](https://github.com/CanopyTax/single-spa/blob/master/docs/applications.md#registered-applications) of [single-spa](https://github.com/CanopyTax/single-spa).

## Installation
```sh
npm install --save single-spa-riot
```

## Usage

```js
import * as Riot from 'riot';
import singleSpaRiot from 'single-spa-riot';
import App from './App.riot'

const riotLifecycles = singleSpaRiot({
  rootComponent: Riot.component(App),
  domElementGetter: () => document.getElementById('#app')
});

export const bootstrap = riotLifecycles.bootstrap;

export const mount = riotLifecycles.mount;

export const unmount = riotLifecycles.unmount;
```

## Options

All options are passed to single-spa-riot via the `opts` parameter when calling `singleSpaRiot(opts)`. The following options are available:

- `domElementGetter`: (required) the callback to get root component mount element.
- `rootComponent`: (optional and replaces `appOptions.loadRootComponent`) the root riot component.
- `loadRootComponent`: (optional and replaces `appOptions.rootComponent`) A promise that resolves with your root component. This is useful for lazy loading.
