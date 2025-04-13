# 1. Two Sum (#1)

**LeetCode Link**: [Two Sum](https://leetcode.com/problems/two-sum/)

---

## Intuition
For each num in nums, need to see if (target-num) is in the list

We need to return index, so it should be dict with num as key and its index as value

One num might appear multiple times, so value need to be a list of indices.

i.e. 
```
nums = [2,7,11,7,15]
map = {2:[0],7:[1,3],11:[2],15:[4]}
```
## Algorithm
Clearly outline the approach step-by-step:

1. create the map 
2. loop through nums and get complement = target - num
3. check if complement in map

## Implementation
My code:
```python!
map = defaultdict(list)
n = len(nums)
for i in range(n):
    map[nums[i]].append(i)

for num in nums:
    tar = target-num

    if tar == num:                 
        if len(map[tar])>1: 
            return map[tar][:2]
        else:
            continue
    else:
        if tar in map:
            return [map[num][0],map[tar][0]]
        else:
            continue
```

Better implementation:

```python
# Python solution example
class Solution:
    def twoSum(self, nums, target):
        hashmap = {}
        for idx, num in enumerate(nums):
            complement = target - num
            if complement in hashmap:
                return [hashmap[complement], idx]
            hashmap[num] = idx

```
## Complexity Analysis
- Time
- Space

## Reflection
Find complement as we building up the map is a more neat implementation!