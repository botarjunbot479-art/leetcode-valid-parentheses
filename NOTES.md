# LeetCode: Valid Parentheses

- slug: `valid-parentheses`
- id: 20
- difficulty: Easy
- tags: String, Stack, Bracket Sequences
- url: https://leetcode.com/problems/valid-parentheses/
- status: **solved_verified**
- detail: Local verified 3/3
- source: LeetCode public GraphQL (no login)
- learned_at: 2026-10-27T08:58:06.514133+00:00

## Problem
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

	- Open brackets must be closed by the same type of brackets.
	- Open brackets must be closed in the correct order.
	- Every close bracket has a corresponding open bracket of the same type.

 

Example 1:

Input: s = "()"

Output: true

Example 2:

Input: s = "()[]{}"

Output: true

Example 3:

Input: s = "(]"

Output: false

Example 4:

Input: s = "([])"

Output: true

Example 5:

Input: s = "([)]"

Output: false

 

Constraints:

	- 1 4
	- s consists of parentheses only '()[]{}'.

## Example testcases (from LeetCode)
```
"()"
"()[]{}"
"(]"
"([])"
"([)]"
```

## Solution (local)
```python
def is_valid(s):
    pair = {")": "(", "]": "[", "}": "{"}
    st = []
    for ch in s:
        if ch in "([{":
            st.append(ch)
        else:
            if not st or st[-1] != pair[ch]:
                return False
            st.pop()
    return not st

```
