# Testing services with httpMock

{% embed url="https://2019.ng-conf.org/2019/angulars-httpclient-testing-depth/" %}

### How to debug expectOne 

`Error: Expected one matching request for criteria "Match by function: ", found none.`

Not very explicit it fact the expected  url is not matching exactly the mocked  url. 

A way to debug that is to use the form with a custom function that allows to do the matching by hand 

```javascript
const req = httpMock.expectOne((request: any) => {
   // Here we test urlWithParams and not url
   return request.urlWithParams === expectedUrl + addedParams;
});
```





