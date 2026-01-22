# Leetcode-and-other-coding-problems
Solving leetcode and other problems with logic

# Two Sum

## Problem Statement

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input has exactly one solution, and you may not use the same element twice.

## Example

**Input:**

```
nums = [2,7,11,15]
target = 9
```

**Output:**

```
[0,1]
```

## Approach

* Use a hash map (dictionary) to store previously seen numbers and their indices.
* For each element, calculate the required complement (`target - current number`).
* If the complement exists in the map, return both indices.

## Complexity

* **Time Complexity:** O(n)
* **Space Complexity:** O(n)

## Python Solution

```python
class Solution:
    def twoSum(self, nums: list[int], target: int) -> list[int]:
        seen = {}
        for i, num in enumerate(nums):
            diff = target - num
            if diff in seen:
                return [seen[diff], i]
            seen[num] = i
```


# Add Two Numbers (Linked List)

## Problem Statement

You are given two non-empty linked lists representing two non-negative integers.
The digits are stored in reverse order, and each node contains a single digit.

Add the two numbers and return the sum as a linked list.

## Example

**Input:**

```
l1 = [2,4,3]
l2 = [5,6,4]
```

**Output:**

```
[7,0,8]
```

**Explanation:**
342 + 465 = 807

## Approach

* Traverse both linked lists simultaneously.
* Add corresponding digits along with carry.
* Store the unit digit in a new node.
* Carry forward any overflow.

## Complexity

* **Time Complexity:** O(max(m, n))
* **Space Complexity:** O(max(m, n))

## Python Solution

```python
class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        dummy = ListNode(0)
        current = dummy
        carry = 0

        while l1 or l2 or carry:
            val1 = l1.val if l1 else 0
            val2 = l2.val if l2 else 0

            total = val1 + val2 + carry
            carry = total // 10

            current.next = ListNode(total % 10)
            current = current.next

            if l1:
                l1 = l1.next
            if l2:
                l2 = l2.next

        return dummy.next
```
