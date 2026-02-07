Problem: Longest Substring Without Repeating Characters

Algorithm:
1. Initialize an empty set to store unique characters.
2. Use two pointers (left and right) to represent a sliding window.
3. Move the right pointer to expand the window.
4. If a duplicate character is found:
   - Remove characters from the left until the duplicate is removed.
5. Update the maximum window length.
6. Return the maximum length found.

Time Complexity: O(n)
Space Complexity: O(n)

Explanation:
This solution uses the sliding window technique to avoid rechecking
characters, ensuring optimal performance.
