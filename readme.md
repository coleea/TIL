# TIL

=============================================

## 2021-03-28

### HTML5의 File API

`<input type="file">`로 명시된 HTMLInputElement API는 내부 속성인 files을 통하여 FileList API에 접근할 수 있다\
FileList API는 0개 이상의 파일 목록을 관리하는 유사 배열이다. 이들 각각의 요소는 File API의 인스턴스로 구성된다\
File API는 파일의 바이너리 데이터를 담고 있으며 window.atoi() 메소드를 이용하여 base64 포멧으로도 변환 가능하다\
\
File API에서 파일 정보는 Blob으로 구현되어 있다. 그러므로 File 생성자도 블롭을 인자로 받는다. 아래와 같다\
`new File([blob], "filename")`


### HTML5의 Base64 API

웹브라우저에서 이미지를 base64로 표현하고 싶을 때 두가지 경우로 나누어 생각할 수 있다
1. 로컬에서 File API로 불러온 이미지를 base64로 변환
2. 네트워크로 다운로드받은 이미지를 변환

로컬 이미지는 window.atoi()로 변환할 수 있다. 하지만 네트워크로 다운받은 파일의 base64변환은 조금 까다롭다
1. 먼저 fetch로 이미지를 다운로드 받는다
2. blob 객체를 생성한다. `fetch(url).then(response => response.blob())` 으로 생성할 수 있다
3. FileReader `API의 readAsDataURL(blob)` 메소드를 호출하면 blob이 base64 문자열로 변경된다

=============================================