class Solution:
    def nearestPalindromic(self, n: str) -> str:
        length = len(n)
        
        # Possible candidates
        # 1. Lower palindrome by decrementing the prefix
        # 2. Higher palindrome by incrementing the prefix
        # 3. Palindrome by mirroring the prefix
        # 4. Edge case: '999' -> '1001' and '1000' -> '999'

        candidates = set()
        
        # Case 1 and Case 2: Decrement or Increment the first half
        prefix = int(n[:(length + 1) // 2])
        
        for i in [-1, 0, 1]:
            new_prefix = str(prefix + i)
            if length % 2 == 0:
                candidate = new_prefix + new_prefix[::-1]
            else:
                candidate = new_prefix + new_prefix[-2::-1]
            candidates.add(int(candidate))
        
        # Edge cases
        candidates.add(10 ** (length - 1) - 1)  # Edge case: '100' -> '99'
        candidates.add(10 ** length + 1)        # Edge case: '999' -> '1001'
        
        # Convert n to integer
        original = int(n)
        candidates.discard(original)  # Exclude the original number itself if it is a palindrome
        
        # Find the closest palindrome
        closest = min(candidates, key=lambda x: (abs(x - original), x))
        
        return str(closest)

# Example usage:
sol = Solution()
result = sol.nearestPalindromic("123")
print(result)  # Output: "121"
