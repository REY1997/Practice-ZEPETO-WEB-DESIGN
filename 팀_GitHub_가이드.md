# 팀 GitHub 협업 가이드 🛠️

> 이 문서는 팀원 모두가 동일한 환경에서 마크업 작업을 할 수 있도록 작성된 가이드입니다.
> Mac 환경 기준으로 작성되었습니다.

---

## 목차
1. [Git & GitHub 설치](#1-git--github-설치)
2. [VS Code 설치 및 설정](#2-vs-code-설치-및-설정)
3. [프로젝트 코드 받기 (Clone)](#3-프로젝트-코드-받기-clone)
4. [공동 작업 방법](#4-공동-작업-방법)
5. [마크업 코드 규칙](#5-마크업-코드-규칙)
6. [자주 쓰는 명령어 모음](#6-자주-쓰는-명령어-모음)

---

## 1. Git & GitHub 설치

### 1-1. Homebrew 설치
터미널을 열고 아래 명령어를 붙여넣어 실행하세요.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

설치 중간에 `RETURN/ENTER` 키를 눌러 진행합니다.
설치가 끝나면 터미널에 안내되는 **Next steps** 명령어 3줄을 순서대로 실행하세요.

```bash
echo >> /Users/사용자이름/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv zsh)"' >> /Users/사용자이름/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv zsh)"
```

> ⚠️ `사용자이름` 부분은 터미널에서 안내해주는 실제 경로를 그대로 복사해 사용하세요.

설치 확인:
```bash
brew --version
```
버전 번호가 나오면 성공입니다.

---

### 1-2. Git 설치
```bash
brew install git
```

설치 확인:
```bash
git --version
```

---

### 1-3. GitHub 계정 설정
Git에 내 이름과 이메일을 등록합니다. (커밋 기록에 표시됩니다)

```bash
git config --global user.name "내 이름"
git config --global user.email "내 GitHub 이메일"
```

---

## 2. VS Code 설치 및 설정

### 2-1. VS Code 다운로드
[https://code.visualstudio.com](https://code.visualstudio.com) 에서 다운로드 후 설치합니다.

### 2-2. 추천 확장 프로그램
VS Code 좌측 Extensions 탭(네모 아이콘)에서 아래 확장을 설치하세요.

| 확장 이름 | 용도 |
|-----------|------|
| Prettier | 코드 자동 정렬 |
| ESLint | 코드 오류 감지 |
| Live Server | 브라우저 실시간 미리보기 |
| Korean Language Pack | VS Code 한국어 지원 |

---

## 3. 프로젝트 코드 받기 (Clone)

### 3-1. GitHub Personal Access Token 발급
GitHub는 비밀번호 대신 토큰을 사용합니다. **최초 1회만** 발급하면 됩니다.

1. GitHub 오른쪽 위 프로필 사진 클릭
2. **Settings** 클릭
3. 왼쪽 맨 아래 **Developer settings** 클릭
4. **Personal access tokens → Tokens (classic)** 클릭
5. **Generate new token (classic)** 클릭
6. Note에 이름 입력 (예: `my-mac`)
7. **repo** 체크박스 체크 ✅
8. **Generate token** 클릭
9. 생성된 `ghp_xxxx...` 토큰을 복사해 안전한 곳에 보관

> ⚠️ 토큰은 페이지를 벗어나면 다시 볼 수 없습니다. 반드시 저장해두세요!

---

### 3-2. 프로젝트 Clone
```bash
git clone https://github.com/팀계정/저장소이름.git
```

Username을 물어보면 GitHub 아이디, Password를 물어보면 위에서 발급한 토큰을 입력합니다.

---

## 4. 공동 작업 방법

### 매일 작업 시작 전 — 최신 코드 받기
```bash
git pull
```
반드시 작업 전에 실행해서 팀원의 최신 변경사항을 받아오세요.

---

### 작업 후 — GitHub에 올리기
```bash
git add .
git commit -m "작업 내용 요약"
git push
```

#### 커밋 메시지 작성 규칙
커밋 메시지는 어떤 작업을 했는지 알 수 있게 간결하게 작성합니다.

| 예시 | 설명 |
|------|------|
| `메인 헤더 마크업 완료` | 새로운 작업 완료 |
| `내비게이션 링크 수정` | 기존 코드 수정 |
| `푸터 불필요한 태그 삭제` | 코드 정리 |

---

### 작업 흐름 요약
```
git pull → 작업 → git add . → git commit -m "메모" → git push
```

---

## 5. 마크업 코드 규칙

팀 전체가 동일한 규칙으로 작업해야 코드를 함께 관리하기 쉽습니다.

### 들여쓰기
- **2칸 스페이스** 사용 (탭 사용 금지)

```html
<!-- ✅ 올바른 예 -->
<ul>
  <li>항목 1</li>
  <li>항목 2</li>
</ul>

<!-- ❌ 잘못된 예 -->
<ul>
    <li>항목 1</li>
</ul>
```

### 태그 및 속성
- 태그명과 속성명은 모두 **소문자** 사용
- 속성값은 반드시 **큰따옴표(`"`)** 사용

```html
<!-- ✅ 올바른 예 -->
<img src="image.jpg" alt="이미지 설명">

<!-- ❌ 잘못된 예 -->
<IMG SRC='image.jpg' ALT='이미지 설명'>
```

### 클래스 네이밍
- 단어 구분은 **하이픈(`-`)** 사용
- 의미 있는 이름 사용 (축약어 지양)

```html
<!-- ✅ 올바른 예 -->
<div class="main-header">
<button class="btn-submit">

<!-- ❌ 잘못된 예 -->
<div class="mainHeader">
<button class="btn1">
```

### HTML 구조
- `<!DOCTYPE html>` 선언 필수
- `lang` 속성 필수 (`ko` 사용)
- 이미지에는 반드시 `alt` 속성 작성

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>페이지 제목</title>
</head>
<body>
  ...
</body>
</html>
```

### 주석
- 섹션 구분 시 주석 사용

```html
<!-- header -->
<header>...</header>
<!-- //header -->

<!-- main -->
<main>...</main>
<!-- //main -->
```

---

## 6. 자주 쓰는 명령어 모음

| 명령어 | 설명 |
|--------|------|
| `git pull` | 최신 코드 받아오기 |
| `git status` | 현재 변경된 파일 확인 |
| `git add .` | 변경된 파일 전체 스테이징 |
| `git add 파일명` | 특정 파일만 스테이징 |
| `git commit -m "메모"` | 커밋 (저장) |
| `git push` | GitHub에 올리기 |
| `git log` | 커밋 기록 보기 |
| `git diff` | 변경 내용 확인 |

---

> 문서에 추가하고 싶은 내용이 있으면 팀장에게 알려주세요 😊
