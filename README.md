Test cases for HTML layout dimensions that divide, round and sum to a value greater than the original dividend.

For example;

- An document has two columns.
- Both columns are 50% the width of the parent.
- The width of the container is 9 pixels.
- How wide should each column be?

Major web browsers handle this differently;

|| Browser || First || Second || `element.offsetWidth` || Avoids pixels in multiple elements ||
| Chrome | 5 | 4 | ✅ 5 and 4 respectively | Yes |
| Safari | 5 | 4 | 5, _even for the 4px column_ | Yes |
| Firefox | 4.5 | 4.5 | rounded to 5 | No |
| Edge | 4.5 | 4.5 | rounded to 5 | No |
 