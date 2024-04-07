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
* 注意：多观察需要分类讨论的情况
* 正确答案：
  ``` java
  class Node{
    int val;
    Node next;
    Node(){}
    public Node(int val){
        this.val = val;
    }
  }
  class MyLinkedList {
    int size;
    Node head;

    public MyLinkedList() {
        this.size = 0;
        this.head = new Node(0);
    }
    
    public int get(int index) {
        if(index < 0||index >= size){
            return -1;
        }
        Node p =head;
        for(int i = 0;i <= index;i++){
            p = p.next;
        }
        return p.val;
    }
    
    public void addAtHead(int val) {
        addAtIndex(0,val);
    }
    
    public void addAtTail(int val) {
        addAtIndex(size,val);
    }
    
    public void addAtIndex(int index, int val) {
        if(index > size){
            return;
        }
        if(index < 0){
            index = 0;
        }
        size++;
        Node p = new Node(val);
        Node q = head;
        for(int i = 0;i < index;i++){
            q = q.next;
        }
        p.next = q.next;
        q.next = p;
        return;
    }
    
    public void deleteAtIndex(int index) {
        if(index < 0 || index >= size){
            return;
        }
        size--;
        if(index == 0){
            head = head.next;
            return;
        }
        Node p =head;
        for(int i=0;i < index;i++){
            p = p.next;
        }
        Node q = p.next;
        p.next = q.next;
        return;
    }
  }
  ```
## 206.反转链表
* 注意：
  - 链表不要出现环
 
* 我的答案：
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
      public ListNode reverseList(ListNode head) {
        if(head == null || head.next == null){
            return head;
        }
        ListNode p = head.next;
        head.next = null;
        while(p.next!=null){
            ListNode q = p.next;
            p.next = head;
            head = p;
            p = q;  
        }
        p.next = head;
        head = p;
        return head;
    }
    }
  ```
