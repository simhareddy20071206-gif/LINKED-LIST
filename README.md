
***

## Problem Statement

- **Merge two sorted linked lists** into one sorted linked list (LeetCode Problem 21).
- You are given the heads of two sorted linked lists, h1 and h2.
- **Return the head of the new merged, sorted linked list.**

***

## Recursive Approach Explanation

- If either list is **empty** (null), return the other as the result.
- At every step, compare the head values of h1 and h2:
    - The **smaller** value node becomes the next node in the merged list.
    - **Recursively** merge the rest.
- Repeat until all nodes in both lists are merged in sorted order.

***

## C++ Code

```cpp
ListNode* mergeTwoLists(ListNode* h1, ListNode* h2) {
    if(h1 == NULL) return h2;
    if(h2 == NULL) return h1;
    if(h1->val <= h2->val) {
        h1->next = mergeTwoLists(h1->next, h2);
        return h1;
    } else {
        h2->next = mergeTwoLists(h1, h2->next);
        return h2;
    }
}
```

***

## Key Points

- This is a **recursive solution**.
- At each recursive call, the function decides which node (from h1 or h2) becomes the current node of the result list, then merges the remaining nodes.
- When one list is **exhausted**, simply return the other list as the remainder.
- **Time Complexity:** $$O(n + m)$$, where $$n$$ and $$m$$ are the lengths of the two lists.
- **Space Complexity:** $$O(n + m)$$ due to recursion stack in the worst case.

***

## Example

If:
- h1: 1 → 3 → 5
- h2: 2 → 4 → 6

Output after merging:
- 1 → 2 → 3 → 4 → 5 → 6

***

This extraction is a direct and clear write-up of the explanation and code exactly as presented in the video for merging two sorted linked lists using recursion.[1]

[1](https://www.youtube.com/watch?v=f8RPIb-0DDE&list=PLGjplNEQ1it-OKRcYlCEDpTiIB1YOcvn6&index=5)
