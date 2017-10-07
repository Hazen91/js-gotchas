# js-gotchas
JavaScript Gotchas and Common Mistakes

1. `0` is falsy but `"0"` is true.
      ```js
      if (0) {
          console.log('yey.');
        } else {
          console.log('boom'); // this will be printed
        }


      if ("0") {
          console.log('yey.'); // this will be printed
        } else {
          console.log('boom'); 
        }
      ```
 Why?
 
 Because of coercion. Javascript sees a string and like a benovalent language that Javascript is, it tries to fix this itself. Now if condition needs a Boolean output, So compiler tries to convert a string into boolean operator.
 This is how toBoolean is supposed to work as per Sec 9.2 of ECMA-262
  > The result is false if the argument is the empty String (its length is zero); otherwise the result is true. 
  
  So Empty string will return false and rest everything will return true.  
 
 2. 
 ```js
 console.log(Number.MAX_VALUE > 0); // true
 
 console.log(Number.MIN_VALUE < 0); //false GOTCHA
 ``` 
 
People might assume that if MAX_VALUE is the greatest positive number, MIN_VALUE will contain the greatest negative number. Wrong. MIN_VALUE contains the smallest positive number. It should have been ideally named as MIN_POSITIVE_VALUE.
 
