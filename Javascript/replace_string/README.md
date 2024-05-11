# Custom String Replacement Function Documentation

## Overview
This custom function aims to replicate the functionality of the built-in JavaScript `String.replace()` method, with the enhancement of handling multiple occurrences of the substring within the string. It replaces all occurrences of a specified substring within a string with another substring.

## Function Signature
```javascript
customReplace(actualString, subString, repString)
```
## Parameters
- `actualString` (string): The original string in which replacements will be performed.
- `subString` (string): The substring to be replaced within the `actualString`.
- `repString` (string): The string that replaces occurrences of `subString` within `actualString`.

## Return Value
- `newString` (string): The modified string with all replacements applied.

## Algorithm
1. **Initialize Variables**: 
   - `newString`: A new string to hold the result of the replacement.
   - `upCount`: Tracks the number of consecutive matching characters between `subString` and the `actualString`.
   - `indexCount`: Stores the index of the last character of the full match between `subString` and `actualString`.
   - `startIndex`: The starting index of the matched `subString` in `actualString`.
   - `endIndex`: The index following the last character of the matched `subString`.
   - `checkDiff`: Calculates the difference in length between `repString` and `subString`.
   - `checkRange`: Determines the range for replacement.

2. **Iterate Through `actualString`**:
   - Compare characters in `actualString` with the characters in `subString`.
   - Track the number of consecutive matches (`upCount`) and record the index of the last character of a full match (`indexCount`).

3. **Handle Replacement**:
   - Determine the `startIndex` and `endIndex` of the matched `subString`.
   - Adjust the `checkRange` based on the length difference between `repString` and `subString`.
   - Replace all characters within each specified range with characters from `repString`.

4. **Recursion**:
   - After replacing the first occurrence of `subString`, recursively call the function with the modified string to replace all occurrences.

5. **Return Result**:
   - Return the modified `newString` with all replacements applied.

## Example Usage
```javascript
import customReplace from "./javascript_replace_string_method.js";
const actualString = "What is a Whale, and is a Whale a mammal?";
console.log(customReplace(actualString, "Whale", "Gorilla"));
// Output: "What is a Gorilla, and is a Gorilla a mammal?"
```
