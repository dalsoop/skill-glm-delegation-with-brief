## 작업: [테이블명] [컬럼/관계] 추가 migration + 모델 수정

### 1. 파일 목록

| 동작 | 경로 | 역할 |
|------|------|------|
| 생성 | database/migrations/[날짜]_[설명].php | 마이그레이션 |
| 수정 | app/Models/[Model].php | fillable + cast + 관계 추가 |

### 2. 스펙

마이그레이션:
```php
Schema::table('[테이블]', function (Blueprint $table) {
    $table->[타입]('[컬럼]')->[제약];
});
```

모델:
- fillable에 '[컬럼]' 추가
- casts에 '[컬럼]' => '[타입]' 추가
- [필요시] 관계 메서드: [hasMany/belongsTo]
- [필요시] accessor/mutator

### 3. 제약

- Laravel 11+ 문법
- down() 메서드 필수 (롤백 가능)
- 기존 데이터 보존 (nullable 또는 default)
- 인덱스: [필요시 명시]

### 4. 하지 말 것

- 기존 컬럼 수정/삭제
- 시더 데이터 삽입
- Controller/View 수정
- 다른 테이블 변경
