# Chris 템플릿 vs 원본 Google Sites 비교

## 🎨 디자인 변화

### Chris 템플릿의 특징

**레이아웃:**
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  [큰 프로필]     이름
   사진          Youngjin Kwon
  (250px)        
                 [소셜 링크들]
                 Email
                 Google Scholar
                 DBLP
                 LinkedIn
                 
                 Bio 텍스트...
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**vs Google Sites 원본:**
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Bio 텍스트...      [프로필 사진]
                   (우측 float)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### 주요 차이점

| 요소 | Google Sites | Chris 템플릿 |
|------|--------------|--------------|
| **프로필 사진** | 우측 float, 200px | 좌측 고정, 250px |
| **소셜 링크** | 가로 나열 | 세로 나열 |
| **TOC** | 없음 | 우측 사이드바 |
| **섹션 구분** | 최소 | 명확한 헤딩 + 밑줄 |
| **전체 느낌** | 심플 | Academic professional |

---

## ✅ 보존된 모든 컨텐츠

### 1. Bio 정보 (100%)
- ✅ Associate Professor, KAIST, CASYS
- ✅ Best paper awards (SOSP'24, SOSP'21, ATC'18)
- ✅ 모든 수상 내역 (EWON, Google Scholar, KAIST Breakthrough, etc.)
- ✅ Email 및 링크

### 2. Research Interests (신규 추가!)
Chris 템플릿에 맞춰 **상세한 연구 분야**를 bullet point로 정리:
- AI Systems
- Memory Systems
- Operating Systems
- Storage Systems
- Computer Architecture

각 분야별로 구체적인 토픽 나열

### 3. Awards & Honors (재구성)
원본의 수상 내역을 **별도 섹션**으로 분리:
- Best Paper Awards (3개)
- Institutional Recognition (6개)

### 4. Recent Publications (100%)
원본의 13개 논문 모두 포함:
- BEAM (MLSYS 2026)
- PIM-malloc (HPCA 2026)
- CofferOS (EUROSYS 2026)
- MTTM (EUROSYS 2026)
- BASK (EUROSYS 2026)
- SAND (SOSP 2025)
- Scalable Address Spaces (SOSP 2025)
- Defeating Use-After-Free (S&P 2025)
- Lossless Acceleration (NAACL 2025)
- Adios (EuroSys 2025)
- OZZ (SOSP 2024) - Best paper
- BUDAlloc (SECURITY 2024)
- On-/Off-CPU Bottlenecks (OSDI 2024)

### 5. Teaching (100% + 개선)
원본의 3개 강의 모두 포함 + 강의 설명 추가:
- CS492 (Virtualization)
- CS330 (OS and Labs)
- CS530 (Graduate OS)

**신규 추가:**
- Teaching philosophy
- Teaching award 별도 표시

### 6. Professional Service (100%)
원본의 모든 내용 포함:
- Conference Leadership (재구성)
- Program Committees (2018-2026)
- Editorial Boards

### 7. Student Opportunities (확장)
원본 인턴십 공지 + 상세 정보:
- Research areas (상세)
- Application process (단계별)
- What to expect
- FAQ

---

## 📏 레이아웃 상세

### Spacing (Tight!)

```css
h2: margin-top: 35px, margin-bottom: 12px
p: margin: 10px 0
li: margin: 4px 0
```

### 프로필 섹션

```css
Grid: 250px (이미지) + 1fr (컨텐츠)
Gap: 30px
```

### 색상

```css
텍스트: #333
링크: #1a73e8 (Google blue)
헤딩: #222
Border: #e0e0e0
```

---

## 📁 파일 구조

```
quarto-chris-style/
├── _quarto.yml          # TOC 활성화
├── style.css            # Chris 스타일 + Tight
├── index.qmd            # 메인 (Bio, Awards, Publications)
├── publication.qmd      # 전체 논문 (연도별)
├── teaching.qmd         # 강의 (상세 설명)
├── members.qmd          # 멤버
├── internship.qmd       # 학생 모집 (상세)
└── images/
    ├── profile.jpg      # 큰 프로필 사진
    └── group-photo.jpg  # 그룹 사진
```

---

## 🎯 Chris 템플릿 적용 이유

### 장점:

1. **Academic credibility**: 프로필 사진이 크고 prominent
2. **Clear organization**: 섹션 구분이 명확
3. **Navigation**: TOC로 빠른 이동
4. **Professional**: 학술 홈페이지로 적합
5. **Scalable**: 컨텐츠 추가가 쉬움

### 유지된 점:

1. **Tight spacing**: 원본처럼 여백 최소화
2. **All content**: 모든 원본 내용 보존
3. **Academic tone**: 학술적 톤 유지

---

## 🚀 다음 단계

### 1. 이미지 추가
```bash
images/profile.jpg       # 500x500px 이상
images/group-photo.jpg   # 800-1200px 너비
```

### 2. Preview
```bash
quarto preview
```

### 3. 조정 필요 시
- 프로필 사진 크기
- 여백 조정
- 색상 변경
- 섹션 순서

---

## 💡 주요 개선사항

### 원본 → Chris 템플릿

**구조:**
```
단순 나열 → 섹션별 조직화
```

**프로필:**
```
작은 사진 (200px) → 큰 사진 (250px)
우측 float → 좌측 고정 그리드
```

**네비게이션:**
```
상단 메뉴만 → 메뉴 + TOC 사이드바
```

**컨텐츠:**
```
압축된 정보 → 확장된 설명
```

**예:**
- Teaching: 링크만 → 강의 설명 + 철학
- Internship: 간단 공지 → 상세 가이드
- Research: 없음 → Interests 섹션 신규

---

## 📊 Before & After

### Home 페이지

**Before (Google Sites):**
- Bio (5줄)
- Awards (bio 안에)
- Recent publications (13개)
- 사진 2개

**After (Chris 템플릿):**
- Large profile + Social links
- Bio (확장)
- Research Interests (신규)
- Awards & Honors (별도 섹션)
- Selected Recent Publications
- Teaching (요약)
- Professional Service (요약)
- Student Opportunities (요약)
- Group photo

**결과:** 더 많은 정보를 **더 명확하게** 제공

---

## 🎨 Visual Comparison

### Google Sites
```
Simple, minimal, tight
━━━━━━━━━━━━━━━━━
Text...  [Photo]
         (small)

Publications
• item
• item

Links
━━━━━━━━━━━━━━━━━
```

### Chris Template
```
Professional, organized, clear
━━━━━━━━━━━━━━━━━━━━━━━━━━
[LARGE    |  Name
 PHOTO]   |  Links (vertical)
          |  
          |  ## Bio
          |  Text...
          |
          |  ## Research Interests
          |  • Area 1
          |  • Area 2
━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## ✨ 결론

**모든 원본 컨텐츠 보존 + Chris 템플릿의 장점 활용**

- ✅ 빠진 내용 없음
- ✅ Tight layout 유지
- ✅ Academic professional 느낌
- ✅ Navigation 개선
- ✅ 확장성 확보
