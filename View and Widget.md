# View and Widget
---
## View
> View란?  
> App의 실행화면을 구성하는 모든 요소들을 통틀어 View라고 한다.  

- 예를 들면, ```LinearLayout```, ```Button```, ```TextView``` 같은 것들이 모두 View에 해당하는 것이다.
- Widget
  - View의 요소 중에 시각적인 요소이다.
  - ex) ImageView, TextView, Button..
- ViewGroup
  - View 중에 영역적인 요소이다.
  - Layout, Container
- View의 요소 배치
  - View의 요소 배치는 XML 언어로 수행된다.
  - 모든 View 요소는 Layout 태그 내에 포함되어야한다.
- View Attribute
  - View 요소에는 갖가지 속성을 부여할 수 있다.
  - 그 중 크기 속성(width, height)은 반드시 들어가야만 하는 속성이다.
  - 시각 표현 관련 속성을 통해서 태그를 화면에 다양하게 표현할 수 있다(색상, 회전..).
  - Android Studio에는 크기를 직접 지정하거나, 참조할 수 있다.
    - match_parent : 상위 요소의 공간 범위를 참조한다.
    - wrap_content : 본인 및 하위 요소의 텍스트 문자 크기를 참조한다.
    - 지정 값 (단위) : Widget은 dp를 쓰며, 텍스트는 sp를 쓴다.
- View의 영역
  - View의 영역은 아래와 같이 Context, Padding, Margin으로 구분된다.  
  ![image](https://user-images.githubusercontent.com/71700079/160574407-42e5f0be-d33b-4fab-9484-2cafa0079c4a.png)  
  - Padding은 Widget의 경계선으로 부터, Widget 내부의 요소가 멀어지도록 여백을 설정한다.
  - Margin은 Widget의 경계산 밖으로, 부모 태그로부터 Widget이 멀어지도록 여백을 설정한다.  
  ![image](https://user-images.githubusercontent.com/71700079/160574607-14bdb4f1-94af-46b9-bcf8-65b0b1b99bdd.png)  

### View Attribute
- View Color : 아래와 같이 View 요소의 색을 결정할 수 있다.
```XML
<Button
        android:backgroundTint="#00FF00"/>
```
- View Rotation : 아래와 같이 회전 또한 가능하다.
```XML
<Button
        android:rotation="20"/>
```
- View Visibility : 아래와 같이 View의 가시성을 조절할 수 있다.
```XML
<Button
        android:visibility="invisible"/> // 자리는 차지하지만 보이지 않는다.
<Button
        android:visibility="gone"/> // 자리도 차지하지 않고, 보이지 않는다.
<Button
        android:visibility="visible"/> // 보인다.
```
- View enable
```XML
<Button
        android:enabled="true"/>
<Button
        android:enabled="false"/> // 버튼이 활성화 되지 않아, 클릭이 되지 않는다.
<Button
        android:clickable="true"/>
<Button
        android:clickable="false"/> // 버튼이 클릭이 활성화되지 않는다.
```

## Widget & Algorithm
> Widget은 구성된 Algorithm을 시작하는 Trigger 역할을 수행할 수 있다.  
> 따라서 우리는 Algorithm과 Widget을 연결해 줄 필요가 있다.  

- Widget의 등록 : 아래와 같이 각 Widget마다 id를 등록해주어야 한다.
```XML
<Button
        ...
        android:id="@+id/BtnAdd"/>
<Button
        ...
        android:id="@+id/BtnSub"/>
```
- Widget의 연결(Kotlin) : MainActivity File에서 Widget을 연결해줄 수 있다.
```Kotlin
class MainActivity : AppCompatActivity(){
  lateinit var btnAdd : Button; lateinit var btnSub : Button
  
  override fun onCreate(savedInstanceState: Bundle?){
    btnAdd = findViewById(R.id.BtnAdd) // 아까 등록했던 id를 통해서 View를 참조한다.
    btnSub = findViewById(R.id.BtnSub)
    
    btnAdd.setOnClickListner{ view -> 
      // 더하기 알고리즘이 들어가고, 
      false // 이 값이 true이면, 받은 Click을 없애버리고
            // False이면, 다른 곳에서도 사용할 수 있도록 받은 Click을 남겨두겠다는 의미이다.
    }
  }
}
```
