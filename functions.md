## JSONata Function Library
The following is a proposed function library for use within JSONata expressions.
This is work in progress. Some of these functions have been implemented, but mostly not.


#### String functions
- `$string(arg)`

   Casts the `arg` parameter to a string
   
- `$length(str)`

   Returns the number of characters in the string `str`
   
- `$substring(str, start[, length])`

Returns a string containing the characters in the first parameter `str`
starting at position `start` (zero-offset).  If `length` is specified, then
the substring will contain maximum `length` characters.  If `start` is negative
then it indicates the number of characters from the end of `str`.
See [substr](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr) for full definition.

  - `$substringBefore(str, chars)`

   Returns the substring before the first occurrence of the character sequence `chars` in `str`.
   If `str` does not contain `chars`, then it returns `str`.


  - `$substringAfter(str, chars)`

   Returns the substring after the first occurrence of the character sequence `chars` in `str`.
   If `str` does not contain `chars`, then it returns `str`.


  - `$uppercase(str)`

  Returns a string with all the characters of `str` converted to uppercase.


  - `$lowercase(str)`

  Returns a string with all the characters of `str` converted to lowercase.


- `$split(str, separator)`

- `$join(array[, separator])`

- `$format(pattern, ...)`

  [printf style formatting](https://en.wikipedia.org/wiki/Printf_format_string#Format_placeholder_specification). Other formatting schemes are available.

#### Numerical functions

- `$number(arg)`

  Cast the value of `arg` to a number

- `$sum(array)`
- `$abs(number)`
- `$max(array)`
- `$min(array)`
- `$round(number)`

  Rounds up to the nearest integer

- `$roundHalfToEven(number)`

  [Round half to even](https://en.wikipedia.org/wiki/Rounding#Round_half_to_even) Commonly used in financial calculations.

- `$average(array)`
- `$power(base, exponent)`

#### Boolean functions

- `$boolean(arg)`

  Casts the argument to a Boolean

- `$not(arg)`

  Returns Boolean NOT on the argument.  `arg` is first cast to a boolean

#### Date/Time functions

#### Array functions

- `$count(array)`

  Returns the number of items in the array
  
- `$append(array, array)`

  Appends two arrays
  
- `$flatten(array)`

  Flattens nested array into flat array
  
- `$range(start, end, increment)`

  Generates an array of numbers starting with `start`, not exceeding `end`, in increments of `increment` (defaults to 1)

#### Object functions

- `$keys(object)`

  Returns an array containing the keys in the object

- `$lookup(object, key)`

  Returns the value assosciated with `key` in `object`
  
- `$merge(object, object)`
  
  Returns an object containing the union of the two `object` parameters.  If an entry in the second object 
  has the same key as an entry in the first, then the value will be overridden by the second.