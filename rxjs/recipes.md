# Recipes

### How to get all successful request even if some are failing&#x20;

{% embed url="https://betterprogramming.pub/rxjs-error-handling-with-forkjoin-3d4027df70fc" %}

“If any input observable errors at some point, forkJoin will error as well and all other observables will be immediately unsubscribed.”

So the solution is to handle each error of each observable to remit an observable

```
const error$ = this.myService.getTodo(201)
  .pipe(
    catchError(err => of({isError: true, error: err})),
  );

```

\
