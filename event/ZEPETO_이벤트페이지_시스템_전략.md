# ZEPETO 이벤트 페이지 템플릿 시스템 전략

> **핵심 목표**: 디자인·개발 리소스를 최소화하면서, 20개국어 대응 이벤트 페이지를 누구나 빠르게 만들 수 있는 구조를 만든다.

---

## 현재 문제 진단

지금 구조의 병목은 **"텍스트가 이미지 안에 갇혀 있다"** 는 것입니다.

```
텍스트 수정 요청
→ 프모팀이 피그마에서 20개 언어 이미지 수정
→ 20개 이미지 재출력
→ 프론트에 전달
→ 배포
```

텍스트를 이미지에서 분리하는 순간, 이 병목이 사라집니다.

---

## 해결 구조 (3단계 레이어)

### Layer 1. 디자인 토큰 (Design Tokens)
이벤트마다 바뀌는 색상, 폰트, 간격 등을 변수로 관리합니다.

```css
/* 이벤트마다 이 값만 바꾸면 전체 디자인이 바뀜 */
:root {
  --color-primary: #FF4FCB;
  --color-bg: #1A0033;
  --font-heading: 'ZEPETOFont', sans-serif;
  --border-radius: 16px;
}
```

프모팀이 피그마에서 디자인 토큰을 정의하면, 개발자가 CSS 변수 몇 개만 교체해서 새 이벤트 테마를 만들 수 있습니다.

---

### Layer 2. 컴포넌트 라이브러리 (Component Library)
이벤트 페이지에서 반복적으로 쓰이는 UI 조각들을 컴포넌트로 만들어둡니다.

**공통 컴포넌트 예시:**

| 컴포넌트 | 설명 |
|----------|------|
| `EventHero` | 상단 메인 배너 (타이틀 + 서브 텍스트 + CTA 버튼) |
| `CountdownTimer` | D-Day 카운트다운 |
| `RewardCard` | 보상 아이템 카드 |
| `RuleAccordion` | 이벤트 규칙 접기/펼치기 |
| `StickyButton` | 하단 고정 참여 버튼 |
| `LanguageSwitcher` | 언어 전환 UI |

각 컴포넌트는 **텍스트를 직접 갖지 않고**, 언어 키(key)를 받아서 표시합니다.

```jsx
// ❌ 지금 방식 (텍스트가 이미지 안에 고정)
<img src="banner_ko.png" />
<img src="banner_en.png" />
... (20개)

// ✅ 새 방식 (컴포넌트 + 다국어 키)
<EventHero
  titleKey="event.title"
  subtitleKey="event.subtitle"
  ctaKey="event.cta"
/>
```

---

### Layer 3. 다국어 시스템 (i18n)
텍스트는 JSON 파일로 언어별로 분리해서 관리합니다.

```
/locales
  /ko.json
  /en.json
  /ja.json
  /zh-TW.json
  ... (20개 언어)
```

각 JSON 파일 구조:
```json
{
  "event": {
    "title": "겨울 스페셜 이벤트",
    "subtitle": "지금 참여하고 특별 아이템을 받아보세요!",
    "cta": "지금 참여하기"
  }
}
```

텍스트 수정이 생기면 **JSON 파일 한 줄만 바꾸면** 20개 언어 이미지를 다시 뽑을 필요 없이 반영됩니다.

운영팀이나 번역팀이 직접 Google Sheets나 엑셀에서 관리하고, 자동으로 JSON으로 변환되게 할 수도 있습니다.

---

## 반응형 웹 룰 고정

반응형 규칙도 컴포넌트 안에 내장시켜, 이벤트마다 새로 짜지 않아도 되게 합니다.

```css
/* 컴포넌트 내부에 고정된 반응형 룰 */
.event-hero {
  padding: 40px 20px;         /* 모바일 기본 */
}

@media (min-width: 768px) {
  .event-hero {
    padding: 80px 40px;       /* 태블릿 */
  }
}

@media (min-width: 1200px) {
  .event-hero {
    padding: 100px 0;         /* 데스크탑 */
    max-width: 1200px;
    margin: 0 auto;
  }
}
```

---

## 이벤트 페이지 조립 방식

새 이벤트가 생기면, 개발자는 컴포넌트를 레고처럼 조합하기만 합니다.

