# leetcode_Longest_Palindromic_Substring
+ 앞뒤가 똑같고 길이가 잴 긴 문자열 구하기
+ 前後字元相同並且找出最常字串
>Timothy H Chang 코드를 참고하였습니다
-----
+ Example1
```
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.
```
----
+ Example2
```
Input: s = "cbbd"
Output: "bb"
```
----

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        def cal(l,r):
            while(l >= 0 and r < len(s) and s[l] == s[r]): 
                l-=1 # 왼쪽으로 한칸
                r+=1 # 오른쪽으로 한칸
            
            return s[l+1:r] #0일때 위치가 -1되므로 l+1:r을 반환 해준다
        
        res = ""
        #"babad"
        for i in range(len(s)): 
            ori = cal(i,i)
            if len(test) > len(res):
                res = ori
        #"cbbd"
            ori = cal(i,i+1) # cbbd와 같은 문자열 처리
            if len(test) > len(res):
                res = ori
        
        return res
```
---
```
결론 : 
중간위치로 좌우 한칸씩 확인하며 값을 저장
```
---
```
結論:
由中間值去判斷左右各一格來找出最大長度的string
```
---
### Result
Runtime: 1429 ms, faster than 54.45% of Python3 online submissions for Longest Palindromic Substring.\
Memory Usage: 14 MB, less than 60.46% of Python3 online submissions for Longest Palindromic Substring.
