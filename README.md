# Rotate Array

Given an array, rotate the array to the right by k steps, where k is non-negative.

### Example:

**_Input:_** `nums = [1,2,3,4,5,6,7], k = 3`

**_Output:_** `[5,6,7,1,2,3,4]`

**_Explanation:_**
rotate 1 steps to the right: `[7,1,2,3,4,5,6]`

rotate 2 steps to the right: `[6,7,1,2,3,4,5]`

rotate 3 steps to the right: `[5,6,7,1,2,3,4]`

### Constraints:

`1 <= nums.length <= 10^5`

`-2^31 <= nums[i] <= 2^31 - 1`

`0 <= k <= 10^5`


## Solution in JavaScript:

```
var rotate = function(nums, k) {
        
    k = k % nums.length;
    let count = 0;
    for (let start = 0; count < nums.length; start++) {
        let current = start;
        let prev = nums[start];
        do {
            let next = (current + k) % nums.length;
            let temp = nums[next];
            nums[next] = prev;
            prev = temp;
            current = next;
            count++;
        } while (start != current)
    }
    
    return nums;
};
```
