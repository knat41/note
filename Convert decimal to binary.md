# 
n = int(input())
if n == 0:
    ans = str(0)
else:
    ans = ''
while n > 0:
    ans = str(n % 2) + ans
    n = n // 2
print(ans)