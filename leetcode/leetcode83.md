[leetcode83](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-list/)

思路：
+ 将当前节点与之后的节点进行比较
  * 如果相等，即为重复的，需要更改next指针，跳过下一个节点指向下一个节点之后的节点
  * 不相等,则继续向后遍历

时间复杂度：O(n) 对链表的每个节点都进行检查是否重复
空间复杂度：O(1) 没有申请额外的空间  

### Code
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode cur = head;
        while(cur!=null&&cur.next!=null){
            if(cur.next.val == cur.val){
                cur.next = cur.next.next;
            }else{
                cur = cur.next;
            }
        }
        return head;
    }
}
```