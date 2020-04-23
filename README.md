# Excel Sheet Column Number
## https://leetcode.com/problems/excel-sheet-column-number

Given a column title as appear in an Excel sheet, return its corresponding column number.

For example:

    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
    AA -> 27
    AB -> 28 
    ...
```    
Example 1:

Input: "A"
Output: 1

Example 2:

Input: "AB"
Output: 28

Example 3:

Input: "ZY"
Output: 701
```

# Implementation :

```java
class Solution {
    public int titleToNumber(String s) {
        if(s == null || s.length() == 0)
            return 0;
        int column = 0;
        int unit = 0;
        for(int i = s.length()-1; i >= 0; i--) {
            char ch = s.charAt(i);
            int value = (ch - 'A') + 1; 
            int pos = (int) Math.pow(26, unit);
            column = column + (pos * value);
            unit++;
        }
        return column;
    }
}
```

