# When does 5 + 5 = 9?

Test cases for HTML layout dimensions that divide, round and sum to a value different to the original dividend.

### For example

- A container has two columns.
- Both columns are 50% the width of the parent.
- The width of the container is 9 pixels.
- How wide should each column be?

### Major web browsers handle this differently

Browser | First | Second | `element.offsetWidth` | Aliases †
------- | ----- | ------ | --------------------- | -------
Chrome | 5 | 4 | 5 and 4 respectively | No
Safari | 5 | 4 | 5, _even for the 4px column_ | No
Firefox | 4.5 | 4.5 | rounded to 5 | Yes
Edge | 4.5 | 4.5 | rounded to 5 | Yes
 
† Allows element boundaries to be mid-pixel, causing that pixel to be aliased based on the two elements that it straddles.

## Test cases

- Halves; 9px ÷ 2
    - [Column width](https://bevanr.github.io/5-and-5-is-9/width.html)
    - [Row height](https://bevanr.github.io/5-and-5-is-9/height.html)
- Thirds; 10px ÷ 3
    - [Row height](https://bevanr.github.io/5-and-5-is-9/thirds/height.html)
    - [Column width](https://bevanr.github.io/5-and-5-is-9/thirds/width.html)

## Workaround solution

### Width

- Round the left edge.
- Round the right edge.
- The width is the difference.

### Height

- Round the top edge.
- Round the bottom edge.
- The height is the difference.

### Example

```javascript
getDimensions(element: HTMLElement) {
    const {round} = Math
    const rect = element.getBoundingClientRect()
    return {
        height: round(rect.bottom) - round(rect.top),
        width: round(rect.right) - round(rect.left),
    }
}
```

