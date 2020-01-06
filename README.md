# React Native로 만드는 날씨 앱



이 강의로 배우는 것

- 크로스 플랫폼 ios, 안드로이드 앱을 만든다.

- 리액트와 결합된 자바스크립트 그리고 엑스포의 파워를 이용해 만듭니다.

- 휴대폰의 geolocation에 접근하고, 그것을 api에 보낸 다음 날씨에 따라 스크린을 덮을 것이다.

- 아이콘을 어떻게 작업하는지, 레이아웃 시스템, 나의 현재 위치를 갖고 어떻게 작동하는지 배운다.
- 데이터와 어떻게 작업하는지도 배울 것이다.



## 설치할 것

- node.js
  - `node -v` 로 확인했을 때 버전이 10이상이어야 함
- npm
  - `npm -v`로 확인했을 때 버전이 6이상이어야 함
- [선택] Android studio 또는 Xcode
  - 위 두가지의 설치를 원치 않다면 Expo로 핸드폰으로 작업할 수 있다.
  - Expo는 AppStore/Playstore에서 다운로드

- `npm install -g expo-cli`
  - 참고 : https://facebook.github.io/react-native/docs/getting-started

 

## Expo란 무엇인가?

Expo는 무엇이고 React Native와 무슨 관련이 있을까?

기본적으로 Expo는 `create--react-app`과 같은 것인데 그 위에 더 많은 것들을 가지고 있다.

리액트 네이티브를 위한 설정 파일같은 것들이 없는 방식으로, 모든 것이 셋업이 되어있다.



만약 리액트 네이티브를 수동으로 작업하고 싶다면 `React Native Cli Quick start`를 클릭해야한다.

이것은 커맨드라인 인터페이스이고, node, watchman, react-native-cli 등을 설치해야한다.

한마디로 이 방식은 native files들을 더 많이 컨트롤 하고 싶을때를 위한 것이다.

즉, react native CLI로 작업할 때 나 대신 Android studio 또는 Xcode 파일을 생성하고, 양쪽 파일들이 리액트 네이티브에서 실행될 것이다. 나는 양쪽 파일들에 다 접근을 할 수 있기 때문에, 어떤 때는 둘을 결합할 수도 있을 것이다.



반대로 expo는 모든 native files들을 숨기고 모든 것을 관리해준다.

가장 큰 장점은 휴대폰에서 앱을 테스트 할 수 있다는 것이다.

단점은 native files들을 크게 제어할 수 없다는 점이다.



이제 Expo(https://expo.io/)에 계정을 생성하고 로그인해보자. 

expo는 더 나은 개발자 경험을 제공하고, 내가 앱을 만드는 방식을 처리해준다.

simulation, react native update 등을 처리해주고, 더 많은 API를 제공하며, 문서도 정리가 잘되어있다.

그러므로 expo는 수동적인 작업들이 덜 필요하고, 시작하는데 더 빠른 방식이다.





## 프로젝트 시작하기

원하는 경로로 가서 아래의 코드를 실행한다.

```react
$ expo init [프로젝트명]
```

코드를 실행하면 몇가지를 물어보는데, 



<u>1) blank or blank(TypeScript) or Tabs or bare-minimum</u>

expo가 자동생성을 할 수 있기 때문이다.

우리는 zero부터 시작할 것이기 때문에 **blank를 선택**한다.



<u>2) 프로젝트 생성</u>

```
"name" : "[프로젝트명 입력]"
```



<u>3) Yarn install 할 지의 여부</u>

 npm이랑 같은 것이기 때문에 npm을 사용하도록 한다. **n** 입력