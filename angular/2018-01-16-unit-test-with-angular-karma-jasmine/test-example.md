# Test example

* Test a component emission

```javascript
describe('emitChange', () => {
    it('should emit the ipn changed', () => {
      spyOn(component.ipnChanged, 'emit');
      component.emitChange('p092354');
      expect(component.ipnChanged.emit).toHaveBeenCalledWith('p092354');
    });
  });
```



