# Javascript Helper Functions
1. [add_query_args](#add_query_args)

[Back](https://github.com/oryc9x/helper-function)

## add_query_args
Retrieves a modified URL query string.
```javascript
/**
 * @param object args
 * @param string uri
 * @return string
 */
function add_query_args( args, uri ) {
   args = args || {};
   uri = uri || location.href;
   var fiestSeperator = uri.indexOf('?') == -1 ? '?' : '&';
   for(var key in args) {
      var pattern = new RegExp( '([?&])' + key + '=.*?(&|$)', 'i' );
      if (uri.match(pattern)) {
         return uri.replace(pattern, '$1' + key + '=' + args[key] + '$2' );
      } else {
         return uri + fiestSeperator + key + '=' + args[key];
      }
   }
}
```
