---
layout: post
title:  "F1 Score == Accuracy 인 경우는?"
category : [Data-Science]
tag: [Data-Science]
---



# F1 Score == Accuracy ??

F1 Score는 여러 평균을 가지고 있다.

Macro 평균, Micro 평균, Weighted 평균

각 평균들이 어떤 방식을 통해 구해지는지는 대충 느낌적으로(?) 알고 있다. 

그림으로 표현하면 아래와 같다


## Macro-Averaged F1 Score 2


```python
#Macro F1 Score
from IPython.display import Image
Image("D:\Blog\Post\images\Macro F1.jpg")
```




![jpeg](..\Category\Data-Science\images\output_2_0.jpg)



## Weighted F1 Score


```python
Image("D:\Blog\Post\images\Weighted F1.jpg")
```




![jpeg](..\Category\Data-Science\images\output_4_0.jpg)



## Micro F1 Score


```python
Image("D:\Blog\Post\images\Micro F1.jpg")
```




![jpeg](..\Category\Data-Science\images\output_6_0.jpg)



### 정리해보면 

- Macro 평균은 각 클래스의 F1 Score의 평균
- Weighted 평균은 각 클래스가 전체 데이터에서 차지하는 비중을 고려한 F1 Score의 평균
- Micro 평균은 전체 데이터의 F1 Score 평균이라는 느낌이다.

### 이 때, 만약 모든 데이터가 정확히 1개의 클래스만 갖는 데이터를 생각해보자 
### (Multi Label이 아닌 경우 많은 데이터들이 이런 경우를 가지고 있다.)

- Accuracy 는 전체 데이터중 True 데이터의 비율이다

$$Accuracy = \frac{TP+TN}{TP+TN+FP+FN} $$  
  
  

이 때 모든 데이터가 정확히 1개의 클래스만 갖는다면, 사실상 TN이라는 데이터는 없다. 그건 또 다른 TP 값이 된다. 즉 TP==TN이 된다.  
  
  

$$Accuracy = \frac{TP+TP}{TP+TP+FP+FN}\\ \\ =\frac {2TP}{2TP+FP+FN}\\ \\ =\frac{TP}{TP+\frac{1}{2}(FP+FN)}$$

### 이제 다시 Micro F1 Score의 표를 보자. 

  


동일한 값임을 확인할 수 있다.

이 사실을 몰랐을 때, 괜히 실험을 부탁한 부사수에게 뭐 잘못 나온거 아니냐고 코드 한 번 보자고 했다가 머쓱했던 적이 있다.

이 글을 읽으시는 분들은 그런 실수를 피할 수 있으면 좋겠다.
