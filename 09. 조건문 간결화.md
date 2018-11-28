## 1. 조건문 쪼개기(Decompose Conditinal)

```
복잡한 조건문(if-then-else)이 있을 때는 if, then, else 부분을 각각 메서드로 빼내자
```

~~~java
  if(date.before (SUMMER_START) || date.after(SUMMER_END))
    charge = quantity * _winterRate + _winterServiceCharge;
  else charge = quantity * _summerRate;
~~~

~~~java
  if(notSummer(date))
    charge = winterCharge(quantity);
  else charge = summerCharge(quantity);
~~~


#### 동기

조건을 검사하고 다양한 조건에 따라 다른 작업을 처리하는 코드를 작성하면 금방 method가 길어진다.

큰 덩어리의 코드를 잘게 쪼개고 각 코드 조각을 용도에 맞는 이름의 method 호출로 바꾸면, 코드의 용도가 분명히 드러남


#### 방법
* if 절을 별도의 method로 빼내자
* then 절과 else절을 각각의 method로 빼내자
