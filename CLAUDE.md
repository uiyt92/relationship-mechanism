# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

프레젠테이션/인터랙티브 콘텐츠용 standalone HTML 파일 모음. 빌드 도구 없이 브라우저에서 직접 열어 확인.

## 기술 스택

- HTML + CSS + vanilla JS (빌드 도구 없음)
- 폰트: Pretendard, Montserrat, Apple SD Gothic Neo
- 일부 파일에서 Tailwind CDN, Font Awesome CDN 사용
- 이미지/영상은 같은 디렉토리에서 상대 경로로 참조

## 디자인 패턴

- **모바일 세로형 (9:16)** 중심 레이아웃 — max-width 380~500px
- 다크 테마 기본 (`#000`, `#141416` 계열 배경)
- 클릭/터치 기반 순차 표시, CSS 애니메이션
- **애니메이션은 자동 진행 금지** — 반드시 버튼 클릭 또는 방향키/엔터 입력으로만 실행되도록 구현
- `관계의 메커니즘.html`은 자체 디자인 토큰(`:root` CSS 변수) 사용 — 새 슬라이드 추가 시 기존 토큰 재활용
