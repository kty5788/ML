# 선형회귀 - 선형회귀가 원점을 지나는 직선일때

선형회귀가 원점을 지난다는 가정이라 함은

그래프가 y = wx + b 그래프에서 b가 0임을 의미한다.

---

```python
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

def linearregression(w):
    w *= 1/20
    y = w * x
    line.set_data(x,y)
    return y

def costfunction(w):
    w *= 1/20
    y = w * x
    y_slice = y[1:]
    total = 0
    for i in range(len(data_x)):
        total += sum((data_y - y_slice))**2
    
    total /= (2 * len(data_x))
    plt.scatter(w,total,c='blue')


    


data_x = np.arange(0,4)
data_y = np.arange(0,4) # 임의의 x,y 데이터 생성
x = np.arange(0,5) # x축
fig = plt.figure()



plt.subplot(1,2,1) # 1행 2열 1번째 그래프 설정
plt.xlim(0,4)
plt.ylim(0,10) # 1번째 그래프의 x축/y축 범위 설정
plt.scatter(data_x,data_y,c='red') # 임의의 데이터 좌표에 표현
line, = plt.plot([],[])
ani = FuncAnimation(fig, linearregression, frames=81, interval=100) # 선형 애니메이션


plt.subplot(1,2,2) # 1행 2열 2번째 그래프 설정
plt.xlim(0,4)
plt.ylim(0,200) # 2번 그래프 x축/y축 범위 설정
ani2 = FuncAnimation(fig,costfunction, frames= 81, interval=100) # 비용함수 애니메이션


plt.show()
```

데이터를 예측하는 가장 '지도학습(supervised learning)'인 선형회귀에서 아주아주 단순한 형태인 y = wx 형태의 꼴읖 보았다.

예측된 값으로 도출된 오른쪽 그래프 (비용함수)는 '이차함수' 형태이다.

