# SafeArea
디자인 한 UI가 어떤 기종에서든 잘 보여지도록 함.
<img src="https://user-images.githubusercontent.com/84646738/204072232-fd1ea174-f076-4fec-95d1-c467ef4397cd.png">
이렇게 하단이 잘리는 경우에 SafeArea로 감싸준다면
<img src="https://user-images.githubusercontent.com/84646738/204072252-d02174a1-3e23-4f17-bdb1-3aa16f7301e0.png">
이런 결과를 얻을 수 있다.

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
