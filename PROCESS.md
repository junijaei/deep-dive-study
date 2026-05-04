# 문서 추가 프로세스

새 챕터 문서를 추가할 때 전체 흐름을 정의한다.
각 단계의 상세 규칙은 링크된 문서를 참고한다.

| 규칙 문서 | 용도 |
| --- | --- |
| [GENERATION_RULES.md](./GENERATION_RULES.md) | 각 파일의 생성 규칙 (aside 변환, 섹션 구조 등) |
| [README_UPDATE_RULES.md](./README_UPDATE_RULES.md) | README.md 4개 영역 갱신 규칙 |

---

## 작업 순서

### 1. 원본 확인

- `week/weekXX_original.md` 열기
- 대상 챕터 번호(`# N. 제목`) 목록과 주차 번호(XX) 파악

### 2. 챕터 파일 생성

챕터마다 반복. → [GENERATION_RULES.md §2](./GENERATION_RULES.md#2-챕터-파일-생성-규칙-chapterschnNreadmemd)

- `chapters/chNN/README.md` 생성

### 3. 문제 파일 생성 (선택)

스터디 문제가 있을 때만. → [GENERATION_RULES.md §3](./GENERATION_RULES.md#3-문제-모음-파일-규칙-chapterschnNquestionsmd)

- `chapters/chNN/questions.md` 생성

### 4. 주차 인덱스 파일 생성/수정

신규 주차면 생성, 기존 주차면 수정. → [GENERATION_RULES.md §4](./GENERATION_RULES.md#4-주차-인덱스-파일-생성-규칙-weekweekxxmd)

- `week/weekXX.md` 생성 또는 수정

### 5. README.md 업데이트

3개 영역 전부 갱신. → [README_UPDATE_RULES.md](./README_UPDATE_RULES.md)

- Progress 카운트 & 프로그레스 바
- 주차별 진행 현황 테이블 (주차 + 링크 + ✅)
- 챕터 목록

---

## 체크리스트

```
[ ] chapters/chNN/README.md 생성
[ ] chapters/chNN/questions.md 생성 (문제 있을 때만)
[ ] week/weekXX.md 생성 또는 수정
[ ] README.md — Progress 카운트 & 프로그레스 바 갱신
[ ] README.md — 주차별 진행 현황 테이블 주차 + 링크 + ✅ 추가
[ ] README.md — 챕터 목록 링크 추가
```
