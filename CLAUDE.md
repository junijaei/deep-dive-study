# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

이웅모 저 『모던 자바스크립트 Deep Dive』 스터디 기록 저장소다. 빌드/테스트/린트 명령어는 없다. 모든 작업은 Markdown 문서 생성과 편집이다.

## 디렉토리 구조

```
week/
  weekXX_original.md   ← 직접 작성한 원본 노트 (수정 금지)
  weekXX.md            ← 주차 인덱스 + 핵심 요약 + 토론 (생성/편집 대상)

chapters/
  chNN/
    README.md          ← 챕터별 정리 문서 (생성/편집 대상)
    questions.md       ← 챕터별 문제 모음 (있을 때만 생성)

README.md              ← 전체 인덱스 + Progress 테이블
GENERATION_RULES.md    ← 문서 생성 상세 규칙 (이 파일이 최우선 참고)
```

## 문서 작업 시 필수 규칙

상세 규칙은 `GENERATION_RULES.md`를 참고한다. 핵심만 요약하면:

### 챕터 파일 생성 (`chapters/chNN/README.md`)
- 원본(`weekXX_original.md`)의 `# N. 제목` 단위로 분리
- `<aside>` 블록 → GFM 콜아웃으로 변환:
  - 태그·이모지·내부 빈 줄 제거 후 각 줄에 `> ` 접두사
  - 블록 최상단에 `> [!NOTE]` 추가
- 챕터 사이 `---` 구분선 제거, 나머지 콘텐츠는 원본 그대로 유지

### 주차 인덱스 파일 (`week/weekXX.md`)
필수 섹션: `## 진행범위` → `## 요약 문서` → `## 핵심 요약`  
선택 섹션: `## 토론` (스터디 토론 내용이 있을 때만, 이름 제거 후 주제별 정리)

### 문제 모음 파일 (`chapters/chNN/questions.md`)
- 질문: `## QN.` 형식
- 정답: `<details><summary>정답</summary>` 태그로 접힌 상태 제공
- 스터디원 이름·개인 풀이 포함 금지

## README.md 업데이트 규칙

새 챕터 문서를 생성할 때마다 함께 업데이트해야 하는 항목:
1. `## Progress` 테이블 — 해당 챕터 행에 `✅` 추가
2. 상단 카운트(`N / 49`) 및 프로그레스 바 갱신
3. `## 챕터 목록` 해당 주차 섹션에 링크 추가

## 콘텐츠 출처 구분

| 파일 | 출처 |
| --- | --- |
| `chapters/chNN/README.md` | 직접 정리 |
| `chapters/chNN/questions.md` | 스터디 중 출제된 문제 |
| `week/weekXX.md` 토론 섹션 | 스터디 토론 내용 |
| `week/weekXX.md` 핵심 요약 | LLM 요약 |
