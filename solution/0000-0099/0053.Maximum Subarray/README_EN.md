# [53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray)

[中文文档](/solution/0000-0099/0053.Maximum%20Subarray/README.md)

## Description

<p>Given an integer array <code>nums</code>, find the contiguous subarray&nbsp;(containing at least one number) which has the largest sum and return its sum.</p>

<p><strong>Example:</strong></p>

<pre>

<strong>Input:</strong> [-2,1,-3,4,-1,2,1,-5,4],

<strong>Output:</strong> 6

<strong>Explanation:</strong>&nbsp;[4,-1,2,1] has the largest sum = 6.

</pre>

<p><strong>Follow up:</strong></p>

<p>If you have figured out the O(<em>n</em>) solution, try coding another solution using the divide and conquer approach, which is more subtle.</p>

## Solutions

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        n = len(nums)
        res = f = nums[0]
        for i in range(1, n):
            f = nums[i] + max(f, 0)
            res = max(res, f)
        return res
```

### **Java**

```java
class Solution {
    public int maxSubArray(int[] nums) {
        int f = nums[0], res = nums[0];
        for (int i = 1, n = nums.length; i < n; ++i) {
            f = nums[i] + Math.max(f, 0);
            res = Math.max(res, f);
        }
        return res;
    }
}
```

### **C++**

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int f = nums[0], res = nums[0];
        for (int i = 1; i < nums.size(); ++i) {
            f = nums[i] + max(f, 0);
            res = max(res, f);
        }
        return res;
    }
};
```

### **JavaScript**

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function (nums) {
  let f = nums[0],
    res = nums[0];
  for (let i = 1; i < nums.length; ++i) {
    f = nums[i] + Math.max(f, 0);
    res = Math.max(res, f);
  }
  return res;
};
```

### **Go**

```go
func maxSubArray(nums []int) int {
    f, res := nums[0], nums[0]
    for i := 1; i < len(nums); i++ {
        if f > 0 {
            f += nums[i]
        } else {
            f = nums[i]
        }
        if f > res {
            res = f
        }
    }
    return res
}
```

### **...**

```

```

<!-- tabs:end -->
