# Version 3 변경사항

## ✅ 완료된 수정사항

### 1. Research Interests → Bio에 병합 ✅

**변경 전:**
```
## Bio
(짧은 bio)

## Research Interests
* AI Systems: ...
* Memory Systems: ...
* Operating Systems: ...
* Storage Systems: ...
* Computer Architecture: ...
```

**변경 후:**
```
## Bio
(확장된 bio with research interests inline)

"My research interests span AI systems (LLM serving, GPU computing), 
memory systems (disaggregation, CXL, PIM), operating systems 
(kernel optimization, virtualization, security), storage systems 
(file systems, databases, SSD), and computer architecture 
(CPU/GPU offloading, SmartNIC)."
```

**효과:** 더 간결하고 흐름이 자연스러움

---

### 2. Selected Recent Publications 타이트하게 ✅

**제거됨:**
```
Authors TBD.  ← 모두 제거
```

**추가된 스타일:** `style.css`
```css
/* Publications - tighter spacing */
#selected-recent-publications + p {
  margin: 6px 0;  /* 10px → 6px */
  line-height: 1.5;  /* 더 타이트 */
}
```

**효과:** 논문 목록이 더 간결하고 읽기 쉬움

---

### 3. Complete List 링크 강조 ✅

**변경 전:**
```
See the complete list on my Publications page or Google Scholar.
```

**변경 후:**
```
┌─────────────────────────────────────┐
│ See the complete list on my         │
│ Publications page or Google Scholar │
└─────────────────────────────────────┘
(회색 박스 + 남색 왼쪽 테두리 + 큰 폰트)
```

**스타일 추가:** `style.css`
```css
.complete-list-link {
  margin-top: 20px;
  padding: 15px;
  background: #f8f9fa;
  border-left: 4px solid #1e3a8a;
  font-size: 1.1em;      /* 폰트 크게 */
  font-weight: 600;      /* 굵게 */
}
```

**효과:** 전체 논문 리스트로 가는 링크가 눈에 확 띔

---

### 4. Student Opportunities → Internship ✅

**변경된 파일:**
- `index.qmd`: 섹션 제목
- `internship.qmd`: 페이지 제목

**효과:** 더 직관적인 명칭

---

### 5. 프로필 이미지 다운로드 안내 ✅

**문제:** 네트워크 제한으로 자동 다운로드 실패

**해결:** `images/DOWNLOAD_PROFILE.md` 생성
- 이미지 URL 제공
- 3가지 다운로드 방법 안내
- 파일명: `profile.jpg`로 저장
- 위치: `images/` 폴더

---

## 📁 수정된 파일

```
index.qmd
├── Bio 섹션 수정 (Research Interests 병합)
├── Publications 섹션 수정 (Authors TBD 제거)
├── Complete list 링크 스타일 추가
└── Student Opportunities → Internship

internship.qmd
└── 제목 변경

style.css
├── Publications tighter spacing 추가
└── Complete list link 스타일 추가

images/DOWNLOAD_PROFILE.md
└── 프로필 이미지 다운로드 가이드 (신규)
```

---

## 🎯 결과 미리보기

### Bio Section
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
┌─────────────────────────────┐
│  Bio                        │
└─────────────────────────────┘

Associate Professor...
My research interests span AI systems 
(LLM serving, GPU computing), memory 
systems (disaggregation, CXL, PIM), ...

Best paper awards...
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Publications Section
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
┌─────────────────────────────┐
│  Selected Recent Publications│
└─────────────────────────────┘

BEAM: Joint Resource–Power... MLSYS 2026.
PIM-malloc: A Fast and... HPCA 2026.
...

┌────────────────────────────────┐
│ See the complete list on my    │
│ Publications page or Google... │
└────────────────────────────────┘
    ↑ 크고 눈에 띄는 링크
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 📋 남은 작업

### 필수
- [ ] 프로필 이미지 다운로드
  - 방법: `images/DOWNLOAD_PROFILE.md` 참고
  - 파일: `images/profile.jpg`
  
- [ ] 그룹 사진 다운로드 (선택)
  - 파일: `images/group-photo.jpg`

### 선택
- [ ] Preview로 확인
  - `quarto preview`
  - 레이아웃 확인
  - 색상 조정 필요 시 요청

---

## 🚀 다음 단계

```bash
# 1. 압축 해제
tar -xzf homepage-chris-style-v3.tar.gz
cd quarto-chris-style

# 2. 프로필 이미지 다운로드
# images/DOWNLOAD_PROFILE.md 참고

# 3. Preview
quarto preview
```

---

## 💡 추가 조정 가능

만족스럽지 않다면 다음을 조정 가능:

**Publications 간격 더 좁히기:**
```css
/* style.css */
#selected-recent-publications + p {
  margin: 4px 0;  /* 6px → 4px */
}
```

**Complete list 박스 색상 변경:**
```css
.complete-list-link {
  background: #e0f2fe;  /* 연한 파란색 */
  border-left: 4px solid #0284c7;
}
```

**Bio 텍스트 조정:**
- `index.qmd`의 Bio 섹션 직접 편집
