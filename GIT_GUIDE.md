# Git 사용 가이드

## ✅ 준비 완료

이 디렉토리는 Git으로 관리할 준비가 되어 있습니다.

**정리 완료:**
- ✅ `_site/` 폴더 제거 (빌드 결과물)
- ✅ `.quarto/` 폴더 제거 (임시 파일)
- ✅ `.gitignore` 업데이트 완료

---

## 🚀 Git 초기 설정

### 1. Git 저장소 초기화

```bash
cd ~/homepage2  # 또는 실제 경로
git init
```

### 2. 파일 추가

```bash
# 모든 파일 추가
git add .

# 또는 선택적으로
git add *.qmd *.yml *.css *.md images/
```

### 3. 첫 커밋

```bash
git commit -m "Initial commit: Academic homepage"
```

---

## 📦 GitHub에 푸시

### 1. GitHub에서 새 저장소 생성

GitHub에서 새 repository 생성 (예: `homepage`)

### 2. Remote 추가

```bash
# HTTPS
git remote add origin https://github.com/YOUR_USERNAME/homepage.git

# 또는 SSH
git remote add origin git@github.com:YOUR_USERNAME/homepage.git
```

### 3. 푸시

```bash
git branch -M main
git push -u origin main
```

---

## 🔄 일반적인 Git 워크플로우

### 파일 수정 후

```bash
# 변경사항 확인
git status

# 변경사항 보기
git diff

# 파일 추가
git add index.qmd style.css  # 수정한 파일들

# 커밋
git commit -m "Update bio section and styling"

# 푸시
git push
```

### 새 이미지 추가

```bash
git add images/new-photo.jpg
git commit -m "Add new group photo"
git push
```

---

## 🌐 Cloudflare Pages 배포

### 설정

1. Cloudflare Pages에서 GitHub 저장소 연결
2. Build settings:
   - **Build command**: `quarto render`
   - **Build output directory**: `_site`
   - **Root directory**: `/` (기본값)

### 자동 배포

```bash
# 로컬에서 수정
vim index.qmd

# Git 푸시
git add index.qmd
git commit -m "Update publications"
git push

# → Cloudflare가 자동으로 빌드 & 배포!
```

---

## 📋 .gitignore 설명

현재 `.gitignore`에 포함된 항목:

```bash
# Quarto 빌드 결과
/.quarto/      # Quarto 임시 파일
/_site/        # 빌드된 HTML (배포시에만 필요)

# OS 파일
.DS_Store      # macOS
Thumbs.db      # Windows

# 로그
*.log

# Quarto 중간 파일
**/*.quarto_ipynb

# 에디터 파일
.vscode/       # VS Code 설정
.idea/         # IntelliJ/PyCharm
*.swp, *.swo   # Vim
*~             # 백업 파일
```

---

## 💡 유용한 Git 명령어

### 상태 확인

```bash
git status           # 변경사항 확인
git log              # 커밋 히스토리
git log --oneline    # 간단한 히스토리
```

### 변경사항 되돌리기

```bash
# 마지막 커밋 취소 (파일은 유지)
git reset --soft HEAD~1

# 파일 변경사항 취소
git checkout -- index.qmd

# 스테이징 취소
git reset HEAD index.qmd
```

### 브랜치 사용

```bash
# 새 브랜치 생성 및 전환
git checkout -b feature/new-design

# 수정 후 커밋
git add .
git commit -m "Redesign layout"

# main으로 전환 후 병합
git checkout main
git merge feature/new-design

# 푸시
git push
```

---

## 🔧 Quarto 빌드 & 로컬 테스트

### Preview (Git 추적 안 됨)

```bash
quarto preview
# → _site와 .quarto 폴더 생성
# → .gitignore에 있어서 Git에 포함 안 됨
```

### 빌드만

```bash
quarto render
# → _site 폴더만 생성
```

### 정리

```bash
# 빌드 결과물 삭제
rm -rf _site .quarto
```

---

## 📝 권장 커밋 메시지 스타일

```bash
# 새 기능
git commit -m "Add research interests section"

# 버그 수정
git commit -m "Fix profile image alignment"

# 스타일 변경
git commit -m "Update heading colors to navy blue"

# 내용 업데이트
git commit -m "Update publications for 2026"

# 이미지 추가
git commit -m "Add group photo from lab retreat"
```

---

## ⚠️ 주의사항

### 커밋하지 말아야 할 것

- ❌ `_site/` 폴더 (빌드 결과물)
- ❌ `.quarto/` 폴더 (임시 파일)
- ❌ 개인 설정 파일 (`.vscode/`, `.idea/`)
- ❌ 큰 바이너리 파일 (비디오 등)

### 커밋해야 할 것

- ✅ `.qmd` 파일 (소스)
- ✅ `.yml`, `.css` 파일 (설정)
- ✅ `.md` 문서
- ✅ 이미지 (`images/` 폴더)
- ✅ `.gitignore`

---

## 🎯 체크리스트

### 초기 설정
- [ ] `git init`
- [ ] 파일 추가 (`git add .`)
- [ ] 첫 커밋 (`git commit`)
- [ ] GitHub 저장소 생성
- [ ] Remote 추가
- [ ] 푸시 (`git push`)

### 배포 설정
- [ ] Cloudflare Pages 연결
- [ ] Build command: `quarto render`
- [ ] Output: `_site`
- [ ] 자동 배포 확인

### 일상 작업
- [ ] 로컬에서 수정
- [ ] `quarto preview`로 확인
- [ ] `git add` & `git commit`
- [ ] `git push`
- [ ] Cloudflare 자동 배포 확인

---

## 📞 문제 해결

### "_site 폴더가 계속 추적됨"

```bash
# Git 캐시에서 제거
git rm -r --cached _site
git commit -m "Remove _site from tracking"
git push
```

### "변경사항이 너무 많음"

```bash
# .gitignore가 제대로 작동하는지 확인
git status --ignored

# 이미 추적 중인 파일 확인
git ls-files
```

---

## 🚀 완료!

이제 Git으로 홈페이지를 관리할 준비가 되었습니다!

```bash
git init
git add .
git commit -m "Initial commit: Academic homepage"
git remote add origin YOUR_REPO_URL
git push -u origin main
```

Happy coding! 🎉
