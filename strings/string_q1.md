## Write a function to check for a needle (string) in haystack (string)

```javascript
function findNeedleInHaystack(haystack, needle) {
  if(!haystack || !needle) return null;
  if(haystack === "" && needle === "") return 0;
  if(haystack === "" && needle !== "") return null;
  if(needle === "") return 0;

  //Solution 1
  /*
  var start = null;
  for(var i=0, j=0;i<haystack.length;i++){
    if(haystack.charAt(i) === needle.charAt(j)) {
      if(start === null) start = i;
      j++;
      if( j === needle.length) return start;
    }else {
      if(start || start === 0) {
        i = start + 1;
        j = 0;
        start = null;
      }
    }
  }
  return null;
  */
  // Solution 1 ends

  //Solution 2 
  for(var i = 0; i<haystack.length; i++){
    if(haystack.charAt(i) === needle.charAt(0)) {
      var h = i+1;
      var n = 1;
      while(n<needle.length) {
        if(haystack.charAt(h) === needle.charAt(n)) {
          h++;
          n++;
        } else break;
      }
      if(n === needle.length) return i;
    }
  }
  return null;
  //Solution 2 ends
}
```