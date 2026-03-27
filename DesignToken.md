# ZEPETO Web Event — Design Tokens

> 이벤트 페이지에서 공통으로 사용하는 디자인 값을 변수화한 문서입니다.
> 피그마 Variables와 1:1 매칭됩니다.

---

## 목차
1. [Typography (타이포그래피)](#1-typography-타이포그래피)
2. [Color (컬러)](#2-color-컬러)
3. [Spacing (간격)](#3-spacing-간격) *(예정)*
4. [사용 방법](#4-사용-방법)

---

## 1. Typography (타이포그래피)

### Font Family

| 토큰 이름 | 값 | 용도 |
|-----------|-----|------|
| `--font-family-display` | SF Pro Display | Title (20px 이상) |
| `--font-family-text` | SF Pro Text | Body, Caption (17px 이하) |

### Font Weight

| 토큰 이름 | 값 | 약어 |
|-----------|-----|------|
| `--font-weight-regular` | 400 | R |
| `--font-weight-medium` | 500 | M |
| `--font-weight-semibold` | 600 | SB |
| `--font-weight-bold` | 700 | B |
| `--font-weight-heavy` | 800 | H |

---

### Title (SF Pro Display)

대제목, 섹션 타이틀 등 큰 텍스트에 사용합니다.

| 피그마 이름 | CSS 토큰 | Size | Weight | Line Height |
|------------|----------|------|--------|-------------|
| Title/64H | `--font-title-64-heavy` | 64px | Heavy (800) | 70px |
| Title/56B | `--font-title-56-bold` | 56px | Bold (700) | 70px |
| Title/48B | `--font-title-48-bold` | 48px | Bold (700) | 60px |
| Title/40H | `--font-title-40-heavy` | 40px | Heavy (800) | 48px |
| Title/36B | `--font-title-36-bold` | 36px | Bold (700) | 44px |
| Title/32B | `--font-title-32-bold` | 32px | Bold (700) | 40px |
| Title/28H | `--font-title-28-heavy` | 28px | Heavy (800) | 36px |
| Title/28B | `--font-title-28-bold` | 28px | Bold (700) | 36px |
| Title/28R | `--font-title-28-regular` | 28px | Regular (400) | 36px |
| Title/26SB | `--font-title-26-semibold` | 26px | Semibold (600) | 32px |
| Title/24B | `--font-title-24-bold` | 24px | Bold (700) | 32px |
| Title/24SB | `--font-title-24-semibold` | 24px | Semibold (600) | 32px |
| Title/22B | `--font-title-22-bold` | 22px | Bold (700) | 28px |
| Title/22SB | `--font-title-22-semibold` | 22px | Semibold (600) | 28px |
| Title/22R | `--font-title-22-regular` | 22px | Regular (400) | 28px |
| Title/20B | `--font-title-20-bold` | 20px | Bold (700) | 28px |
| Title/20SB | `--font-title-20-semibold` | 20px | Semibold (600) | 28px |
| Title/20M | `--font-title-20-medium` | 20px | Medium (500) | 28px |
| Title/20R | `--font-title-20-regular` | 20px | Regular (400) | 28px |

---

### Body (SF Pro Text)

본문, 설명 텍스트에 사용합니다.

| 피그마 이름 | CSS 토큰 | Size | Weight | Line Height |
|------------|----------|------|--------|-------------|
| Body/17B | `--font-body-17-bold` | 17px | Bold (700) | 22px |
| Body/17SB | `--font-body-17-semibold` | 17px | Semibold (600) | 22px |
| Body/17M | `--font-body-17-medium` | 17px | Medium (500) | 22px |
| Body/17R | `--font-body-17-regular` | 17px | Regular (400) | 22px |
| Body/16B | `--font-body-16-bold` | 16px | Bold (700) | 22px |
| Body/16SB | `--font-body-16-semibold` | 16px | Semibold (600) | 22px |
| Body/16M | `--font-body-16-medium` | 16px | Medium (500) | 22px |
| Body/16R | `--font-body-16-regular` | 16px | Regular (400) | 22px |
| Body/15B | `--font-body-15-bold` | 15px | Bold (700) | 20px |
| Body/15SB | `--font-body-15-semibold` | 15px | Semibold (600) | 20px |
| Body/15M | `--font-body-15-medium` | 15px | Medium (500) | 20px |
| Body/15R | `--font-body-15-regular` | 15px | Regular (400) | 20px |
| Body/14B | `--font-body-14-bold` | 14px | Bold (700) | 20px |
| Body/14B_2 | `--font-body-14-bold-sm` | 14px | Bold (700) | 18px |
| Body/14M | `--font-body-14-medium` | 14px | Medium (500) | 20px |
| Body/14M_2 | `--font-body-14-medium-sm` | 14px | Medium (500) | 18px |
| Body/14R | `--font-body-14-regular` | 14px | Regular (400) | 18px |
| Body/13B | `--font-body-13-bold` | 13px | Bold (700) | 18px |
| Body/13SB | `--font-body-13-semibold` | 13px | Semibold (600) | 18px |
| Body/13M | `--font-body-13-medium` | 13px | Medium (500) | 18px |
| Body/13R | `--font-body-13-regular` | 13px | Regular (400) | 18px |

> **참고**: `_2` 또는 `-sm` 접미사가 붙은 토큰은 같은 사이즈에서 줄간격(line-height)이 더 타이트한 변형입니다.

---

### Caption (SF Pro Text)

주석, 부가 정보, 배지 등 작은 텍스트에 사용합니다.

| 피그마 이름 | CSS 토큰 | Size | Weight | Line Height |
|------------|----------|------|--------|-------------|
| Caption/12B | `--font-caption-12-bold` | 12px | Bold (700) | 16px |
| Caption/12SB | `--font-caption-12-semibold` | 12px | Semibold (600) | 16px |
| Caption/12M | `--font-caption-12-medium` | 12px | Medium (500) | 16px |
| Caption/12R | `--font-caption-12-regular` | 12px | Regular (400) | 16px |
| Caption/11B | `--font-caption-11-bold` | 11px | Bold (700) | 16px |
| Caption/11SB | `--font-caption-11-semibold` | 11px | Semibold (600) | 16px |
| Caption/11R | `--font-caption-11-regular` | 11px | Regular (400) | 16px |
| Caption/10SB | `--font-caption-10-semibold` | 10px | Semibold (600) | 14px |
| Caption/10M | `--font-caption-10-medium` | 10px | Medium (500) | 14px |

---

## 2. Color (컬러)

### Gray Solid

불투명한 그레이 계열 색상입니다. 숫자가 클수록 어둡습니다.

| 피그마 이름 | CSS 토큰 | 값 | 용도 |
|------------|----------|-----|------|
| Gray-Solid/Gray 100 | `--color-gray-100` | `#000008` | 블랙 (최진한) |
| Gray-Solid/Gray 84 | `--color-gray-84` | `#292930` | 기본 텍스트 |
| Gray-Solid/Gray 72 | `--color-gray-72` | `#47474D` | 보조 텍스트 (강조) |
| Gray-Solid/Gray 64 | `--color-gray-64` | `#5C5C61` | 보조 텍스트 |
| Gray-Solid/Gray 54 | `--color-gray-54` | `#75757A` | 비활성 텍스트 |
| Gray-Solid/Gray 40 | `--color-gray-40` | `#99999C` | placeholder |
| Gray-Solid/Gray 22 | `--color-gray-22` | `#C7C7C9` | 구분선 (강조) |
| Gray-Solid/Gray 12 | `--color-gray-12` | `#E0E0E1` | 구분선 |
| Gray-Solid/Gray 06 | `--color-gray-06` | `#F0F0F0` | 배경 (연한 그레이) |

---

### Gray Alpha

반투명 그레이 계열입니다. 배경 위에 오버레이할 때 사용합니다.

| 피그마 이름 | CSS 토큰 | 기반색 | 불투명도 |
|------------|----------|--------|---------|
| Gray-Alpha/Gray 84% | `--color-gray-alpha-84` | `#000008` | 84% |
| Gray-Alpha/Gray 72% | `--color-gray-alpha-72` | `#000008` | 72% |
| Gray-Alpha/Gray 64% | `--color-gray-alpha-64` | `#000008` | 64% |
| Gray-Alpha/Gray 54% | `--color-gray-alpha-54` | `#000008` | 54% |
| Gray-Alpha/Gray 40% | `--color-gray-alpha-40` | `#000008` | 40% |
| Gray-Alpha/Gray 22% | `--color-gray-alpha-22` | `#000008` | 22% |
| Gray-Alpha/Gray 12% | `--color-gray-alpha-12` | `#000008` | 12% |
| Gray-Alpha/Gray 06% | `--color-gray-alpha-06` | `#000008` | 6% |

---

### White Solid

불투명 흰색입니다.

| 피그마 이름 | CSS 토큰 | 값 | 불투명도 |
|------------|----------|-----|---------|
| White/White 100 | `--color-white-100` | `#FFFFFF` | 100% |

---

### White Alpha

반투명 흰색 계열입니다. 다크 배경 위 텍스트, 오버레이 등에 사용합니다.

| 피그마 이름 | CSS 토큰 | 기반색 | 불투명도 |
|------------|----------|--------|---------|
| White/White 80% | `--color-white-alpha-80` | `#FFFFFF` | 80% |
| White/White 60% | `--color-white-alpha-60` | `#FFFFFF` | 60% |
| White/White 48% | `--color-white-alpha-48` | `#FFFFFF` | 48% |
| White/White 36% | `--color-white-alpha-36` | `#FFFFFF` | 36% |
| White/White 24% | `--color-white-alpha-24` | `#FFFFFF` | 24% |
| White/White 12% | `--color-white-alpha-12` | `#FFFFFF` | 12% |
| White/White 0% | `--color-white-alpha-00` | `#FFFFFF` | 0% |

---

### Background

페이지 및 섹션 배경색입니다.

| 피그마 이름 | CSS 토큰 | 값 | 용도 |
|------------|----------|-----|------|
| Bg/Offwhite #01 | `--color-bg-offwhite-01` | `#F5F5F6` | 배경 (따뜻한 그레이) |
| Bg/Offwhite #02 | `--color-bg-offwhite-02` | `#F8F8FA` | 배경 (밝은 그레이) |
| Bg/Black 100 | `--color-bg-black-100` | `#000000` | 다크 배경 (100%) |
| Bg/Black 50 | `--color-bg-black-50` | `#000000` | 다크 배경 (50%) |
| Bg/Black 20 | `--color-bg-black-20` | `#000000` | 다크 배경 (20%) |
| Bg/Red10 | `--color-bg-red-10` | `#FFFFFF` → `#FB3559` | 빨간 그라디언트 배경 |

---

### Point (포인트 컬러)

브랜드 색상 및 강조색입니다.

| 피그마 이름 | CSS 토큰 | 값 | 용도 |
|------------|----------|-----|------|
| Point/Primary 100 | `--color-primary` | `#5C46FF` | ZEPETO 브랜드 퍼플 |
| Point/Primary 12 | `--color-primary-12` | `#5C46FF` (12%) | 퍼플 배경 (연한) |
| Point/Primary 05 | `--color-primary-05` | `#5C46FF` (5%) | 퍼플 배경 (매우 연한) |
| Point/Red 100 | `--color-red` | `#FB3559` | 에러, 경고, 핫 |
| Point/Purple 100 | `--color-purple` | `#F323FF` | 보조 퍼플 |
| Point/Yellow 100 | `--color-yellow` | `#FFC700` | 알림, 하이라이트 |
| Point/Premium Blue | `--color-premium-blue` | `#300DB2` | 프리미엄 (블루) |
| Point/Premium Red 100 | `--color-premium-red` | `#FF005C` | 프리미엄 (레드) |

---

### Gradient (그라디언트)

| 피그마 이름 | CSS 토큰 | 용도 |
|------------|----------|------|
| Gradient/Brand Gradient 100 | `--gradient-brand` | 브랜드 그라디언트 |
| Gradient/Premium Plus 100 | `--gradient-premium` | 프리미엄 그라디언트 |

> ⚠️ 그라디언트 정확한 값은 피그마에서 별도 확인 필요

---

## 3. Spacing (간격)

> *다음 단계에서 추가 예정*

---

## 4. 사용 방법

### CSS 파일 임포트
프로젝트 최상위에 `tokens.css` 파일을 두고 임포트합니다.

```html
<link rel="stylesheet" href="tokens.css" />
```

### 사용 예시
```css
/* 이벤트 메인 타이틀 */
.event-hero__title {
  font: var(--font-title-32-bold);
  color: var(--color-text-default);
}

/* 이벤트 설명 */
.event-hero__description {
  font: var(--font-body-15-regular);
  color: var(--color-text-secondary);
}

/* 유의사항 작은 텍스트 */
.event-rules__text {
  font: var(--font-caption-12-regular);
  color: var(--color-gray-54);
}

/* 다크 배경 위 텍스트 */
.event-hero--dark .event-hero__title {
  color: var(--color-text-on-dark);
}

/* CTA 버튼 */
.event-cta {
  background-color: var(--color-accent);
  color: var(--color-white-100);
}

/* 딤 오버레이 */
.event-dim {
  background-color: var(--color-dim);
}
```

### 네이밍 규칙
```
Typography:  --font-{카테고리}-{사이즈}-{굵기}
Color:       --color-{그룹}-{단계}

font 카테고리: title | body | caption
font 굵기:     heavy | bold | semibold | medium | regular

color 그룹:  gray | white | primary | red | ...
color 시맨틱: text-default | text-secondary | border-default | ...
```

---

> 이 문서는 피그마 Variables와 동기화됩니다. 토큰 변경 시 피그마와 이 문서를 함께 업데이트해주세요.
