# day4

## 24. 两两交换链表中的节点
* 我的答案（AC了嘿嘿）
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
      public ListNode swapPairs(ListNode head) {
          ListNode dummy = new ListNode(0,head);// 引入虚拟头节点
          
          ListNode p = dummy;
          while(p.next != null && p.next.next != null){
              ListNode pre = p.next;
              ListNode cur = p.next.next;
              pre.next = cur.next;
              cur.next = pre;
              p.next = cur;
              p = cur.next;
          }
          return dummy.next;
      }
  }
  ```

## 19.删除链表的倒数第N个节点
* 注意：
  - 这道题用到了快慢指针、虚拟节点
  - 注意return的节点
* 正确答案（第一次差一点AC）：
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
      public ListNode removeNthFromEnd(ListNode head, int n) {
          ListNode dummy = new ListNode(0,head);
          ListNode pre = dummy;
          for(int i = 0;i < n;i++){
              pre = pre.next;
          }
          ListNode cur = dummy;
          while(pre.next!=null){
              cur = cur.next;
              pre = pre.next;
          }
          ListNode delete = cur.next;
          cur.next = delete.next;
          return dummy.next;
      }
  }
  ```

## 面试题 02.07. 链表相交

## 142.环形链表II
