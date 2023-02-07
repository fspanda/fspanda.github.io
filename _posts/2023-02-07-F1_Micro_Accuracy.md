---
layout: post
title:  "F1 Micro 와 Accuracy"
categories: 
    - Data Science
---

# F1 Micro와 Accuracy는 같은가?

**논문 작업 중 부사수에게 F1 Score와 Accuracy 값을 계산해 달라 부탁했다.** 

결과를 확인했는데 Macro, Weighted F1 Score는 그럴듯하게 나오는데 F1 Score와 Accuracy 값이 동일하게 나오는 걸 확인.

뭔가 이상하다 싶어 구글링을 해 보니 이런 글이 나온다.

[Is F1 micro the same as Accuracy?]([https://](https://stackoverflow.com/questions/37358496/is-f1-micro-the-same-as-accuracy))

나만 이 내용을 처음 안 것은 아닌 듯했다. 

글에 들어가면 누군가 친절하게 연습장으로 공식이 성립됨을 보여줬는데, 필기체에 영 익숙치 않아 알아보기 힘드니

Latex 수식으로 정리해 보았다.


$$Precision = \frac{TP}{TP+FN} $$

$$Recall = \frac{TP}{FP+FN} $$

$$F1 Score = \frac{Precision*Recall}{Precision+Recall} = \frac{TP}{TP+\frac{1}{2}(FP+FN)}$$
 