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
다트 앱 실행시 main()함수가 시작된다.
https://user-images.githubusercontent.com/84646738/203331304-f56c1006-3199-468a-ab50-279ca8095798.jpg
