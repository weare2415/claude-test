# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

한국어 명언을 랜덤하게 보여주는 정적 웹페이지입니다. 빌드 프로세스나 외부 의존성 없이 단일 HTML 파일로 구성되어 있습니다.

## 로컬 실행

브라우저에서 직접 열기:
```
start index.html
```

로컬 서버 사용:
```
python -m http.server 8000
npx serve
```

## 아키텍처

**단일 파일 구조**: 모든 HTML, CSS, JavaScript가 `index.html`에 포함됨

**데이터 구조**:
- `quotes` 배열에 20개의 명언 객체 저장 (149-230행)
- 각 객체는 `text`와 `author` 속성 포함

**주요 함수**:
- `getRandomQuote()`: 중복 방지 로직으로 랜덤 명언 표시 (234-246행)
- `shareQuote()`: Web Share API 또는 클립보드 복사로 명언 공유 (248-262행)
- `copyToClipboard()`: 클립보드 복사 및 알림 표시 (264-272행)

**스타일링**:
- 컬러 스킴: `#667eea` → `#764ba2` 그라데이션
- 반응형: 768px 브레이크포인트 (107-128행)
- Flexbox 레이아웃 (버튼, 연락처 정보)
- CSS 애니메이션: 버튼 hover 효과 (92-98행)

**명언 추가 방법**:
`quotes` 배열에 `{text: "명언 내용", author: "저자명"}` 형식으로 추가
