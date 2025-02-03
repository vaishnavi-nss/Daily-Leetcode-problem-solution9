# Daily-Leetcode-problem-solution9
PROBLEM

You are given a string s and an integer k.
Define a function distance(s1, s2) between two strings s1 and s2 of the same length n as:
The sum of the minimum distance between s1[i] and s2[i] when the characters from 'a' to 'z' are placed in a cyclic order, for all i in the range [0, n - 1].
For example, distance("ab", "cd") == 4, and distance("a", "z") == 1.
You can change any letter of s to any other lowercase English letter, any number of times.
Return a string denoting the lexicographically smallest string t you can get after some changes, such that distance(s, t) <= k.

Intuition

We need to construct a lexicographically smallest string t such that the cyclic distance between s and t is at most k. This approach ensures that we obtain the smallest lexicographical string while keeping the distance constraint satisfied.

Approach

The cyclic distance between two characters s[i] and t[i] is given by:
min(∣s[i]−t[i]∣,26−∣s[i]−t[i]∣)
Since we want t to be lexicographically smallest, we try to change each character in s to 'a' first, as 'a' is the smallest letter.

Algorithm

Traverse s from left to right.
For each character s[i], check how much it costs to change it to 'a'.
The cost is min(|s[i] - 'a'|, 26 - |s[i] - 'a'|).
If we can afford to change s[i] to 'a' (i.e., cost ≤ k), we do it and subtract the cost from k.
Otherwise, we decrement s[i] lexicographically as much as possible within the remaining k.
Stop when k == 0 or after processing the entire string.

Complexity

Time complexity: O(n)

Space complexity:O(1)
