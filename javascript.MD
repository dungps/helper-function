# Javascript Helper Functions
1. [add_query_args](#add_query_args)

[Back](https://github.com/oryc9x/helper-function/blob/master/README.md)

## add_query_args
```javascript
function add_query_args( args, uri ) {
   args = args || {};
   uri = uri || location.href;
   var fiestSeperator = uri.indexOf('?') == -1 ? '?' : '&';
   for(var key in args) {
      var pattern = new RegExp( '([?&])' + key + '=.*?(&|$)', 'i' );
      if (uri.match(pattern)) {
         return uri.replace(re, '$1' + key + '=' + args[key] + '$2' );
      } else {
        return uri + fiestSeperator + key + '=' + args[key];
      }
   }
}
```
