Test cases for HTML layout dimensions that divide, round and sum to a value greater than the original dividend.

For example;

- An document has two columns.
- Both columns are 50% the width of the parent.
- The width of the container is 9 pixels.
- How wide should each column be?

Major web browsers handle this differently;

Browser | First | Second | `element.offsetWidth` | Aliases †
------- | ----- | ------ | --------------------- | -------
Chrome | 5 | 4 | ✅ 5 and 4 respectively | No
Safari | 5 | 4 | 5, _even for the 4px column_ | No
Firefox | 4.5 | 4.5 | rounded to 5 | Yes
Edge | 4.5 | 4.5 | rounded to 5 | Yes
 
† Allows element boundaries to be mid-pixel, causing that pixel to be aliased based on the two elements that it straddles.
