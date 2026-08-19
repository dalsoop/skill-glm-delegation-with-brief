## 작업: [사이트/앱] 반응형 breakpoint [N]단계 추가

### 1. 파일 목록

| 동작 | 경로 | 역할 |
|------|------|------|
| 수정 | [CSS 파일 경로] | @media 쿼리 추가 |

### 2. 스펙

breakpoint:
- [Npx]: [그리드 열수, 폰트 크기, 패딩, 숨김 요소]
- [Npx]: [위와 동일]
- [Npx]: [위와 동일]

대상 선택자:
- [.class1]: [변경 내용]
- [.class2]: [변경 내용]

### 3. 제약

- 기존 CSS 변수·클래스 유지
- mobile-first 또는 desktop-first 명시: [어느 쪽]
- 기존 @media 쿼리와 충돌 없이 추가
- 단위: rem 우선, px는 breakpoint만

### 4. 하지 말 것

- 기존 스타일 덮어쓰기
- !important 사용
- 새 CSS 변수 정의
- HTML 구조 변경
