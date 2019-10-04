# NGRX unit test

### What to test 

* Actions 
* Effects 
* Reducer 
* Selector

### How to 

* [https://christianlydemann.com/the-complete-guide-to-ngrx-testing/](https://christianlydemann.com/the-complete-guide-to-ngrx-testing/)



### Marbles test 

* [https://medium.com/@bencabanes/marble-testing-observable-introduction-1f5ad39231c](https://medium.com/@bencabanes/marble-testing-observable-introduction-1f5ad39231c)
* [https://github.com/jisaacks/RxJS/blob/master/doc/writing-marble-tests.md](https://github.com/jisaacks/RxJS/blob/master/doc/writing-marble-tests.md)

### Tricks 

#### Testing an effect not returning action 

* [https://stackoverflow.com/questions/53358677/ngrx-effects-testing-with-dispatch-false](https://stackoverflow.com/questions/53358677/ngrx-effects-testing-with-dispatch-false)
* [https://stackoverflow.com/questions/48137205/ngrx-effects-testing-an-effect-returns-empty/53188160\#53188160](https://stackoverflow.com/questions/48137205/ngrx-effects-testing-an-effect-returns-empty/53188160#53188160)
* Successful for me more simple technic [https://stackoverflow.com/questions/48318095/how-to-unit-test-this-effect-with-dispatch-false](https://stackoverflow.com/questions/48318095/how-to-unit-test-this-effect-with-dispatch-false)

the code

```typescript
@Injectable()
export class NotificationEffects {
  @Effect({dispatch: false})
  notificationShow$ = this.actions$
    .ofType(notificationAction.NOTIFICATION_SHOW)
    .do((action: notificationAction.NotificationShowAction) => {
      this.notificationService.info(action.payload.config);
    });

  constructor(private actions$: Actions, private notificationService: NotificationService) {}
}
```

The test

```javascript
describe('notificationShow$', () => {
  let effects: NotificationEffects;
  let service: any;
  let actions$: Observable<Action>;
  const payload = {test: 123};

  beforeEach( () => {
    TestBed.configureTestingModule( {
      providers: [
        NotificationEffects,
        provideMockActions( () => actions$ ),
        {
          provide: NotificationService,
          useValue: jasmine.createSpyObj('NotificationService', ['info'])
        }
      ]
    } );

    effects = TestBed.get(NotificationEffects);
    service = TestBed.get(NotificationService);
  });

  it('should call a notification service method info with a payload', () => {
    actions$ = cold('a', { a: new notificationAction.NotificationShowAction(payload) });
    effects.notificationShow$.subscribe(() => {
      expect(service.info).toHaveBeenCalledWith(payload);
    });
  });
});
```

