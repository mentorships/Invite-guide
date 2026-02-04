# 🛡️ Mentorships Repo 초대 가이드
멘토링 및 강의 자료는 GitHub Private Repository로 관리됩니다.  
초대를 자동화하기 위해 별도의 API를 제공하오니, 아래 가이드를 따라 초대 요청을 진행해주세요.

※ 참고: 자료를 파일로만 공유할 경우 분실 시 재다운로드가 어려울 수 있어, GitHub를 통해 언제든 다시 받아보실 수 있도록 저장소 초대 방식을 선택했습니다.

<br/>

## 🔗 Base URL
https://mentorships.anb-network.com

<br/>

## 💼 사전 준비
|항목|설명|
|:--:|:--:|
|GitHub Username|본인의 GitHub 프로필에 있는 사용자명 (아래 참고 이미지)|
|Repository 이름|수업 시 전달 예정|
|X-API-KEY|수업 시 전달 예정|

<br/>

## 🚀 사용 방법
### 동영상: https://youtu.be/t4NrAYhkmcc
### 1. Swagger UI 사용하기
* Swagger UI 접속
* 우측 상단 "Authorize" 클릭 → X-API-KEY 입력 후 Authorize
* POST /invite/ → Try it out 클릭
* 아래와 같이 요청 바디 입력:
  ```json
  {
    "username": "자신의 github username",
    "repo": "전달드린 repo값"
  }
  ```
* Execute 클릭 → 응답이 201인지 확인
* 사용하시는 email에 접속하여 메일을 확인하세요: ruby-kim invited you to mentorships/{repo 이름}
* View invitation 이후 Accept을 누르면 수업 자료를 받으실 수 있습니다.

### 2. 직접 Endpoint 사용하기
#### `POST` /invite/
#### Request Body
```json
{
  "username": "자신의 github username",
  "repo": "전달드린 repo값"
}
```
#### Headers
|헤더 이름|값 예시|설명|
|:--:|:--:|:--:|
|Content-Type|application/json|요청 본문은 JSON 형식이어야 합니다|
|X-API-KEY|수업 시 전달 예정|각 repo에 매핑된 고유 API Key 입니다.|
* Response가 201로 나오는지 확인
* 사용하시는 email에 접속하여 메일을 확인하세요: `ruby-kim invited you to mentorships/{repo 이름}`
* View invitation 이후 Accept을 누르면 수업 자료를 받으실 수 있습니다

<br/>

## 🧾 응답 코드 요약
|코드|설명|
|:--:|:--:|
|201|초대 성공 (확인 이메일 전송됨)|
|204|이미 초대된 사용자|
|400|필수 값 누락 (username 또는 repo)|
|403|금지된 repo 또는 API Key 오류|
|500|서버 내부 오류|

<br/>

## 📩 문의
문의사항은 아래로 연락 부탁드립니다:<br/>
**dev.rubykim@gmail.com**
