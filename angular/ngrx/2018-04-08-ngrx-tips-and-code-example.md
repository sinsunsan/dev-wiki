---
layout: post
title: Angular Ngrx tips and code examples
published: true
---

# Angular NGRX / Tips and code examples

You can learn ngrx by watching the lesson of Todd Motto here. It is the most complete and linear way to learn ngrx. You should do this before diving into more precise topics. [https://platform.ultimateangular.com/courses/ngrx-store-effects](https://platform.ultimateangular.com/courses/ngrx-store-effects)

## Dispatch several actions from the same effects

* [https://stackoverflow.com/questions/41701138/dispatch-multiple-actions-in-one-effect](https://stackoverflow.com/questions/41701138/dispatch-multiple-actions-in-one-effect)

## Use of ngrx/entity

[https://alligator.io/angular/ngrx-entity/](https://alligator.io/angular/ngrx-entity/)

## NGRX effects anti patterns

* [https://medium.com/@m3po22/stop-using-ngrx-effects-for-that-a6ccfe186399](https://medium.com/@m3po22/stop-using-ngrx-effects-for-that-a6ccfe186399)

  A quoted article on using effects 

* [https://bertrandg.github.io/ngrx-effects-complex-stream-with-nested-actions/](https://bertrandg.github.io/ngrx-effects-complex-stream-with-nested-actions/)
* [https://stackoverflow.com/questions/47554267/dispatch-multiple-action-from-one-effect](https://stackoverflow.com/questions/47554267/dispatch-multiple-action-from-one-effect)

## React to query success with a snackbar, confirm

Good tutorial that explain the refactoring of a component in ngrx [http://brianflove.com/2018/01/10/ngrx-refactor-module/](http://brianflove.com/2018/01/10/ngrx-refactor-module/)

And a tutorial to put snackbar management in store [http://brianflove.com/2018/03/16/ngrx-mat-snackbar/](http://brianflove.com/2018/03/16/ngrx-mat-snackbar/)

## Update ngrx version 5

Medium article that explain the changes of ngrx v5 [https://medium.com/ngrx/ngrx-5-and-schematics-2d8cc3906506](https://medium.com/ngrx/ngrx-5-and-schematics-2d8cc3906506)

## Using ngrx entity

* Medium article that explain the new feature of entity that allow to save some boiler plate code and standardize our components with entity [https://medium.com/ngrx/introducing-ngrx-entity-598176456e15](https://medium.com/ngrx/introducing-ngrx-entity-598176456e15)
* Not nice presentation but good example of using the adapter of ngrx entity [https://www.concretepage.com/angular-2/ngrx/ngrx-entity-example\#createEntityAdapter](https://www.concretepage.com/angular-2/ngrx/ngrx-entity-example#createEntityAdapter)
* Alligator blog tutorial on ngrx/entity [https://alligator.io/angular/ngrx-entity/](https://alligator.io/angular/ngrx-entity/)
* The doc of ngrx entity adapter on github [https://github.com/ngrx/platform/blob/master/docs/entity/adapter.md](https://github.com/ngrx/platform/blob/master/docs/entity/adapter.md)

## Hot and cold observable

[https://medium.com/@benlesh/hot-vs-cold-observables-f8094ed53339](https://medium.com/@benlesh/hot-vs-cold-observables-f8094ed53339)

## Testing ngrx

Todd motto is a reference but is a paid resource [https://ultimateangular.teachable.com/courses/ngrx-store-effects/lectures/3923989](https://ultimateangular.teachable.com/courses/ngrx-store-effects/lectures/3923989)

Other articles about testing ngrx

* Official ngrx testing doc

## Marble test

[https://github.com/ReactiveX/rxjs/blob/master/doc/marble-testing.md](https://github.com/ReactiveX/rxjs/blob/master/doc/marble-testing.md) [https://medium.com/@benlesh/hot-vs-cold-observables-f8094ed53339](https://medium.com/@benlesh/hot-vs-cold-observables-f8094ed53339) [https://github.com/ngrx/platform/blob/master/docs/store/testing.md](https://github.com/ngrx/platform/blob/master/docs/store/testing.md)

### Other uses of ngrx effects

[https://blog.angularindepth.com/start-using-ngrx-effects-for-this-e0b2bd9da165](https://blog.angularindepth.com/start-using-ngrx-effects-for-this-e0b2bd9da165)

### Filter selector in component instead of creating a new selector

```typescript
  getLines(): Observable<Lines[]> {
    return this.store
      .select(getProjecLines)
      .pipe(
        map(lines =>
          lines.filter(
            line => line.status === true,
          ),
        ),
      );
  }
```

### Listening to actions dispatch in component 

To prevent creating a boolean of the state of a completion in reducer. You can subscribe to the action dispatch the same way a reducer do.

```typescript
showWarning() {
    return this.appActions.pipe(
      ofType(actions.ADD_LINES_SUCCESS),
      map(
        (action: actions.AddLinesSuccess) =>
          action.payload,
      ),
      takeUntil(this.onDestroy$),
      tap(({ lines }) => {
```



