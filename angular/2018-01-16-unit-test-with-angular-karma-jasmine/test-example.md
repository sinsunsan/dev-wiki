# Unit test recipes \(Jasmine / Karma / Angular\)

#### Test a component emission

```javascript
describe('emitChange', () => {
  it('should emit the ipn changed', () => {
    spyOn(component.ipnChanged, 'emit');
    component.emitChange('p092354');
    expect(component.ipnChanged.emit).toHaveBeenCalledWith('p092354');
  });
});
```

#### Test a form initialization

```javascript
describe('ngOnInit', () => {
  it('should initialize the form with approval IPN', () => {
     const testIpn = '55352sss';
     component.approval = { ipn: testIPN};
     component.ngOnInit();
     expect(component.ipnForm.value.ipn).toBe(testIPN);
  });
});
```

#### Test the afterClosed function of a mat dialog 

{% embed url="https://stackoverflow.com/a/56679050/1453811" %}



