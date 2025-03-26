---
title: "Longest Repeating Character Replacement"
date: "2025-03-26"
authors:
  - "jathurchan"
featuredVideo: "https://youtu.be/fkq6JXK3ulY"
projects:
  - "52"
---

```python
from collections import Counter

class Solution:
    def characterReplacement(self, s: str, k: int) -> int:
        # s = "ABAB", k = 2
        # res = 4

        # s = "AABABBA", k = 1
        # res = 4

        # sliding window

        n = len(s)
        left = 0
        freq = Counter()

        res = 0

        for right in range(n):
            freq[s[right]] += 1
            highestFreq = max(freq.values())

            while (right-left+1 - highestFreq) > k:
                freq[s[left]] -= 1
                left += 1

            res = max(res, right-left+1)
        
        return res

        # Time: O(n)
        # Space: O(1)
```
