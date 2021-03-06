# Angular Wormhole

This component allows rendering all of its content to be rendered elsewhere on
the page.

## Why?

Sometimes a dialog or tooltip has to be rendered outside of an element, as CSS
stacking contexts may interfere with positioning.

## Installation

```bash
$ yarn add angular-wormhole
```

Import `AngularWormholeModule` in your app:

```typescript
import { NgModule } from '@angular/core';
import { AngularWormholeModule } from 'angular-wormhole';

@NgModule({
  imports: [
    AngularWormholeModule
  ]
})
export class AppModule {}
```

### Example usage

index.html
```html
<body>
  <my-angular-app></my-angular-app>
  <div id="wormhole-target"></div>
</body>
```

In a component template:

```html
<ng-wormhole to="#wormhole-target">
  <my-popover>...</my-popover>
</ng-wormhole>
```

The `<my-popover>` component will then be rendered in the `#wormhole-target`
element, it will also automatically cleaned up once your component will be
destroyed.

### Attributes

*to: selector*
Which element to append to.

```html
<ng-wormhole to="#wormhole-target">
  <my-popover>...</my-popover>
</ng-wormhole>
```

### Inputs

*to: selector*
Which element to append to.

```html
<ng-wormhole [to]="'#wormhole-target'">
  <my-popover>...</my-popover>
</ng-wormhole>
```

*renderInPlace: boolean = false*
Should the component render its children in place?

```html
<ng-wormhole to="#wormhole-target" [renderInPlace]="true">
  <my-popover>...</my-popover>
</ng-wormhole>
```

# Credits

This component is heavily inspired by
[ember-wormhole](https://github.com/yapplabs/ember-wormhole).
Contributions from @stefanpenner, @krisselden, @chrislopresto, @lukemelia,
@raycohen and others.
