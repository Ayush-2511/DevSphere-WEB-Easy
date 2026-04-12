# 🟢 Easy: Cart Data Cleaning (Debugging Fundamentals)

## Challenge Overview

In this challenge, you are tasked with fixing a JavaScript function that processes shopping cart data. The function `processCartData` is supposed to clean, validate, and calculate the total price of items in a cart. However, it contains several subtle bugs that lead to incorrect results, especially when dealing with edge cases and malformed input.

Your goal is to identify and fix these bugs to ensure the function works correctly for all valid inputs and gracefully handles invalid ones.

## Problem Description

You are given a list of `cartItems`, where each item is an object with the following structure:

```javascript
{
  id: string,       // Unique identifier
  name: string,     // Product name
  quantity: string, // Number of items (can be "0", "1", " 2 ", "NaN", etc.)
  price: string     // Price per item (can be "10.00", " 5 ", "invalid", etc.)
}
```

The `processCartData` function should perform the following operations:

1.  **Validation:**
    *   `id`: Must be a non-empty string.
    *   `name`: Must be a non-empty string after trimming any leading/trailing whitespace.
    *   `quantity`: Must be a positive integer (e.g., "1", "5", "10"). "0", negative numbers, non-numeric strings, or empty strings are invalid.
    *   `price`: Must be a positive number (e.g., "10.00", "5", "12.50"). "0", negative numbers, non-numeric strings, or empty strings are invalid.
2.  **Filtering:** Remove any `cartItems` that fail validation.
3.  **Type Conversion:** Convert `quantity` and `price` from strings to their appropriate number types for valid items.
4.  **Total Calculation:** Calculate the sum of (`quantity` \* `price`) for all valid and cleaned items.

## Expected Output

The `processCartData` function should return an object with two properties:

*   `cleanedCart`: An array of valid and cleaned cart item objects. Each item in this array should have `quantity` and `price` as numbers.
*   `totalPrice`: A number representing the sum of (`quantity` \* `price`) for all items in `cleanedCart`.

## How to Run

1.  Navigate to the `easy` directory:
    ```bash
    cd easy
    ```
2.  Run the tests:
    ```bash
    node test.js
    ```

The tests are designed to fail initially. Your task is to modify `easy.js` until all tests in `test.js` pass.
## Important Implementation Notes

1. Validate `id`
   * Always `trim` before validation

3. Validate `name`

4. Validate `quantity`
   
   * `quantity` must be integer, `price` can be decimal.

6. Validate `price`

   
## Hints

*   Pay close attention to **type conversions** (especially `Number()` behavior with different string inputs like `"  "`, `""`, `"NaN"`).
*   Consider the **order of your validation checks**. Does it make sense to convert a value to a number *before* checking if it's a valid string?
*   Review the **logic for calculating the total price**. Is it correctly multiplying quantity by price for each item?
*   Think about **edge cases**: empty strings, strings with only whitespace, "0" as a number, "NaN" as a number, negative numbers.

**Remember:** The code is intentionally broken. Your critical thinking and debugging skills are key!
