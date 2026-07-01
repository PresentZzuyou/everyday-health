# Everyday Health 작업 규칙

- 작업 파일은 `health_calendar.html`만 수정한다.
- `index.html`은 자동 생성 파일이므로 직접 수정하지 않는다.
- 단일 HTML 파일 구조이며 CSS, JS, HTML이 모두 포함되어 있다.
- 외부 라이브러리 없이 바닐라 JS로 작업한다.

## 주요 전역 변수

- `selExercises`: 현재 선택된 운동 이름 Set
- `perExSets`: 운동별 세트 데이터 객체
- `selParts`: 선택된 운동 부위 Set
- `data`: 날짜별 운동 기록 localStorage 저장 객체

## UI 패턴

- 모달은 `.overlay + .modal` 구조를 따른다.
- 운동 목록 행은 `.ex-list-row`, 선택 시 `.sel` 클래스를 토글한다.
- 세트 입력 박스는 `.ex-sets-mr`를 사용한다.
- 근력 입력은 `makeSetInpRow`, 유산소 입력은 `makeCardioInpRow`를 사용한다.
- 화면 갱신 시 `renderPartBtns()`, `renderExGrid()`를 호출한다.
