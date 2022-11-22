# 인텔리제이에서 플러터 환경 설정하기

1. Android SDK 설치
Setting > Android SDK > Edit
SDK Components 체크 > Next > Finish

2. Flutter 플러그인 설치
Setting > Plugins > Marketplace > Flutter 검색, 설치
Dart도 같이 설치하면 됨.

3. Flutter SDK 설치
https://flutter.dev/docs/get-started/install
!주의 : zip 압축 풀기시 Program Files 아래 위치하면 안됨.
Setting > Flutter > Flutter SDK 위치를 압축 푼 경로로 지정.

4. Flutter 프로젝트 생성
Project name은 소문자 언더바 구분으로 입력할 것.
test_flutter(o)

5. AVD(Android Virtual Device) 생성 및 실행
Tools > Android > AVD Manager 실행
Create Virtual Device 클릭
Phone > Pixel 2 선택하고 Next
API 30 Download > 완료 후 Next > Finish > Actions의 실행 버튼 클릭시 AVD가 구동 됨.

6. Pubspec.yaml 파일 열고 상단의 Pub get 클릭 > main.dart 열람 문제 해결됨.

# 시작 프로젝트 뜯어보기

<img src="https://user-images.githubusercontent.com/84646738/203331304-f56c1006-3199-468a-ab50-279ca8095798.jpg"><br>
다트 앱 실행시 main()함수가 시작된다.<br>
runApp은 플러터 앱을 시작하는 역할을 한다.<br>
이 함수에 플러터 앱을 시작하면서 화면에 표시할 위젯을 전달한다.<br>

<img src="https://user-images.githubusercontent.com/84646738/203332125-30988400-2f64-439a-b10f-8982460b7d32.jpg"><br>
위젯으로 전달된 MyApp 클래스 정의 코드이다.<br>
StatelessWidget 클래스는 상태가 변경되지 않는 위젯이다.<br>
@override 애노테이션으로 build() 메서드를 재정의한다.<br>
build() 메서드는 어떤 위젯을 만들 것인지 정의하는 부분이다.<br>
<br>
runApp()을 이용해 클래스를 실행할 때는 MaterialApp() 메서드를 반환해야 한다.<br>
MaterialApp() 메서드에는 title, theme, home등이 정의되어 있다.<br>
title : 앱 이름<br>
theme : 앱 테마<br>
home : 어플 실행시 첫화면에 표시될 내용<br>
visualDensity : 어플이 어떤 플랫폼에서도 잘 보이도록 지원.<br>
<br>
플러터 앱을 구성하는 위젯은 stateless 와 statefull 두 가지로 구분된다.<br>
이 두가지는 상태 연결과 관련이 있다.<br>
상태를 연결할 필요가 없는 위젯을 stateless widget 이라고 하며 StatelessWidget 클래스를 상속받아 만든다.<br>
상태를 연결할 필요가 없다는 말은 앱이 위젯의 상태를 감시하지 않아도 된다는 말이다.<br>
정적인 화면(내용이 갱신되지 않는 화면)을 보여줄 때는 앱이 위젯의 상태를 감시하지 않아도 된다.<br>
<br>
상태가 연결된 동적인 위젯을 statefull widget 이라고 하며 StateFullWidget 클래스를 상속받아 만든다.<br>
내용을 갱신해야할 때 즉, 앱이 위젯의 상태를 감시하다가 위젯이 특정 상태가 되면 알맞은 처리를 해야할 때 사용한다.<br>
당연히 statefull widget이 자원을 더 많이 사용한다.<br>
