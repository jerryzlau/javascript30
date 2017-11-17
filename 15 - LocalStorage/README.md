#Useful commands 

## reset html form inputs
```javascript
  // html form has a reset method. form.reset() will reset the value to empty string
  form.reset();
```

## Local Storage 
```javascript
// usage 
localStorage.setItem('key', values);

// value type: value has to be a string 
value = JSON.stringify(value); 

// read value back from localstorage as json
value = JSON.parse(localStorage.getItem('key'));