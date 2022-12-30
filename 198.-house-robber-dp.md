# 198. House Robber - DP

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and it will automatically contact the police if two adjacent houses were broken into on the same night.

Given an integer array `nums` representing the amount of money of each house, return _the maximum amount of money you can rob tonight without alerting the police_.

&#x20;

**Example 1:**

<pre><code><strong>Input: nums = [1,2,3,1]
</strong><strong>Output: 4
</strong><strong>Explanation: Rob house 1 (money = 1) and then rob house 3 (money = 3).
</strong>Total amount you can rob = 1 + 3 = 4.
</code></pre>

```python
class Solution(object):
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        choose1=choose2=0

        for n in nums:
            temp=max(choose1+n,choose2)
            choose1=choose2
            choose2=temp

        return choose2
```
