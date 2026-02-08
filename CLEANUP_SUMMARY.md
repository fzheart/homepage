# 홈페이지 정리 완료 - Git Ready 버전

## ✅ 완료 사항

### 1. 중간 파일 제거
- ❌ `_site/` 폴더 삭제 (빌드 결과물)
- ❌ `.quarto/` 폴더 삭제 (Quarto 임시 파일)

### 2. .gitignore 업데이트

**추가된 항목:**
```
# Quarto build outputs
/.quarto/
/_site/

# OS files
.DS_Store
Thumbs.db

# Logs
*.log

# Quarto intermediate files
**/*.quarto_ipynb

# Editor files
.vscode/
.idea/
*.swp
*.swo
*~

# Temporary files
*.tmp
.Rproj.user
```

### 3. Git 가이드 추가
- `GIT_GUIDE.md` 파일 생성
- Git 초기 설정부터 Cloudflare 배포까지 전체 워크플로우 포함

---

## 📁 최종 파일 구조

```
homepage2/
├── .gitignore              ✅ 업데이트됨
├── _quarto.yml             
├── style.css               
├── index.qmd               
├── publication.qmd         
├── teaching.qmd            
├── members.qmd             
├── internship.qmd          
├── images/
│   ├── profile.jpg         
│   └── DOWNLOAD_PROFILE.md 
├── README.md               
├── GIT_GUIDE.md            🆕 새로 추가
├── CHANGELOG_V3.md         
├── CUSTOMIZATION_GUIDE.md  
└── DESIGN_COMPARISON.md    
```

**제거된 항목:**
- ❌ `_site/` (약 4MB - 빌드 결과물)
- ❌ `.quarto/` (임시 캐시)

---

## 🚀 Git 시작하기

### 빠른 시작

```bash
# 1. 압축 해제
tar -xzf homepage-clean.tar.gz
cd homepage2

# 2. Git 초기화
git init

# 3. 파일 추가
git add .

# 4. 첫 커밋
git commit -m "Initial commit: Academic homepage"

# 5. GitHub 저장소와 연결
git remote add origin https://github.com/YOUR_USERNAME/homepage.git

# 6. 푸시
git branch -M main
git push -u origin main
```

자세한 내용은 `GIT_GUIDE.md` 참고!

---

## 🌐 Cloudflare Pages 배포

### 1. Cloudflare Pages 설정

- GitHub 저장소 연결
- **Build command**: `quarto render`
- **Build output**: `_site`

### 2. 자동 배포

```bash
# 로컬에서 수정
vim index.qmd

# 푸시
git add index.qmd
git commit -m "Update bio"
git push

# → Cloudflare가 자동으로 빌드 & 배포!
```

---

## 🔄 일상적인 워크플로우

### 수정 → 확인 → 배포

```bash
# 1. 파일 수정
vim index.qmd style.css

# 2. 로컬에서 확인
quarto preview

# 3. Git에 커밋
git add index.qmd style.css
git commit -m "Update layout and styling"

# 4. 푸시
git push

# 5. Cloudflare가 자동 배포
```

---

## ⚠️ 주의사항

### quarto preview 실행 시

```bash
quarto preview
# → _site/, .quarto/ 폴더 생성됨
# → .gitignore에 포함되어 Git 추적 안 됨 ✅
```

### git status 확인

```bash
git status
# _site/와 .quarto/가 보이지 않아야 정상 ✅
```

### 빌드 파일 정리

```bash
# 필요시 수동 삭제 가능
rm -rf _site .quarto
```

---

## 📋 체크리스트

### Git 초기 설정
- [ ] `git init`
- [ ] `git add .`
- [ ] `git commit -m "Initial commit"`
- [ ] GitHub 저장소 생성
- [ ] `git remote add origin ...`
- [ ] `git push -u origin main`

### Cloudflare 배포
- [ ] Cloudflare Pages에서 저장소 연결
- [ ] Build command: `quarto render` 설정
- [ ] Output directory: `_site` 설정
- [ ] 첫 배포 확인

### 확인 사항
- [ ] `git status` 시 _site, .quarto 안 보임
- [ ] `quarto preview` 정상 작동
- [ ] 이미지 파일 (`images/profile.jpg`) 존재
- [ ] 로컬 preview 정상 작동

---

## 💡 유용한 팁

### 수정사항 확인

```bash
git status          # 변경된 파일 확인
git diff            # 변경 내용 확인
git log --oneline   # 커밋 히스토리
```

### 브랜치로 작업

```bash
# 실험적 변경은 브랜치에서
git checkout -b experiment/new-layout
# 수정 & 테스트
git add .
git commit -m "Try new layout"

# 만족하면 메인에 병합
git checkout main
git merge experiment/new-layout
git push
```

### 긴급 롤백

```bash
# 마지막 커밋 취소
git reset --soft HEAD~1

# 파일 변경 취소
git checkout -- index.qmd
```

---

## 📞 추가 도움말

**전체 가이드:** `GIT_GUIDE.md`

**커스터마이징:** `CUSTOMIZATION_GUIDE.md`

**디자인 설명:** `DESIGN_COMPARISON.md`

**변경사항:** `CHANGELOG_V3.md`

---

## 🎉 준비 완료!

이제 Git으로 버전 관리하면서 자동 배포할 수 있습니다!

```bash
git init && git add . && git commit -m "Initial commit"
```

Happy coding! 🚀
