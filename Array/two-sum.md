# Two Sum (#1)

**LeetCode Link**: [Two Sum](https://leetcode.com/problems/two-sum/)

---

## Intuition
Your initial idea and thought process.

## Algorithm
1. Step-by-step explanation of your approach.
2. Clearly explain your logic.

## Implementation
```python
# Python solution
class Solution:
    def twoSum(self, nums, target):
        hashmap = {}
        for idx, num in enumerate(nums):
            complement = target - num
            if complement in hashmap:
                return [hashmap[complement], idx]
            hashmap[num] = idx

