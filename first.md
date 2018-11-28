* question:  
给定一个整数数组，其中有两项之和为一个特定的数字，假设每次 input 只有一个唯一解，不允许两次使用同一个元素，返回这两个数的索引。

* 举例：  
```node
给定nums = [2, 7, 11, 12]，target = 9

由于nums[0] + nums[1] = 9
所以返回[0, 1]
```

* answer:  
```node
function foo (arr, input) {
    const map = {};
    const result = [];

    for (let i = 0, length = arr.length; i < length; i++) {
        const temp = input - arr[i];
        if (typeof map[temp] !== 'undefined') {
            result[0] = map[temp];
            result[1] = i;
            return result;
        }
        map[arr[i]] = i;
    }
} 
```
by @Robin-front
