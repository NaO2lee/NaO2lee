# 이나영 — AI 빌더

(주)연희 AI 빌더팀 / Tangiblestory 신규 뷰티브랜드 TF
`tkfkd4528@gmail.com`

---

## About

안녕하세요, 이나영입니다.

도메인 지식과 데이터, 그리고 LLM을 조합해 직접 경험하지 못한 영역까지 설계·실행하는 'AI 빌더'로 일하고 있습니다. AI를 단순한 도구가 아니라, 현실적인 결과물을 만들어내기 위한 동반자로 활용합니다.

화학 → 바이오소재 → 의료·생체신호 → 제조 도메인을 거치며, 데이터를 정제하고 의미를 끌어내는 일을 일관된 관점으로 확장해 왔습니다. 현재는 빌더 2명·디자인 2명으로 구성된 소규모 팀에서 글로벌 D2C 자사몰, 카메라 기반 제품 인식 시스템, 회계 자동화 포털을 직접 구축하고 운영하고 있습니다.

---

## Live Projects

| Project | Live | Stack |
|---|---|---|
| **acosmeticstory** — 글로벌 D2C 자사몰 | [acosmeticstory.com](https://acosmeticstory.com) | Shopify · Liquid · JS |
| **Intrinsic AR** — 30종 스킨케어 제품 AR 인식, 텍스쳐 정보 제공 | [acosmeticstory.github.io/intrinsic-ar](https://acosmeticstory.github.io/intrinsic-ar/) | MindAR · A-Frame · Tesseract.js |
| **Holder AR** — 라벨 바코드 스캔 → 제품 정보 | [holders.acosmeticstory.com](https://holders.acosmeticstory.com) | zxing-js · GS1 EAN-13 · Cloudflare |
| **Everyplay** — Holiday project (줄넘기 라이브 스트리밍) | [everyplay.weplaykorea.com](https://everyplay.weplaykorea.com/) | Frontend |

---

## What I'm Building

### Cross-border D2C Storefront

- Shopify 기반 자사몰 직접 구축·운영
- 모바일 인터랙션 재설계 — 토글 → 슬라이드 + 도트
- 15개국 크로스보더 규제 리서치
- 다국어 고지 시스템 — 한·영·일·중·아랍·프·베·힌·벵·네팔어
- 배송 차단·세금 안내·면책 문구 통합 운영

### Performance & Cross-platform UX *(빌더 팀원 1명과 공동 진행)*

라이브 자사몰의 모바일 성능과 멀티 디바이스 UX를 직접 계측·개선

| Metric (Mobile) | Before | After | Δ |
|---|---:|---:|---:|
| Lighthouse Performance | 66 | **85** | **+19** |
| LCP — Largest Contentful Paint | 5.8s | **3.0s** | **−48%** |
| FCP — First Contentful Paint | 1.85s | **1.35s** | **−28%** |
| SEO | 85 | **92** | **+7** |
| Bundle | — | **−6.1MB** | (미사용 AR 라이브러리 제거) |
| CLS — Cumulative Layout Shift | 0 | **0** | 유지 |

```
Lighthouse  ▓▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░░  66
            ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░░░  85   +19
LCP (s)     ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  5.8
            ▓▓▓▓▓▓▓▓▓▓░░░░░░░░░░  3.0  −48%
FCP (s)     ▓▓▓▓▓▓▓░░░░░░░░░░░░░  1.85
            ▓▓▓▓▓░░░░░░░░░░░░░░░  1.35 −28%
SEO         ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░░░  85
            ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░  92   +7
```

세부 작업

- **로딩** — 서드파티 스크립트 지연 로드, 렌더링 차단 CSS 해결, 영상 첫 부분만 부분 다운로드(전체/절반 시 병목 발생 → 일부분으로 최적화) → 3초 이내 재생
- **인터랙션** — 그래픽 ID 이미지 페이지 로드 후 500ms 시점에 사전 캐시 → 탭 전환 시 서버 요청 없이 즉시 표시
- **태블릿** — PC로 인식되어 마우스 호버 효과가 터치에서 불편 → 환경 감지 후 슬라이드 방식으로 전환
- **안드로이드 모아레** — 본연 1·2·5·13 코어 4종 카드에서 발생 → UA 감지 + 해당 4종 한정 해상도 다운그레이드 (2000px → 600px)

### SEO

- **Google SEO** — 사이트 구조·메타데이터·`robots.txt`·sitemap 자동 출력 검증
- **Shopify SEO** — Shopify 자체 SEO 한계 보완, 다국어 메타·hreflang 처리, 페이지별 타이틀·설명 최적화
- **결과 — Lighthouse SEO 85 → 92**

### Camera-based Product Identification

**Intrinsic AR**
- 30종 스킨케어 제품 스마트폰 카메라 즉시 인식
- MindAR 이미지 매칭 69 타겟 — 21종 처리
- Tesseract.js 3-pass OCR fallback — 나머지 9종 보완
- 11개 언어 자동 분기, 텍스처 비디오·물성값(경도·pH·수분율) 실시간 표시

**Holder AR**
- 라벨 인쇄 EAN-13 바코드 zxing-js 스캔 → Shopify 상품 정보 즉시 fetch
- GS1 Korea 정식 바코드 150종 발급
- 자체 서브도메인 인프라 직접 구축

### Accounting RPA Portal

- Cloudflare Workers + D1 + R2 기반 ERP 전표 자동화 포털 구축
- 카드 명세서·세금계산서 학습형 매핑으로 자동 분류
- D365 표준 템플릿(공제·불공제 시트 분리) 출력
- 비전공 실무자 친화 화면 — 의미 기반 라벨, 추천 카드, 검토 큐 직접 설계

### Manufacturing Cost Dashboard

- 제조 공정 원가 가시화 대시보드
- 1차 구현 완료, 안정 운영을 위해 Cloudflare 인프라 마이그레이션 진행 중

### AI-driven Marketing Pipeline

- Midjourney·Sora — 브랜드 영상·이미지 제작
- Gemini — 제품 데이터·브랜드 아이덴티티 일관 AI 이미지 프롬프트 설계
- SNS AI 에이전트 — 글로벌 마케팅 자동화 운영

---

## Holiday Project

### Everyplay — 줄넘기 대회 라이브 스트리밍

- 회사 외 holiday project, 후배와 공동 운영
- **Korea Open 오픈 경기 3일** 실제 라이브 서비스 운영
- [everyplay.weplaykorea.com](https://everyplay.weplaykorea.com/) — 프론트엔드 담당

---

## Research

### Publications

| Year | Journal · Role | Title |
|---|---|---|
| 2025.11 | **Robotics (MDPI)** Vol.14, No.12 · Co-author | A Comprehensive Review of Autonomous Mobile Robots in Healthcare: Implications for Patient-Transporting Human-Following Robots |
| 2024.06 | **IEEE Access** · **First author** | Advancing Continuous Blood Pressure Estimation with Transformer on Photoplethysmography in Operation Room |
| 2024.02 | **한국컴퓨터정보학회 논문지** · Co-author | Designing a smart safe transportation system within a university using object detection algorithm |
| 2017 | **Chem. Sci.** 8(8), 5460–5467 · **First author** | Bioinorganic redox mechanism (iron-organometallic) |

### Conferences

- **ICT4sHealth&Home** (2022.12) — Oral presentation: Continuous Blood Pressure Estimation with PPG
- **EBRC & HOME Conference** (2022.06) — Invasive continuous BP estimation with deep learning models

---

## Awards & Grants

- **한국컴퓨터정보학회 우수논문상** (2023.01) — 객체인식 반응형 교통시스템
- **EBRC & HOME 우수논문상** (2022.06) — PPG 기반 혈압 추정 딥러닝
- **충남리빙랩 페어 3등** (2023.11) — (재)충남정보문화산업진흥원
- **2022 청년동아리 3.14 지원사업** — 아산시장 선정
- **ICT 혁신인재 4.0 사업** 수혜 (2021.09 ~ 2023.08)
- **지능형 홈케어 산업 전문인력 양성 사업** 수혜 (2021.09 ~ 2023.08)

---

## Certifications

- **빅데이터분석기사** (2025.01)
- **SQLD** — SQL 개발자 (2024.06)
- **ADsP** — 데이터분석 준전문가 (2024.03)
- **사회문제 해결 퍼실리테이터** — 대전세종충남 지역혁신플랫폼 (2022.02)

---

## Education

| Period | Degree |
|---|---|
| 2021 — 2024 | 순천향대학교 대학원 석사 — ICT융합학과 AI 빅데이터 전공 (GPA **4.25 / 4.5**) |
| 2016 — 2017 | 이화여자대학교 대학원 석사 수료 — 생체무기화학 |
| 2011 — 2015 | 대진대학교 화학과 학사 (GPA **3.91 / 4.5**) |

---

## Selected Project History

- **국립보건연구원** — 데이터 매니저 (2022.05 ~ 2022.12) · 웨어러블·모바일 기반 생활습관 데이터 분석
- **산업통상자원부 / KEIT** — 연구원 (2022.01 ~ 2022.12) · 감염환자 격리 이송 사람 추종형 반자율 침상 로봇 (Robotics 논문 연계)
- **순천향대학교 천안병원** — 데이터 분석 인턴 (2021.07 ~ 2022.02) · 신경외과 임상 데이터
- **대전세종충남 지역혁신플랫폼** — 연구원 (2022.05 ~ 2023.06) · 미래 모빌리티 인터페이스
- **㈜바이오스탠다드 기술연구소** — 연구원 (2019.09 ~ 2021.08) · 히알루론산 기반 기능성 하이드로겔 개발
- **충남사회혁신센터 / 아산시 청년동아리** — 팀장 (2022.04 ~ 2022.12) · 지역 문제 해결형 혁신 프로젝트

---

## Stack

**Web · Storefront** Shopify · Liquid · HTML · CSS · JavaScript · Framer
**AR · CV** MindAR · A-Frame · zxing-js · Tesseract.js · Canvas 2D · OpenCV
**AI · LLM** PyTorch · TensorFlow · Transformer · LLM · RAG · Prompt Engineering
**Backend · Infra** Cloudflare Workers · D1 · R2 · Supabase · Firebase · Node.js
**SEO · Marketing** Google SEO · Shopify SEO · Google Ads · Google Analytics
**Automation** N8N · Microsoft Power Automate · Google AI Platform
**Tooling** Claude Code · Codex · git · Figma · KeyShot · Photoshop · Illustrator

---

## Activity

![NaO2lee's GitHub stats](https://github-readme-stats.vercel.app/api?username=NaO2lee&show_icons=true&hide_border=true&count_private=true)
![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=NaO2lee&hide_border=true)

> 비공개 저장소 활동 포함

---

## Contact

`tkfkd4528@gmail.com`
