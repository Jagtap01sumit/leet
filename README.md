# leetcode 


### 342. Power of Four
```java
class Solution {
    public boolean isPowerOfFour(int n) {
        // classic bitwise trick to check if a number has only one bit set
        // n     = 1000
        // n - 1 = 0111
        // n & (n - 1) = 1000 & 0111 = 0000
        int x = n & (n-1);
        
        int count =0;

        if(n>0 && x==0){
            while(n>1){
                n>>=1;
                count++;
            }
        }else{
            return false;
        }
        return (count%2==0)? true: false;
    }
}

```
```
1️⃣ n >>= 1;

>> is the bitwise right shift operator.

n >>= 1 is shorthand for n = n >> 1.

Right shifting by 1 is the same as integer division by 2 (dropping any remainder).
```
| n (decimal) | n (binary) | n >> 1 (binary) | Result (decimal) |
|-------------|------------|-----------------|------------------|
| 8           | 1000       | 0100            | 4                |
| 4           | 0100       | 0010            | 2                |
| 2           | 0010       | 0001            | 1                |
