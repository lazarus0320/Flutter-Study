# SafeArea
디자인 한 UI가 어떤 기종에서든 잘 보여지도록 함.<br>
<img src="https://user-images.githubusercontent.com/84646738/204072232-fd1ea174-f076-4fec-95d1-c467ef4397cd.png"><br>
이렇게 하단이 잘리는 경우에 SafeArea로 감싸준다면<br>
<img src="https://user-images.githubusercontent.com/84646738/204072252-d02174a1-3e23-4f17-bdb1-3aa16f7301e0.png"><br>
이런 결과를 얻을 수 있다.<br><br>

SafeArea의 위젯이 MediaQuery를 통해 앱의 실제 화면 크기를 계산하고 이를 영역으로 삼아 내용을 표시하기 때문에 잘리는 부분없이 전부 나올 수 있는 것임.

```dart
import 'package:flutter/material.dart';
void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  static const String _title = 'CheckboxListTile Example';

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: _title,
      home: Scaffold(
        appBar: AppBar(title: const Text(_title)),
        body: SafeArea(
          child: ListView(
            scrollDirection: Axis.vertical,
            children: <Widget>[
              ListTile(
                leading: Icon(Icons.home),
                title: Text('Home'),
                trailing: Icon(Icons.navigate_next),
                onTap: (){},
              ),
              ListTile(
                leading: Icon(Icons.home),
                title: Text('Home'),
                trailing: Icon(Icons.navigate_next),
                onTap: (){},
              ),
            ],
          ),
          top: true,
          bottom: true,
          right: true,
          left: false,
          maintainBottomViewPadding: false,
        ),
      )
    );
  }
}
```
<img src = "https://user-images.githubusercontent.com/84646738/204074143-d46b6dbd-3186-4460-9703-0a21c1d90aea.jpg">

# Scafold
MaterialApp은 Material Design Pattern으로 하위 페이지나 구성 요소를 담는 그릇이라고 볼 수 있다.(Material Design은 구글에서 만든 디자인 스타일, 혹은 컨셉임.)<br>
그 중 home이라는 옵션은 앱의 화면 구성을 담당하는 부분이다.
<br><br>
<b>Scaffold</b>
기본적인 앱에서 디자인적인 뼈대를 구성하는 위젯이다.
앱 전반적인 디자인에 대한 다양한 속성들을 활용할 수 있다.
* appBar : 화면 상단 바에 대한 설정
* body : 메인 화면 부분

# child/children
특정 컨테이너의 하위 위젯을 넣으려면 child/children으로 할당해주면 된다.
하나만 넣으려면 child, 여러개면 children이다.
위의 코드에서는 body에 ListView 하나만 들어가므로 child로 넣었고, ListView에 ListTile이 복수로 들어갔기 때문에 children으로 넣었다.

# ListTile/ListView
ListView : 항목들을 행으로 나열함.
ListTile : 각 항목에 대한 열의 항목들을 나열함.(아이콘, 텍스트 등)

```dart
import 'package:flutter/material.dart';
void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  static const String _title = 'CheckboxListTile Example';

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: _title,
      home: Scaffold(
        appBar: AppBar(title: const Text(_title)),
        body: SafeArea(
          child: ListView(
            children: <Widget>[
              ListTile(
                leading: Icon(
                  Icons.home,
                  color: Colors.grey[850],
                ),
                title: Text('home'),
                onTap:(){
                  print('Home pressed');
                },
              ),
              ListTile(
                leading: Icon(
                  Icons.image,
                  color: Colors.grey[850],
                ),
                title: Text('view Image'),
                onTap:(){},
                trailing: Icon(Icons.arrow_forward_ios),
              ),
              ListTile(
                leading: Icon(
                  Icons.border_color,
                  color: Colors.grey[850],
                ),
                title: Text('글쓰기'),
                onTap: (){},
                trailing: Icon(Icons.arrow_forward_ios),
              )
            ]
          )
        ),
      )
    );
  }
}
```
<img src = "https://user-images.githubusercontent.com/84646738/204074750-41b59cf6-f383-4c78-8b9c-a03c9b37fac7.jpg"><br>
* leading : 아이콘
* title : 텍스트
* onTap : 항목을 누를경우 수행되는 메서드
* trailing : title 뒤에 할당할 위젯에 대한 속성. 보통 Icon 위젯이 따라옴.
  상단의 코드에서는 Icon(Icons.arrow_forward_ios)를 넣음으로써 > 모양 아이콘이 title 다음으로 할당되는 것을 확인할 수 있음.
  
