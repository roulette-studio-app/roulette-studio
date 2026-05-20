# Roulette Studio

브라우저에서 룰렛 프로젝트를 만들고, Google 로그인으로 Firebase Firestore에 자동 동기화하는 정적 웹앱입니다.

## 파일 구성

- `index.html`: 화면 구조
- `styles.css`: 스타일
- `app.js`: 룰렛, 로그인, Firestore 동기화 로직
- `firestore.rules`: Firebase Firestore 보안 규칙

## Firebase 설정

1. Firebase Authentication에서 Google 로그인을 켭니다.
2. Firestore Database를 생성합니다.
3. Firestore Rules에 `firestore.rules` 내용을 적용합니다.
4. `firebase-config.js`의 `null`을 Firebase 웹 앱 설정 객체로 바꿉니다.
5. 앱 화면에서 Google 로그인하면 내 룰렛은 자동 동기화됩니다.

예:

```js
window.ROULETTE_FIREBASE_CONFIG = {
  apiKey: "...",
  authDomain: "...",
  projectId: "...",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
```

## 배포

GitHub에 이 파일들을 올린 뒤 GitHub Pages, Netlify, Vercel 중 하나로 정적 사이트 배포를 연결하면 됩니다.

배포 후 Firebase Authentication의 승인된 도메인에 배포 도메인을 추가해야 Google 로그인이 작동합니다.

## 공유 워크스페이스

- 내 룰렛: 같은 Google 계정으로 로그인한 기기끼리 자동 동기화합니다.
- 공동작업 룰렛: `룰렛 공유`로 링크와 비밀번호를 만들고, 링크를 받은 사용자가 Google 로그인 후 비밀번호를 입력하면 함께 읽고 수정합니다.
