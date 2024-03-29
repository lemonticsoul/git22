가설: 코테 문제를 좋은 cpu를 사용하면 연산속도가 빨라져서 좀더 빠르게 풀수 있지 않을까?

코테 문제:

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
python'''





## t2 계열

### t2 micro

1. cpu사용량

![image](https://github.com/lemonticsoul/git22/assets/127959482/7c124143-e588-44dc-9141-cfea7cc15d0d)


2. 코테 시간 측정

real    11.488s
user   11.470s
sys     0.012s

### 

## t3계열

### t3 micro

1.cpu 사용


![image](https://github.com/lemonticsoul/git22/assets/127959482/2c121b4e-5d2f-4cf6-abba-23fc48bf0e4c)

코테 시간

real    0m10.944s
user    0m10.917s
sys     0m0.004s




## t4계열

### t4g micro

cpu 사용량

![image](https://github.com/lemonticsoul/git22/assets/127959482/356e9839-ac1e-4110-ae2c-675a5adbdbfe)



real    0m11.326s
user    0m11.318s
sys     0m0.008s

t4g micro와 t3 micro와 뭐가다른가?
gravition 이 적혀있어서 

t4g는 gravition으로 되있지만 cpu 비용대비 성능 이 좋다고 하는데,
g가 없는데 t3가 cpu 사용량이 좋은 이유는 집약적인 이 한문제만 설계되있기 때문에 성능이 좋다고 적혀있다

g가 성능이 좋다고 하는데 왜 시간은 느린가?

아마 python3가 t3에 최적화가 안되있던거같다.

cpu성능이 버전차이는 성능이 개선되지만,
micro에서 large로 갈 때 cpu 성능이 개선되지만 왜? 안되는지 모르겠고,
뇌피셜로 dfs가 모든 노드를 탐색하는데 이 노드를 좀더 깊게 탐색해서 시간이 걸린거같다.
같은 g계열은 cpu성능이 좋아도 미묘하게 그렇게 되지않는점.

## C계열

C4 2xlarge
![image](https://github.com/lemonticsoul/git22/assets/127959482/5a1258aa-8289-46d6-962f-1f73d2e18829)

real    0m11.876s
user    0m11.872s
sys     0m0.004s



