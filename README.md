# idea-garden

> 아이디어를 심고, 목업까지 키우고, 다 자라면 별도 리포지토리로 옮겨 심는 곳.

이 리포지토리는 **코드를 만드는 곳이 아니라 아이디어를 정리하고 외부에 설명할 수 있는 형태(덱)로 다듬는 곳**입니다.
결과물은 그대로 **개인 포트폴리오**가 됩니다.

---

## 🌱 아이디어 리스트

아이디어 하나 = 이슈 하나 = 태그(`idea:<slug>`) 하나.
태그를 누르면 해당 아이디어의 모든 논의가 모입니다.

| 태그 | 아이디어 | 단계 | 이슈 | 덱 |
|---|---|---|---|---|
| [`idea:ja-one-line-trainer`](https://github.com/songyoungoak/idea-garden/labels/idea%3Aja-one-line-trainer) | 일본어 상황 언어화 트레이너 — 3~5단어, 1층 문장으로 말하기 | 🌱 seed | [#1](https://github.com/songyoungoak/idea-garden/issues/1) | _미작성_ |
| `idea:ookubo-restaurant` | 오쿠보 식당 — 아이디어 재정의 필요 | 🌱 seed | _미등록_ | _미작성_ |

[→ 전체 아이디어 이슈 보기](https://github.com/songyoungoak/idea-garden/issues?q=is%3Aissue+label%3Astage%3Aseed%2Cstage%3Asprout%2Cstage%3Agrown)

---

## 1. 흐름 (Lifecycle)

```
GitHub Issue          →  덱(Deck) 작성          →  별도 리포지토리로 이전
(아이디어 1개 = 1 이슈)   (HTML / PDF, KO / JA)      (실제 개발 진행)
   🌱 seed              🌿 sprout → 🌳 grown          🚚 transplanted
```

| 단계 | 라벨 | 의미 |
|---|---|---|
| 🌱 `stage:seed` | 아이디어 한 줄만 있음 | 이슈만 생성 |
| 🌿 `stage:sprout` | 문제/배경이 정리됨 | 이슈 본문 채워짐 |
| 🌳 `stage:grown` | 목표·아키텍처 확정 | `decks/<slug>/` 덱 완성 (KO/JA + PDF) |
| 🚚 `stage:transplanted` | 별도 repo에서 개발 중 | 덱은 여기 남기고 주기적으로 업데이트 |
| 🍂 `stage:archived` | 보류/폐기 | 이유를 이슈에 남기고 close |

**아이디어 하나 = 이슈 하나 = (성숙하면) 덱 하나.** 이슈는 아이디어의 히스토리 저장소이고,
덱은 그 시점의 "외부 공개용 스냅샷"입니다.

---

## 2. 덱(Deck) 규칙

- **분량: 기본 3장, 최대 7장.** 넘으면 아이디어가 아직 안 좁혀진 것.
- **언어: 한국어 + 일본어** 두 버전 필수.
- **포맷: HTML(원본) + PDF(배포용).** PDF는 HTML에서 생성.
- **내용 구성** (3장으로 줄일 땐 2·3·4를 합칩니다)

  1. **Cover** — 프로젝트명, 한 줄 정의, 현재 단계
  2. **배경 / 문제** — 왜 지금 이 문제인가, 누가 불편한가
  3. **개요 / 솔루션** — 무엇을 만드는가, 타깃 고객, 핵심 가치
  4. **기술적 고민** — 지금 풀고 있는 어려운 문제
  5. **아키텍처 선정** — 무엇을 골랐고 왜 골랐는지 (트레이드오프)
  6. **현황 / 로드맵** — 마일스톤
  7. **링크** — 리포지토리, 데모, 연락처

> 덱은 "IR 자료"가 아니라 **고객·동료·채용 담당자에게 이 프로젝트를 설명할 수 있는 수준**을 목표로 합니다.

---

## 3. 공개 / 비공개 경계

외부 공개를 전제로 쓰되, **크리티컬한 정보는 담지 않습니다.**

**공개해도 되는 것**
문제 정의 · 타깃 고객 · 가치 제안 · 기술 스택과 선택 이유 · 아키텍처 개요도 · 마일스톤 · 공개 데모 링크

**절대 담지 않는 것**
- API 키, 토큰, 엔드포인트, 인프라 식별자(계정 ID·버킷명·호스트명)
- 수집 대상 사이트·계약 상세, 데이터 파트너/고객사 실명
- 투자 전략 파라미터, 알파 시그널, 백테스트 세부 수치
- 프롬프트 원문, 모델 파인튜닝 데이터, 미공개 알고리즘의 핵심
- 개인정보, 미공개 매출/원가 수치

판단이 애매하면 **넣지 않습니다.** 덱은 언제든 다시 업데이트할 수 있습니다.

---

## 4. 디렉터리 구조 (예정)

```
idea-garden/
├── README.md
├── CLAUDE.md                 # 작업 규칙 (AI/사람 공용)
├── templates/
│   └── deck.html             # 공통 슬라이드 템플릿 + CSS
├── decks/
│   └── <slug>/
│       ├── content.yaml      # 언어 무관 단일 소스 (KO/JA 텍스트 모두 포함)
│       ├── index.ko.html
│       ├── index.ja.html
│       └── dist/
│           ├── <slug>.ko.pdf
│           └── <slug>.ja.pdf
└── scripts/
    └── build-pdf.sh          # HTML → PDF
```

---

## 5. 프로젝트 목록

### 진행 중 (별도 리포지토리에서 개발)

| 프로젝트 | 리포지토리 | 덱 |
|---|---|---|
| tcg-ai-ecosystem | https://github.com/songyoungoak/tcg-ai-ecosystem | _미작성_ |
| tech | https://github.com/songyoungoak/tech | _미작성_ |
| taken | https://github.com/songyoungoak/taken | _미작성_ |
| companies | https://github.com/songyoungoak/companies | _미작성_ |
| real-estate-appraisal-study | https://github.com/songyoungoak/real-estate-appraisal-study | _미작성_ |
| ai-quant-invest-krx | https://github.com/songyoungoak/ai-quant-invest-krx | _미작성_ |

> 각 프로젝트의 한 줄 소개는 덱 작성 시 채웁니다. 리포 이름만 보고 추측해서 쓰지 않습니다.

### 아이디어 업데이트 필요

| 프로젝트 | 상태 |
|---|---|
| ookubo-restraunt (https://github.com/songyoungoak/ookubo-restraunt) | 아이디어 재정의 필요 — 이슈 미등록 |
| 일본어 상황 언어화 트레이너 (`ja-one-line-trainer`) | 🌱 seed — [#1](https://github.com/songyoungoak/idea-garden/issues/1) |

---

## 6. 새 아이디어 추가하기

1. `idea:<slug>` 라벨을 만들고, Issue 생성 → 라벨 `stage:seed` + `idea:<slug>` + `domain:*` 부여
2. 위 **아이디어 리스트 표에 한 줄 추가** (이슈만 만들고 끝내지 않습니다)
3. 배경 / 문제 / 대상 사용자를 이슈 본문에 채우면 → `stage:sprout`
4. 목표와 아키텍처가 확정되면 → `decks/<slug>/` 에 덱 작성, `stage:grown`
5. 별도 리포 생성 후 개발 시작 → `stage:transplanted`, 덱에 리포 링크 추가

```bash
SLUG=my-new-idea
gh label create "idea:$SLUG" -c "d4c5f9" -d "<아이디어 한 줄 설명>"
gh issue create --title "<아이디어 한 줄>" \
  --label "stage:seed" --label "idea:$SLUG" --label "domain:<분야>"
```

라벨 체계: `stage:*` (성숙도, 1개만) · `idea:<slug>` (아이디어 식별, 덱 디렉터리명과 일치) · `domain:*` (분야)
