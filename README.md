# CSS Calc() Function Border Width Issue

This repository demonstrates a subtle but common error when using the `calc()` function in CSS to calculate element widths or heights. The issue arises when a border is applied to an element whose dimensions are calculated using `calc()`. The border's width is not automatically factored into the calculation, leading to unexpected results.

## Problem
The `calc()` function in CSS is powerful for dynamic calculations, but can be tricky when dealing with elements that also have borders. For example:

```css
.element {
  width: calc(100% - 20px);
  border: 10px solid black;
}
```

In this scenario, you might expect the element to occupy the full width of its parent container, minus 20px. However, the 10px border on both sides adds another 20px to the total width, causing the element to be rendered smaller than anticipated.

## Solution
To correct this, you must factor in the border width into your calculation.  Here's the corrected CSS:

```css
.element {
  width: calc(100% - 40px); /*Subtract double the border width*/
  border: 10px solid black; 
}
```

By subtracting double the border width (2 * 10px = 20px) from the calculation, we ensure that the element's total width (including the border) correctly matches the intended size.