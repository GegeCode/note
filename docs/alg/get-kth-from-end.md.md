# 倒数第 n 个节点

  

> 剑指 offer22

  

## 1、描述

  

输入一个链表，输出该链表中倒数第k个节点。为了符合大多数人的习惯，本题从1开始计数，即链表的尾节点是倒数第1个节点。

  

例如，一个链表有 6 个节点，从头节点开始，它们的值依次是 1、2、3、4、5、6。这个链表的倒数第 3 个节点是值为 4 的节点。

  

```

给定一个链表: 1->2->3->4->5, 和 k = 2.

  

返回链表 4->5.

```

  

## 2、解题思路

  

这道题需要用到技巧，第一次可能想不出来，做过类似的题就很容易。

  

我们需要两个指针，定义为快慢指针，快指针用于检测有没有到链表的末端，满指针用于返回倒数第几个节点。

  

1. 先遍历链表，遍历时，将两个指针的距离调节为，题目中倒数节点的距离；

2. 判断快指针有没有到末端，到了返回慢指针，未到继续遍历。

  

## 3、实现

  
  

```javascript

/**

* @param  {ListNode}  head

* @param  {number}  k

* @return  {ListNode}

*/

var  getKthFromEnd = function (head, k) {

let  fast = head;

let  slow = head;

let  n = 0;

while (fast != null) {

if (n >= k) slow = slow.next;

fast = fast.next;

n++;
}
return  slow;
};
```
