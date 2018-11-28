* question  
  
将一个 32-bit 无符号整数的所有数字倒序，输出一个新的整数，如

eg1. x = 123, return 321  
eg2. x = -123, return -321  
提示：

考虑末尾为零的情况，如 10, 100  
考虑溢出情况，如将 1000000003 倒序排列  
溢出则输出 0.  

* answer  
```node
function newNum(num) {
    let result;
    const max = 2 ** 31;
    const newNum = Math.abs(num);
    if (max < newNum) {
        return 0
    }

    const numArr = newNum.toString().split('');

    result = Number(numArr.reverse().join(''));
    if (num < 0) {
        result = -1 * result;
    }

    if (Math.abs(result) > max) {
        return 0;
    }

    return result;
} 
```
