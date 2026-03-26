# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

프레젠테이션/인터랙티브 콘텐츠용 standalone HTML 파일 모음. 빌드 도구 없이 브라우저에서 직접 열어 확인.

## 기술 스택

- HTML + CSS + vanilla JS (빌드 도구 없음)
- 폰트: Pretendard, Montserrat, Apple SD Gothic Neo
- 일부 파일에서 Tailwind CDN, Font Awesome CDN 사용
- 이미지/영상은 `images/` 폴더에서 상대 경로로 참조

## 디자인 패턴

- **모바일 세로형 (9:16)** 중심 레이아웃 — max-width 380~500px
- 다크 테마 기본 (`#000`, `#141416` 계열 배경)
- 클릭/터치 기반 순차 표시, CSS 애니메이션
- **애니메이션은 자동 진행 금지** — 반드시 버튼 클릭 또는 방향키/엔터 입력으로만 실행되도록 구현
- `관계의 메커니즘.html`은 자체 디자인 토큰(`:root` CSS 변수) 사용 — 새 슬라이드 추가 시 기존 토큰 재활용

## 파일 구조

```
ppt/
├── 관계의 메커니즘.html    # 메인 프레젠테이션 (32+ 슬라이드)
├── 카톡창.html             # 카카오톡 채팅 시뮬레이션
├── CLAUDE.md
├── analytics/              # 카피라이팅 분석 문서
│   └── upselling-analysis.md
└── images/                 # 모든 이미지/영상 에셋
    ├── meetup1~4.jpg       # 간담회 사진
    ├── kakao_screenshot*.png # 카톡 피드백 스크린샷
    ├── feedback1.png        # 피드백 이미지
    ├── jang_wonyoung.jpg
    ├── QR.png
    └── Video_moving_for_*.mp4
```

## 슬라이드 네비게이션 시스템

- `goNext()` / `goPrev()` — 키보드/클릭 네비게이션
- `data-substeps` 속성 — 슬라이드 내 서브스텝 수 지정
- `.substep` 클래스 — 순차 표시 요소
- `isFeedbackSlide()` → `handleFeedbackSubstep()` — 피드백 슬라이드 커스텀 애니메이션
- `partMap` — 슬라이드 ID → 파트 번호 매핑 (진행률 표시용)

## Git / 배포

- GitHub Pages: master 브랜치에서 자동 배포
- Remote: `https://github.com/uiyt92/relationship-mechanism.git`
- 수정 시 자동 commit + push
