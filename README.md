import sys

def longest_unique_substring_length(s: str) -> int:
    last_index = {}
    left = 0
    max_len = 0

    for i, ch in enumerate(s):
        if ch in last_index and last_index[ch] >= left:
            left = last_index[ch] + 1
        last_index[ch] = i
        max_len = max(max_len, i - left + 1)

    return max_len

if __name__ == "__main__":
    s = sys.stdin.readline().strip()
    if not s:
        print(0)
    else:
        print(longest_unique_substring_length(s))
