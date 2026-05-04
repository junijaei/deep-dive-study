# 모던 자바스크립트 Deep Dive 스터디

이웅모 저 『모던 자바스크립트 Deep Dive』를 읽고 챕터별로 내용을 정리한 스터디 기록 저장소입니다.

## 콘텐츠 구성

| 파일                         | 내용                | 출처                          |
| ---------------------------- | ------------------- | ----------------------------- |
| `chapters/chNN/README.md`    | 챕터 핵심 내용 요약 | 직접 정리                     |
| `chapters/chNN/questions.md` | 퀴즈 문제 및 정답   | 스터디 중 출제된 문제 모음    |
| `week/weekXX.md`             | 주차 인덱싱 및 요약 | LLM 요약                      |

## 구조

```
week/
  weekXX.md             ← 주차 인덱스 및 핵심 요약

chapters/
  chNN/
    README.md           ← 챕터별 정리 문서
    questions.md        ← 챕터별 문제 모음
```

---

## Progress

**18 / 49 챕터 완료** (36.7%)

`████████░░░░░░░░░░░░░`

---

## 주차별 진행 현황

| 주차                        | 챕터                              |                         제목                         | 완료 |
| --------------------------- | --------------------------------- | :--------------------------------------------------: | ---- |
| [Week 01](./week/week01.md) | [ch01](./chapters/ch01/README.md) |                      프로그래밍                      | ✅   |
| [Week 01](./week/week01.md) | [ch02](./chapters/ch02/README.md) |                   자바스크립트란?                    | ✅   |
| [Week 01](./week/week01.md) | ch03                              |          자바스크립트 개발 환경과 실행 방법          | ✅   |
| [Week 01](./week/week01.md) | [ch04](./chapters/ch04/README.md) |                         변수                         | ✅   |
| [Week 01](./week/week01.md) | ch05                              |                     표현식과 문                      | ✅   |
| [Week 01](./week/week01.md) | ch06                              |                     데이터 타입                      | ✅   |
| [Week 01](./week/week01.md) | ch07                              |                        연산자                        | ✅   |
| [Week 01](./week/week01.md) | ch08                              |                        제어문                        | ✅   |
| [Week 01](./week/week01.md) | [ch09](./chapters/ch09/README.md) |                타입 변환과 단축 평가                 | ✅   |
| [Week 01](./week/week01.md) | [ch10](./chapters/ch10/README.md) |                     객체 리터럴                      | ✅   |
| [Week 02](./week/week02.md) | [ch11](./chapters/ch11/README.md) |                원시 값과 객체의 비교                 | ✅   |
| [Week 02](./week/week02.md) | [ch12](./chapters/ch12/README.md) |                         함수                         | ✅   |
| [Week 02](./week/week02.md) | ch13                              |                        스코프                        |      |
| [Week 02](./week/week02.md) | ch14                              |                  전역 변수의 문제점                  |      |
| [Week 02](./week/week02.md) | ch15                              |         let, const 키워드와 블록 레벨 스코프         |      |
| [Week 02](./week/week02.md) | ch16                              |                 프로퍼티 어트리뷰트                  |      |
| [Week 03](./week/week03.md) | [ch17](./chapters/ch17/README.md) |             생성자 함수에 의한 객체 생성             | ✅   |
| [Week 03](./week/week03.md) | [ch18](./chapters/ch18/README.md) |                   함수와 일급 객체                   | ✅   |
| [Week 03](./week/week03.md) | [ch19](./chapters/ch19/README.md) |                      프로토타입                      | ✅   |
| [Week 04](./week/week04.md) | [ch20](./chapters/ch20/README.md) |                     strict mode                      | ✅   |
| [Week 04](./week/week04.md) | [ch21](./chapters/ch21/README.md) |                     빌트인 객체                      | ✅   |
| [Week 04](./week/week04.md) | [ch22](./chapters/ch22/README.md) |                         this                         | ✅   |
|                             | ch23                              |                    실행 컨텍스트                     |      |
|                             | ch24                              |                        클로저                        |      |
|                             | ch25                              |                        클래스                        |      |
|                             | ch26                              |                 ES6 함수의 추가 기능                 |      |
|                             | ch27                              |                         배열                         |      |
|                             | ch28                              |                        Number                        |      |
|                             | ch29                              |                         Math                         |      |
|                             | ch30                              |                         Date                         |      |
|                             | ch31                              |                        RegExp                        |      |
|                             | ch32                              |                        String                        |      |
|                             | ch33                              |               7번째 데이터 타입 Symbol               |      |
|                             | ch34                              |                       이터러블                       |      |
|                             | ch35                              |                    스프레드 문법                     |      |
|                             | ch36                              |                  디스트럭처링 할당                   |      |
|                             | ch37                              |                      Set과 Map                       |      |
|                             | ch38                              |                브라우저의 렌더링 과정                |      |
|                             | ch39                              |                         DOM                          |      |
|                             | ch40                              |                        이벤트                        |      |
|                             | ch41                              |                        타이머                        |      |
|                             | ch42                              |                  비동기 프로그래밍                   |      |
|                             | ch43                              |                         Ajax                         |      |
|                             | ch44                              |                       REST API                       |      |
|                             | ch45                              |                       프로미스                       |      |
|                             | ch46                              |               제너레이터와 async/await               |      |
|                             | ch47                              |                      에러 처리                       |      |
|                             | ch48                              |                         모듈                         |      |
|                             | ch49                              | Babel과 Webpack을 이용한 ES6+/ES.NEXT 개발 환경 구축 |      |

---

## 챕터 목록

### Week 01

- [ch01 — 프로그래밍](./chapters/ch01/README.md)
- [ch02 — 자바스크립트란?](./chapters/ch02/README.md)
- [ch04 — 변수](./chapters/ch04/README.md)
- [ch09 — 타입 변환과 단축 평가](./chapters/ch09/README.md)
- [ch10 — 객체 리터럴](./chapters/ch10/README.md)

### Week 02

- [ch11 — 원시 값과 객체의 비교](./chapters/ch11/README.md)
- [ch12 — 함수](./chapters/ch12/README.md)

### Week 03

- [ch17 — 생성자 함수에 의한 객체 생성](./chapters/ch17/README.md)
- [ch18 — 함수와 일급 객체](./chapters/ch18/README.md)
- [ch19 — 프로토타입](./chapters/ch19/README.md)

### Week 04

- [ch20 — strict mode](./chapters/ch20/README.md)
- [ch21 — 빌트인 객체](./chapters/ch21/README.md)
- [ch22 — this](./chapters/ch22/README.md)
