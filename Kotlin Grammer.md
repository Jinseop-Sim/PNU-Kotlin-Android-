# Kotlin Grammer
---
> 기본적인 Kotlin 문법에 대해서 알아보자.  
> 기본적으로 Java 기반의 언어이기 때문에 매우 유사하다.  

## Kotlin의 특징
- 앱 개발을 위해 만들어진 언어이다 보니, 앱 실행에 대한 안정성이 매우 우수하다.
- 비정상 종료의 원인이 되는 NullPointerException을 완화하기 위한 Null Safe가 지원된다.

## 변수의 선언
- 변수는 기본적으로 두 가지 선언법이 있다.
- ```var num: Int``` : Mutable한 변수를 선언한다.
- ```val num: Int``` : Immutable한 변수를 선언한다.
  - 특이하게 변수의 Type 선언을 변수 이름 뒤에 선언한다.

## 함수의 선언
```Kotlin
fun plus(number1: Int, number2: Int): String{
  var sum = (number1 + number2).toString()
  return "두 값을 더하면? " + sum
}
```
