# day3

## 203.移除链表元素
* 注意：
  - 两种方法：分类为删除头节点，删除非头节点进行考虑；构造虚拟节点；
  - 注意判断语句`p!= null && p.next!=null`，要把`p!= null`放在前面，因为当`&&`判断`p!= null`为`false`时，就不会判断`p.next!=null`啦
* 方法一：
``` java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        ListNode p = head;
        while(p!= null && p.val == val){
            head = p.next;
            p = head;
        }
        while(p!= null && p.next!=null){
            if(p.next.val == val){
                ListNode q = p.next;
                p.next = q.next;
            }else{
                p = p.next;
            }
        }
        return head;
    }
}
```
* 方法二：设置虚拟节点
``` java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        ListNode dummy = new ListNode(-1, head);
        ListNode p = dummy.next;
        ListNode q = dummy;
        while(p!=null){
            if(p.val == val){
                q.next = p.next;
                p = q.next;
            }else{
                p = p.next;
                q = q.next;
            }    
        }
        head = dummy.next;
        return head;
    }
}
```
## 707.设计链表

## 206.反转链表
