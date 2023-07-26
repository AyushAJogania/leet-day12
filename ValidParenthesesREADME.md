# leet-day12

# Valid Parentheses - LeetCode Problem

## Problem Description

Given a string `s` containing only the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:
1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every closing bracket has a corresponding opening bracket of the same type.

## Examples

**Example 1:**
```
Input: s = "()"
Output: true
```

**Example 2:**
```
Input: s = "()[]{}"
Output: true
```

**Example 3:**
```
Input: s = "(]"
Output: false
```

## Constraints
- 1 <= s.length <= 104
- `s` consists of parentheses only '()[]{}'.

## Approach

To check the validity of the given string, we can use a stack data structure. We iterate through the string, and for each character:
1. If it is an open bracket ('(', '{', '['), we push it onto the stack.
2. If it is a closing bracket (')', '}', ']'), we check if the stack is empty or the top of the stack doesn't correspond to the same type of bracket. If either of these conditions is true, the string is invalid, and we return false.
3. If the closing bracket matches the top of the stack, we pop the top element from the stack.

After iterating through the entire string, if the stack is empty, the string is valid; otherwise, it is invalid.

## Complexity Analysis

The time complexity for this approach is O(n), where n is the length of the input string `s`. In the worst case, we need to traverse the entire string once. The space complexity is also O(n), as we may need to store all opening brackets in the stack.

## Summary

The problem can be solved using a stack to check the validity of parentheses. We iterate through the string and keep track of opening brackets using a stack, and whenever we encounter a closing bracket, we check if it matches the top of the stack or not. If everything matches, the string is valid; otherwise, it is invalid.

The C++ code provided above demonstrates the implementation of this approach and can be used to test the solution against different test cases.
