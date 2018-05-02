## Old-School Solution: Manual Checking
```js
function foo(bar, options) {
  if (options === undefined) options = { bar: 'qux' };
  /* ... */
}
```

## A New Option: Default Params
```js
const foo = (
  bar,
  options = { baz: 'qux' }  // options defaults to { baz: 'qux' }
) => bar( options.baz === 'qux' ? 'ploni' : 'almoni' )

foo(console.log)            // ploni
foo(console.log, {})        // almoni

foo(console.log, null)      // ✋ Careful! null won't be substituted, only undefined.
                            // TypeError: Cannot read property 'baz' of null

foo(console.log, undefined) // ploni
```