### 88-合并两个有序数组

[leetcode-88](https://leetcode-cn.com/problems/merge-sorted-array/)

思路：

+ 获取两个数组合并后的总长度
+ 两个从尾向前遍历、比较获取较大的元素
+ 遍历结束，当第二个数据还有剩余的元素，直接填充在第一个数据的前面

```
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int p = m-- + n-- -1;
        while(m >=0 && n>=0){
            if(nums1[m] < nums2[n]){
                nums1[p--] = nums2[n--];
            }else{
                nums1[p--] = nums1[m--];
            }
        }
        
        while(n >=0){
            nums1[p--] = nums2[n--];
        }
    }
}
```