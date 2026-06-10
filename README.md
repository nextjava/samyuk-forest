# 삼육대학교 숲해설 — Firebase Hosting 배포

6월의 나무 10종과 푸른 잎 놀이를 담은 한 장짜리 숲해설 사이트.

## 구조
```
forest-guide/
├─ public/
│  └─ index.html      # 사이트 본문 (배포 대상)
├─ firebase.json      # Hosting 설정
├─ .firebaserc        # 연결할 Firebase 프로젝트 ID
└─ .gitignore
```

## 배포 방법

### 1) 로그인 (최초 1회)
```bash
firebase login
```
브라우저 인증이 필요합니다. 터미널이 헤드리스인 경우:
```bash
firebase login --no-localhost
```

### 2) 프로젝트 연결
Firebase 콘솔(https://console.firebase.google.com)에서 프로젝트를 만든 뒤,
프로젝트 ID를 `.firebaserc`의 `YOUR_FIREBASE_PROJECT_ID` 자리에 넣거나:
```bash
firebase use --add        # 목록에서 선택해 default로 등록
```

### 3) 미리보기 (선택)
```bash
firebase emulators:start --only hosting   # http://localhost:5000
```

### 4) 배포
```bash
firebase deploy --only hosting
```
배포가 끝나면 `https://<프로젝트ID>.web.app` 주소가 출력됩니다.

## 콘텐츠 수정
`public/index.html` 한 파일만 고치면 됩니다. 수정 후 다시 `firebase deploy`.
