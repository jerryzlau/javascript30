# css_variable

Day 3 Javascript 30 update css variables with javascript exercise

## Notes:
* How to set variables in css root
  ```CSS
  /* declare variables like this */
    :root{
      --base: #ffc600;
    }

  /* apply it by calling it like this */
    img{
      padding: var(--spacing);
    }
  ```
* How to set css variables in javascript
  ```JavaScript
  // note that both parameters have to be strings
  document.documentElement.style.setProperty([variable], [value]);
  ```
