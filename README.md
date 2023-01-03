# navigation
```
사용 언어 : Dart
프레임워크 : Flutter
개발 일시 : 2023.01.02 ~
기능 : 버튼을 통해 화면 전환하는 앱
개발자 : Won Chi Hyeon
```

### 새로운 화면으로 이동
```
새로운 화면을 띄우거나 이전 화면으로 돌아가는 방법을 알아보겠습니다.
두 화면을 내비게이션하는 앱을 만드는 것이 최종 목표입니다.
main.dart 파일에 두 화면에 해당하는 FirstPage와 SecondPage 클래스를 작성하였습니다.
각 화면에는 화면이동을 위한 ElvatedButton을 구성하고 이 버튼을 눌렀을 때 화면 전환이 되도록 합니다.
```
![image](https://user-images.githubusercontent.com/58906858/210201415-94b8a711-e0a3-40b3-a02f-f49294d267f6.png)

### push로 새로운 화면 호출
```
FirstPage를 수정하여 SecondPage로 전환하려면 Navigator 클래스의 push()메서드를 사용합니다.
첫 번째 인수로 context가 필요하고 두 번째 인수로 MaterialPageRoute 인스턴스가 필요합니다.
MaterialPageRoute 클래스의 builder 프로퍼티에 이동할 페이지를 나타내는 함수를 작성합니다.
MaterialPageRouter( builder: (context) => SecondPage()) 함수의 매개변수인 BuildContext의 타입은 
타입추론으로 생략이 가능합니다.

다음 페이지로 버튼을 탭하면 두 번째 페이지가 표시되고 별다른 코드를 추가하지 않아도
두 번째 페이지에는 AppBar의 leading 영역에 뒤로 가기 아이콘이 표시되며 이 아이콘을 탭하면 
이전 화면으로 이동하도록 자동으로 구성됩니다.
```
![image](https://user-images.githubusercontent.com/58906858/210202087-3b8927af-43a5-466e-b44f-12e5e53f2de4.png)
  
#### pop으로 이전 화면으로 이동
```
Navigator.push() 메서드로 새로운 화면이 표시되어도 이전 화면은 메모리에 남게 됩니다.
이때 Navigator.pop() 메서드로 현재 화면을 종료하고 이전 화면으로 돌아갈 수 있습니다.
```
![image](https://user-images.githubusercontent.com/58906858/210202412-cc893449-6e15-4d57-a517-4c1283fea5ab.png) 

#### 새로운 화면에 값 전달하기
```
새로운 화면을 표시하면서 데이터도 함께 전달하는 방법입니다.
이름과 나이 프로퍼티를 가지는 Person 클래스를 정의하고
FirstPage 클래스의 버튼 클릭 이벤트 부분을 수정합니다. 
SecondPage 클래스에서 Person 객체를 받도록 수정합니다. SecondPage({@required this.person});
```
![image](https://user-images.githubusercontent.com/58906858/210292296-8017ba18-3276-4004-8ed1-4a6ebf8586f9.png)

#### 이전 화면으로 데이터 돌려주기
```
FirstPage 클래스의 push 메서드는 Future 반환 타입을 가집니다.
Future 반환 타입을 가지려면 await 키워드를 메서드 앞에 추가하고
await 키워드를 사용하는 메서드의 인수와 함수 본문 사이에 async를 추가합니다.
두 번째 화면의 버튼을 탭하면 첫 번째 화면에서 'ok'를 출력하는 것을 확인할 수 있습니다.
```
![image](https://user-images.githubusercontent.com/58906858/210293860-2e1d394f-df22-436b-b262-fcb3b6f3dbca.png)
