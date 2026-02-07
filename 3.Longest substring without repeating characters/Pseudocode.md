Algorithm LongestSubstringWithoutRepeatingCharacters(s):

    create empty set char_set
    left ← 0
    max_len ← 0

    for right from 0 to length(s) - 1:
        while s[right] is in char_set:
            remove s[left] from char_set
            left ← left + 1

        add s[right] to char_set
        max_len ← max(max_len, right - left + 1)

    return max_len
