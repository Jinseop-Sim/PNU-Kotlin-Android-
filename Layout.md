# Layout
---
## What is Layout?
> View를 배치하는 상위 Class이고, View를 배치하는 규칙이 된다.  

## Layout의 종류
- Linear Layout : 선형으로 View를 배치한다.
- Relative Layout : View 간의 상대 위치에 따라 배치한다.
- Frame Layout : View들을 겹쳐서 배치한다.
- Grid Layout : 표 형태로 View들을 배치한다.
- Constraint Layout : 계층 구조로 View들을 배치한다.

### Linear Layout
> View를 가로(Horizontal) 혹은 세로(Vertical)로 나열하는 Layout Class이다.  
- ```android: orientation```
  - Horizontal : View를 가로로 나열한다.
  - Vertical : View를 세로로 나열한다.
- ```android: layout_weight```
  - View에 가중치를 주는 속성이다.
  - 각 Component의 크기를 비율에 따라 조정하며, 여백을 자동으로 채워준다.  
  ![image](https://user-images.githubusercontent.com/71700079/162603005-588d6319-65a2-46fc-97e4-d6a8806bc2a9.png)  
- ```android: layout_gravity```
  - View를 왼쪽, 가운데, 오른쪽 등으로 정렬할 때 사용하는 속성이다.
  - Default 값은 Left + Top(왼쪽 상단)이 된다.
  - Layout_gravity : 위젯이 들어가는 영역을 정렬한다.
  - Gravity : View 내부의 콘텐츠를 정렬한다.
  ![image](https://user-images.githubusercontent.com/71700079/162603124-dac245dd-7298-4b4b-907c-c5eb575f6b22.png)  
- Nested Layout : Layout도 클래스이므로 Layout 내에 포함시킬 수 있다.  
![image](https://user-images.githubusercontent.com/71700079/162602810-915872c7-a58f-4dc3-9830-417e092ede05.png)  

### Relative Layout
> View에 대해 상대적인 위치에 다른 View를 배치하는 Layout Class.
- 기준이 되는 View는 반드시 id가 선언되어있어야 한다.
```XML
<ImageView android:id = "@+id/image"
           android:layout_width="wrap_content"
           android:layout_height="wrap_content"
           android:layout_centerInParent="true"/> 
<!-- 부모 Layout의 정 가운데에 배치-->
<Button android:layout_width="30dp"
        android:layout_height="30dp"
        android:layout_alignTop="@id/image"
        android:layout_toLeftOf="@id/image"
        android:text="toLeftOf &amp; alignTop"/>
<!-- XML Entity &amp -->
```
- Layout_centerInParent(Top, Bottom) : 부모 Layout에 배치할 때, 어느 위치에 배치할 지 정한다.
- AlignTop(Bottom) : 상대 View의 위치가 기준 View의 상단이나 하단에 맞추어 정렬된다.
- ToLeftOf(Right) : 상대 View에 대해 왼쪽이나 오른쪽에 위치한다.   

### Frame Layout
> View를 겹쳐서 출력할 수 있는 Layout이다.  

- View를 추가한 순서대로 위에 계속 겹쳐서 출력한다.
- 겹쳐진 View 중에서 특정 순간 하나의 View만 출력하고 싶을 때 사용한다.
- Activity Code에서 원하는 순간에 View의 Visibility 속성 값을 바꾸어서 조절할 수 있다.

### Grid Layout
> 행과 열로 구성된 Table 화면을 만드는 Layout이다.  

- Grid Layout의 배치 규칙
  - Orientation : Vertical, Horizontal로 가로 / 세로 배치를 정한다.
  - Rowcount / ColumnCount : 가로 / 세로로 몇 개의 칸을 배치할 지를 정한다.
- Grid Layout의 특정 View 위치 조정
  - layout_row(column) : View가 위치할 가로 / 세로 방향 Index를 지정할 수 있다.
- Grid Layout의 특정 View의 크기 확장 및 병합
  - layout_gravity : 특정 View를 확장해서 출력한다.
    - ```Fill, Fill_horizontal, Fill_vertical``` 등 옵션이 존재한다.
  - layout_columnSpan(row) : 가로 / 세로로 Table을 병합한다.
