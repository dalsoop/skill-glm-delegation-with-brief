## 작업: [앱명] blade 뷰 [N]개 [기능] 추가

### 1. 파일 목록

| 동작 | 경로 | 역할 |
|------|------|------|
| 수정 | resources/views/[경로].blade.php | [변경 내용] |
| 수정 | resources/views/partials/[이름].blade.php | [변경 내용] |
| 수정 | packages/[패키지]/resources/views/components/[이름].blade.php | [컴포넌트 변경] |
| 수정 | packages/[패키지]/resources/css/components.css | [스타일 추가] |

### 2. 스펙

[컴포넌트/뷰]에 추가할 내용:
- [HTML 구조 상세 — 태그, class, 속성]
- [동적 데이터: $variable 이름 + 타입]
- [조건부 표시: @if 조건]

CSS:
- [클래스명 + 속성]
- [반응형: @media 조건]

### 3. 제약

- Blade 문법 (@if, @foreach, {{ }})
- 기존 CSS 변수 사용 (새 변수 금지)
- 기존 컴포넌트 (x-gujo::*) 활용
- 접근성: aria-label, semantic HTML

### 4. 하지 말 것

- Controller/Model 수정 (별도 위임)
- JavaScript 인라인 추가 (별도 파일로)
- 기존 스타일 덮어쓰기
- 하드코딩 문자열 (번역 키 사용)
