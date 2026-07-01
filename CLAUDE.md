# Everyday Health — 프로젝트 가이드

## 개요
모바일 웹 헬스 캘린더 앱. 운동·식단·수면·체중 등을 날짜별로 기록하는 싱글페이지 앱.

## 파일 구조
- **`health_calendar.html`** — 유일한 소스 파일. **항상 이 파일만 편집할 것.**
- `index.html` — 자동 생성본 (훅이 덮어씀, 직접 편집 금지)
- `/tmp/index.html` — 미리보기 서버용 복사본 (훅이 자동 동기화)

## PostToolUse 훅 (자동 배포)
`health_calendar.html` 편집 시 자동으로:
1. `health_calendar.html` → `index.html` 복사
2. `index.html` → `/tmp/index.html` 복사
3. `git add -A && git commit -m "update" && git push`

## 미리보기 서버
- 포트: 3456
- 서빙 디렉터리: `/tmp` (preview_start 하드코딩)
- localhost:3456에서 `/tmp/index.html` 서빙

## 기술 스택
- 바닐라 JS / HTML / CSS 단일 파일, 외부 라이브러리 없음
- 한국어 UI, 모바일 우선 (max-width 430px)
- 폰트: Poppins (영문), Pretendard (한글)

## 핵심 전역 상태
| 변수 | 타입 | 설명 |
|------|------|------|
| `selExercises` | Set | 선택된 운동 종목명 |
| `perExSets` | Object | 종목별 세트 데이터 |
| `selParts` | Set | 선택된 신체 부위 |

## UI 갱신 함수
- `renderPartBtns()` — 부위 버튼 목록 다시 그리기
- `renderExGrid()` — 운동 종목 그리드 다시 그리기
- 운동 선택/해제 후 반드시 두 함수 모두 호출

## 디자인 토큰 (CSS 변수)
```
--bg, --surface, --surface-2, --inset
--text, --text-2, --text-3
--lime, --lime-deep
--btn-bg, --btn-text
--line, --line-strong
```

## 주의사항
- `index.html`은 절대 직접 편집하지 말 것 (훅이 덮어씀)
- 편집은 반드시 `health_calendar.html`만
- 모바일 앱 스타일이므로 스크롤바는 숨김 처리 (`scrollbar-width:none`)
