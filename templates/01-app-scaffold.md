## 작업: [앱이름] [앱종류] 앱 도메인 로직 구현

### 1. 파일 목록

| 동작 | 경로 | 역할 |
|------|------|------|
| 수정 | Sources/[AppName]/MainView.swift | 주 화면 → 도메인 뷰로 교체 |
| 수정 | Sources/[AppName]/AppModel.swift | 상태 모델에 도메인 데이터 추가 |
| 생성 | Sources/[AppNameCore]/[Domain]Service.swift | 도메인 로직 (파일 읽기/CLI 호출) |
| 생성 | Sources/[AppNameCore]/[Domain]Model.swift | 도메인 데이터 모델 (Codable) |

### 2. 스펙

[Domain]Service:
- 입력: [데이터 소스 경로/형식]
- 동작: [읽기/감시/변환 방법]
- 출력: [어떤 타입의 배열/값]

MainView:
- [화면 구성 상세 — 몇 행, 어떤 정보, 크기]
- [상호작용 — 버튼/클릭/드래그]

AppModel:
- [추가할 @Observable 프로퍼티]
- [refresh/load 메서드 시그니처]

### 3. 제약

- SwiftUI + 기존 스캐폴드 패턴 (AppScaffoldKit, DualEntryKit, StateMirrorKit)
- CommandKit: CLI 호출은 CommandRunning 프로토콜 경유
- StateMirrorKit: 상태 변경 시 publish 호출
- 기존 OnboardingView/SettingsView 건드리지 않음

### 4. 하지 말 것

- 새 Swift 패키지 의존성 추가
- Package.swift 수정
- 테스트 파일 생성 (별도 위임)
- 도메인 판단 로직 (표시만)
