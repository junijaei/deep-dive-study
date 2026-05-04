# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

이웅모 저 『모던 자바스크립트 Deep Dive』 스터디 기록 저장소다. 빌드/테스트/린트 명령어는 없다. 모든 작업은 Markdown 문서 생성과 편집이다.

## 디렉토리 구조

```
week/
  weekXX_original.md   ← 직접 작성한 원본 노트 (수정 금지)
  weekXX.md            ← 주차 인덱스 + 핵심 요약 + 토론

chapters/
  chNN/
    README.md          ← 챕터별 정리 문서
    questions.md       ← 챕터별 문제 모음 (있을 때만)

README.md              ← 전체 인덱스 + Progress 테이블
```

## 참고 문서

| 문서 | 용도 |
| --- | --- |
| [PROCESS.md](./PROCESS.md) | 문서 추가 시 전체 작업 순서 및 체크리스트 (시작점) |
| [GENERATION_RULES.md](./GENERATION_RULES.md) | 각 파일 생성 상세 규칙 (aside 변환, 섹션 구조 등) |
| [README_UPDATE_RULES.md](./README_UPDATE_RULES.md) | README.md 3개 영역 갱신 규칙 |

## 핵심 제약

- `weekXX_original.md`는 **절대 수정하지 않는다.**
- 새 챕터 문서 생성 시 반드시 `README.md`의 3개 영역을 함께 갱신한다. → [PROCESS.md 5단계](./PROCESS.md#5단계-readmemd-업데이트) 참고
