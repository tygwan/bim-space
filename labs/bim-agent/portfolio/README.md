# BIM Agent: Navisworks 플랜트 4D 자동화 애드인

Navisworks 플랜트 모델을 진단하고, 부재끼리의 연결 관계로 시공 순서를 짜서 TimeLiner 4D로 반영하는 애드인이다. 자동 판단마다 근거를 붙이고, 애매한 연결은 엔지니어가 검토해 다시 데이터로 돌려보낸다.

- 개발: [tygwan](https://github.com/tygwan) 단독 개발, 2026.04 – 08 (커밋 309, 마일스톤 M0–M9)
- 기술: C# · .NET Standard 2.0(엔진) / .NET Framework 4.8(Navisworks 쪽) · WPF · Navisworks .NET API
- 검증: 연구용 플랜트 모델(물리 객체 7,890), Navisworks Manage 2025와 2027
- 소스: 아직 비공개다. 공정 연계 기능과의 접점을 검토하고 성능을 다듬은 뒤 공개한다.

## 포트폴리오 보기

- `deck.html`을 브라우저로 연다. 16:9 네 장이다.
  1. 목적과 결과
  2. 아키텍처
  3. 데이터 흐름과 구조
  4. 엔지니어 검토와 4D
- PDF가 필요하면 인쇄에서 "PDF로 저장", 여백 "없음"을 고른다. 장마다 한 쪽이 된다.

## 들어 있는 것

| 경로 | 내용 |
|---|---|
| `deck.html` | 포트폴리오 네 장 |
| `figures/architecture.svg` | 3층 구조(화면 · 변환 · 엔진)와 Navisworks API 호출 수 |
| `figures/pipeline.svg` | 11단계 파이프라인, 결과 파일, 엔지니어 검토와 일정 승인 |
| `figures/schema.svg` | 주요 데이터 구조와 이를 잇는 키(ObjectId) |
| `figures/build.mjs` | 파이프라인·데이터 구조 그림을 표에서 만드는 스크립트(`node figures/build.mjs`) |
| `shots/` | Navisworks Manage 2027 실행 화면(2026-11-13) |

수치 출처: 2027 실행 화면, 엔진 시험 286개, BIM Agent DLL의 코드 구조 분석(REA).
