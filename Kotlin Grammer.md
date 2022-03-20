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
- 기본적으로 위와 같이 함수를 선언한다.

## Collection Data Type(Array, List)
```Kotlin
fun main(){
  var list1: Array<Int> = arrayOf(1,2,3,4,5,6,7,8)
  var list2: List<Int> = listOf(1,2,3,4,5,6,7,8)
  var list3: MutableList<Int> = mutableListOf(1,2,3,4,5,6,7,8)
  
  list1 = list1.plus(9) // 배열 뒤에 새 값을 추가한다.
  list2 = list2.plus(9) // List 뒤에 새 값을 추가한다.
  list3.add(9) // MutableList 뒤에 새 값을 추가한다.
  
  val filtered_list1 = list1.filter{it%3 == 0} // 3가지 List엔 모두 Filter 기능 적용이 가능하다.
  val filtered_list2 = list2.filter{it%3 == 0} // 반복문을 돌아 3의 배수들만 새 배열에 저장한다.
  val filtered_list3 = list3.filter{it%3 == 0}
}
```
- 위와 같이 배열들을 선언하고 이용할 수 있다. 
  - List는 Immutable하다. 읽기 전용이기 때문이다.
  - MutableList를 사용해야 Mutable하게 List를 사용할 수 있다.
- 위의 Data Type들 말고도, Set, Map 등의 Collection Data Type들이 있다.

## Condition
- 조건문은 기본적으로 Java의 ```if, if-else```문이 존재한다.
- 특이한 점은 ```switch```문이 아닌 ```when```문을 이용하는 것!
```Kotlin
when(ranking/5){
  0 -> idx = 0
  1 -> idx = 1
  2 -> idx = 2
  3 -> idx = 3
}
```
- 위와 같이 ```switch```문과 같은 동작을 하는 ```when```문을 구현한다.\

## Loop
- ```While```문은 기본적으로 Java와 동일한 동작을 한다.
- 하지만 ```for```문은 Python과 유사하게 사용을 한다고 보면 되겠다.
