## leetcode-14

最长公共前缀

### 思路

水平扫描

1. 取第一个字符串作为比较的基准，如String firstStr = strs[0];
2. 遍历其他字符串，当其他字符串所对应位置的字符不相等时，就返回所对应位置之前的字符串

### talk is cheap, show your code

```
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if(strs == null || strs.length == 0){ return "";}
        
        String firstStr = strs[0];
        char[] charArr = firstStr.toCharArray();
        for(int i = 0;i<charArr.length;i++){
            char ch = charArr[i];
            for(int j = 1;j< strs.length;j++){
                if(i == strs[j].length() || strs[j].charAt(i) != ch){
                    return firstStr.substring(0,i);
                }
            }
        }
        return firstStr;
    }
}
```

### 时间复杂度： 

比较的次数 = 第一个字符串的字符数量 * 字符串的个数

对于n个长度为m的相同字符串， 会进行 m*n次比较。

### 空间复杂度： 

没有申请额外的内存空间 O(1)