```jsx
// 새 이벤트 페이지 = 컴포넌트 조합 + 토큰 교체
import { EventHero, CountdownTimer, RewardCard, StickyButton } from '@zepeto/event-components'

export default function WinterEvent() {
  return (
    <EventPage theme="winter2025">   {/* 테마 토큰만 교체 */}
      <EventHero titleKey="winter.hero.title" />
      <CountdownTimer endDate="2025-12-31" />
      <RewardCard items={rewardList} />
      <StickyButton ctaKey="winter.cta" />
    </EventPage>
  )
}
```

---

## 최종 목표: 노코드 페이지 빌더

컴포넌트 라이브러리와 다국어 시스템이 완성되면, 그 위에 **드래그 앤 드롭 페이지 빌더**를 올릴 수 있습니다.

```
[컴포넌트 목록]          [캔버스]                [설정 패널]
─────────────      ─────────────────      ─────────────────
 EventHero    →   │  🎉 겨울 이벤트  │   타이틀: [      ]
 CountdownTimer   │  D-3  23:59:59  │   색상: [🎨]
 RewardCard       │  ┌───┐  ┌───┐   │   언어: [KO ▼]
 StickyButton     │  │아이│  │아이│  │
                  │  └───┘  └───┘   │
                  │ [지금 참여하기]  │
```

**운영팀이나 프모팀이 직접:**
- 컴포넌트를 드래그해서 배치
- 텍스트 직접 입력 (자동으로 20개 언어 시트와 연동)
- 이미지 업로드
- 버튼 링크 연결
- 미리보기 후 배포

---

## 구현 단계별 로드맵

### Phase 1 — 기반 구축 (1~2개월)
- 컴포넌트 라이브러리 설계 및 핵심 컴포넌트 개발 (Hero, Button, Timer 등)
- i18n 시스템 세팅 (i18next 또는 동등한 라이브러리)
- 번역 시트(Google Sheets) ↔ JSON 자동 변환 파이프라인 구축
- 디자인 토큰 체계 정의 (피그마 Variables와 연동)

### Phase 2 — 실전 적용 (1~2개월)
- 실제 이벤트 1~2개에 새 시스템 적용 및 검증
- 반응형 룰 확립 및 컴포넌트에 내장
- 내부 가이드 문서 작성

### Phase 3 — 노코드 빌더 (3~6개월)
- 관리자용 페이지 빌더 UI 개발
- 실시간 미리보기 기능
- 배포 파이프라인 연결
- 권한 관리 (운영팀, 프모팀, 개발팀)

---

## 추천 기술 스택

| 영역 | 추천 기술 | 이유 |
|------|-----------|------|
| 컴포넌트 | React + TypeScript | ZEPETO가 이미 웹 프론트에 사용 가능성 높음 |
| 다국어 | i18next | 20개국어 대응에 업계 표준 |
| 번역 관리 | Google Sheets + 변환 스크립트 | 비개발자도 쉽게 편집 가능 |
| 디자인 토큰 | Figma Variables → Style Dictionary | 피그마와 코드 자동 동기화 |
| 노코드 빌더 | 자체 개발 or Craft.js (오픈소스) | 커스터마이징 자유도 높음 |
| 스타일 | CSS Modules or Tailwind | 컴포넌트 스코프 스타일 관리 |

---

## 기대 효과

| 항목 | 현재 | 개선 후 |
|------|------|---------|
| 텍스트 수정 시 | 이미지 20개 재작업 | JSON 파일 1줄 수정 |
| 새 이벤트 페이지 제작 | 디자인+개발 풀 공수 | 컴포넌트 조합 + 토큰 교체 |
| 다국어 적용 | 수동으로 20개 이미지 | 자동으로 전 언어 적용 |
| 반응형 대응 | 이벤트마다 새로 작업 | 컴포넌트에 이미 내장 |
| 운영팀 직접 수정 | 불가 | Phase 3 이후 가능 |

---

> **첫 번째 액션 아이템**: 현재 이벤트 페이지들을 분석해서 반복되는 컴포넌트 패턴을 10개 내외로 추출하는 것이 시작점입니다. 그 목록이 나오면 컴포넌트 라이브러리 설계를 시작할 수 있습니다.
