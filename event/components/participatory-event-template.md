# 참여형 이벤트 템플릿

- Figma: [TEST_웹 이벤트 대응시 AI 활용 리서치](https://www.figma.com/design/gFzskH4dsA4TOpc2HpFHSq/TEST_%EC%9B%B9-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%8C%80%EC%9D%91%EC%8B%9C-AI-%ED%99%9C%EC%9A%A9-%EB%A6%AC%EC%84%9C%EC%B9%98?node-id=136-16819)
- 적용 규칙: `/event/event-component-rules.md`, `/DesignToken.md`

---

## 컴포넌트 구성

| 컴포넌트 | Figma Node ID | 설명 |
|---|---|---|
| `EventHero` | 132:25281 | 이벤트 상단 히어로 이미지 + 타이틀 텍스트 |
| `TabSection` | 132:26595 | 상단 탭 네비게이션 (Event / Item 등) |
| `ParticipationSection` | 133:22158 | 참가 방법 섹션. `StepList`, `TipList` 포함 |
| `RewardSection` | 136:17187 | 보상 섹션. `rewardList` 포함 |
| `PeriodSection` | 138:22735 | 이벤트 기간 표시 섹션 |
| `DisclaimerSection` | 138:22736 | 하단 유의사항(footer) 섹션 |

---

## 컴포넌트 상세

### EventHero
- 히어로 배경 이미지 위에 이벤트 타이틀 텍스트 오버레이
- 텍스트에 drop shadow 적용 (`text-shadow: 0px 0px 6.25px rgba(0,0,0,0.3)`)
- 크기: 375 × 248px

### TabSection
- 활성 탭: bold, `var(--color-gray-84)`, 하단 바 표시
- 비활성 탭: medium, `var(--color-gray-40)`, 하단 바 없음
- 탭 아이템은 동적으로 추가 가능

### ParticipationSection
- 내부에 `StepList`(단계 안내)와 `TipList`(팁 안내) 포함
- `StepList`는 계속 늘어날 수 있는 리스트 구조
- `TipList`는 핑크 태그(`#ff58a4`) + 설명 텍스트 구조
- 배경: `#fff4e9`, radius: 20px

### RewardSection
- 내부에 `rewardList` 포함
- 보상 아이템(순위 + 리워드명 + 이미지) 리스트 구조로 계속 늘어날 수 있음
- 배경: `#fff4e9`, radius: 20px

### PeriodSection
- 이벤트 기간 텍스트 단순 표시
- 배경: `#fff4e9`, radius: 20px

### DisclaimerSection
- 페이지 최하단 footer 역할
- 불릿 리스트 형태로 유의사항 나열, 아이템 수는 유동적
- 배경: `var(--color-bg-offwhite-01)`
