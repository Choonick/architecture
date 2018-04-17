# template method

- 왜 써야하는가? ( 기존코드랑, 디자인 패턴을 적용한 것의 차이점 )
    - 이 패턴의 장점들
   
```
템플릿 메소드 패턴은 "알고리즘의 뼈대"를 맞추는 것에 있습니다. 
즉, 전체적인 레이아웃을 통일 시키지만 상속받은 클래스로 하여금 
어느정도 유연성을 주도록하는 디자인 패턴입니다.
추상 메소드(abstrcat method)와 훅 메소드(hook method)를 적절히 사용해서 
전체적인 알고리즘의 뼈대를 유지하되 유연하게 기능을 변경할 수 있도록 하고자 할 때 사용하면 유용하겠네요. :3

### 추상메소드는 상속받은 클래스에서 무조건 구현 훅 메소드는 구현해도되고 안해도되고?? 맞나?

```
예시
#### 1. 커피 만드는 법
1. 물을 끓인다.
2. 끓는 물에 커피를 우려낸다.
3. 커피를 컵에 따른다.
4. 설탕과 우유를 추가한다.

#### 2. 홍차 만드는 법
1. 물을 끓인다.
2. 끓는 물에 차를 우려낸다.
3. 차를 컵에 따른다.
4. 레몬을 추가한다.


출처: http://jusungpark.tistory.com/24 [정리정리정리]

- 클래스는 5개인데 왜 5개 다써야하는가?? - 각 클래스의 존재 이유
- 다른 사람의 디자인패턴의 질문 한두개





