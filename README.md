

***

## Problem Statement

- Given a **linked list**, reverse it in place.
- Return the new head after reversal.
- This is **LeetCode Problem 206**.
- You are given the head of a singly linked list. Reverse the list, and return the head of the reversed linked list.

***

## Approach Explanation

- You need **three pointers**:
    - `prev` (initially `NULL`)
    - `curr` (starts at `head`)
    - `next` (helper to save next node before breaking the link)

**Steps:**

1. Save `curr->next` in `next` (preserve the address of the next node).
2. Reverse the link: make `curr->next = prev`.
3. Move `prev` to `curr`.
4. Move `curr` to `next`.
5. Repeat until `curr` becomes NULL.
6. At the end, `prev` is the new head.

The traversal is done within a loop until all nodes are processed.

- **Space Complexity:** $$ O(1) $$, only 3 pointers used
- **Time Complexity:** $$ O(n) $$, as we traverse the list once

***

## C++ Code

```cpp
ListNode* reverseList(ListNode* head) {
    ListNode* prev = NULL;
    ListNode* curr = head;
    ListNode* next = NULL;
    while (curr != NULL) {
        next = curr->next;    // Step 1: Save next node
        curr->next = prev;    // Step 2: Reverse current node's pointer
        prev = curr;          // Step 3: Move prev to current
        curr = next;          // Step 4: Move curr to next
    }
    return prev;              // prev is the new head
}
```

***

## Key Points from Explanation

- **Need to preserve next node's address** before breaking the link.
- For every node, repeat 4 actions:  
    1. Save next node
    2. Reverse pointer
    3. Move previous pointer
    4. Move current pointer
- **Stop** when current pointer becomes `NULL`.
- At the end, new head is at the node pointed to by `prev`.
- **No extra space** needed beyond pointers.

***

## Example Dry Run

Original:  1 → 2 → 3 → 4 → 5  
Reversed:  5 → 4 → 3 → 2 → 1

***

**Summary:**  
Always use three pointers and perform 4 repeatable steps in the loop for in-place reversal of singly linked lists. This is a logical, space-efficient approach used in interviews and coding problems.

***

This is the complete step-by-step textual and code extraction as explained in the video for **reversing a linked list**.[1]

[1](https://www.youtube.com/watch?v=R-CKBYnOv1U&list=PLGjplNEQ1it-OKRcYlCEDpTiIB1YOcvn6&index=2)
