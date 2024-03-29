가설: 코테 문제를 좋은 cpu를 사용하면 연산속도가 빨라져서 좀더 빠르게 풀수 있지 않을까?

코테 문제:
## N-Queen
```python
import sys
input=sys.stdin.readline

n=12
graph=[0]*n
cnt=0
def queen(x):
    for i in range(x):
        if graph[x]==graph[i] or abs(graph[x]-graph[i])==abs(x-i):
            return False
    return True

def dfs(x):
    global cnt
    if x==n:
        cnt+=1
        return
    for i in range(n):
        graph[x]=i
        if queen(x):
            dfs(x+1)
    return cnt
dfs(0)
print(cnt)


```
일반으로 돌렸을때?
4.151427 sec







## t2 계열

### t2 micro

1. cpu사용량

![image](https://github.com/lemonticsoul/git22/assets/127959482/7c124143-e588-44dc-9141-cfea7cc15d0d)


2. 코테 시간 측정

real    11.488s
user   11.470s
sys     0.012s

### t2.small

1. cpu사용량

![image](https://github.com/lemonticsoul/git22/assets/127959482/6cf412b9-5f1d-4057-a9e7-c147550f80f5)

2. 코테 시간 측정

real    0m11.429s
user    0m11.424s
sys     0m0.000s



## t3계열

### t3 micro

1.cpu 사용


![image](https://github.com/lemonticsoul/git22/assets/127959482/2c121b4e-5d2f-4cf6-abba-23fc48bf0e4c)

코테 시간

real    0m10.944s
user    0m10.917s
sys     0m0.004s


### T3.large

1.cpu 사용


![image](https://github.com/lemonticsoul/git22/assets/127959482/2fe79c61-9e27-48a0-8919-5874dacb6c63)

2.코테시간

real    0m13.988s
user    0m13.973s
sys     0m0.012s





## t4계열

### t4g micro

1.cpu 사용

![image](https://github.com/lemonticsoul/git22/assets/127959482/356e9839-ac1e-4110-ae2c-675a5adbdbfe)

2.코테시간

real    0m11.326s
user    0m11.318s
sys     0m0.008s

### t4g large

1.cpu 사용

![image](https://github.com/lemonticsoul/git22/assets/127959482/fd3b5349-e582-4961-936e-422ad6406a65)

2.코테시간

real    0m11.315s
user    0m11.307s
sys     0m0.008s




## C계열

### C4 2xlarge

1.cpu 사용

![image](https://github.com/lemonticsoul/git22/assets/127959482/5a1258aa-8289-46d6-962f-1f73d2e18829)

2.코테시간

real    0m11.876s
user    0m11.872s
sys     0m0.004s

### c5.4xlarge

1.cpu 사용

![image](https://github.com/lemonticsoul/git22/assets/127959482/07a3168a-b983-41b9-84c3-3983730efd16)


2.코테시간

real    0m9.521s
user    0m9.520s
sys     0m0.000s





