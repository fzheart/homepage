# Youngjin Kwon's Academic Homepage

**Chris von Csefalvay inspired design with tight layout**

## 🎯 Design Features

This website is inspired by [Chris von Csefalvay's homepage](https://chrisvoncsefalvay.com/) with the following features:

- ✅ **Large profile image** on the left with bio on the right
- ✅ **Academic style** with clear section organization
- ✅ **Tight layout** with minimal spacing
- ✅ **All original content preserved** from Google Sites
- ✅ **Table of contents** on the right for easy navigation
- ✅ **Professional presentation** suitable for academic websites

## 📁 Structure

```
.
├── _quarto.yml       # Site configuration
├── style.css         # Custom styling (Chris-inspired, tight)
├── index.qmd         # Home page with bio, awards, publications
├── publication.qmd   # Complete publication list
├── teaching.qmd      # Teaching info
├── members.qmd       # Lab members
├── internship.qmd    # Student opportunities
└── images/
    ├── profile.jpg      # Main profile photo (required)
    └── group-photo.jpg  # Lab group photo (required)
```

## 🚀 Quick Start

```bash
# Preview
quarto preview

# Build
quarto render
```

## 📸 Required Images

You need two images:

### 1. profile.jpg
- Your main profile photo
- Will be displayed large (250px width) on the left side
- Recommended: 500x500px or larger, square format

### 2. group-photo.jpg
- Lab group photo
- Displayed at the bottom of home page
- Recommended: 800-1200px width

**How to get images from Google Sites:**

```bash
# Visit https://sites.google.com/view/yjkwon
# Right-click on images → "Save image as..."
# Save to images/ folder with correct names
```

Or use wget if you have the URLs:
```bash
wget "IMAGE_URL" -O images/profile.jpg
wget "IMAGE_URL" -O images/group-photo.jpg
```

## 🎨 Design Details

### Layout
- **Profile section**: Side-by-side grid (250px image + content)
- **Headings**: Clear hierarchy with bottom borders
- **Spacing**: Tight margins (10-12px between elements)
- **Width**: Max 1000px content width

### Colors
- Text: #333 (dark gray)
- Links: #1a73e8 (Google blue)
- Headings: #222
- Borders: #e0e0e0 (light gray)

### Typography
- Font: System font stack (San Francisco, Segoe UI, Roboto)
- Body: 15px
- Headings: 1.6-2.2em

## 📝 Content Included

All content from your Google Sites page is preserved:

- ✅ Complete bio with awards and recognition
- ✅ All 13 recent publications
- ✅ Research interests (detailed breakdown)
- ✅ Teaching (3 courses with descriptions)
- ✅ Professional service (PC, organizing, editorial)
- ✅ Student opportunities (internship notice)
- ✅ Links to Google Scholar, DBLP, LinkedIn

## 🌐 Deploy

### GitHub + Cloudflare Pages

```bash
git init
git add .
git commit -m "Initial commit: Chris-style homepage"
git remote add origin YOUR_REPO_URL
git push -u origin main
```

Cloudflare Pages settings:
- Build command: `quarto render`
- Output directory: `_site`

## ✏️ Customization

### Change profile image size

Edit `style.css`:

```css
.profile-section {
  grid-template-columns: 250px 1fr;  /* Change 250px */
}
```

### Adjust spacing

```css
h2 {
  margin-top: 35px;  /* Increase for more space */
  margin-bottom: 12px;
}
```

### Modify colors

```css
a {
  color: #1a73e8;  /* Change link color */
}

h2 {
  border-bottom: 2px solid #e0e0e0;  /* Change border */
}
```

## 📋 TODO

- [ ] Add `images/profile.jpg`
- [ ] Add `images/group-photo.jpg`
- [ ] Complete publication list (2018-2023 papers)
- [ ] Add lab members (PhD, MS, undergrad students)
- [ ] Add full author lists to publications
- [ ] Update with specific paper titles for SOSP'21, ATC'18

## 🔧 Tips

### Adding publications

Edit `publication.qmd`:

```markdown
**Paper Title.** Author1, Author2, **Kwon Y**, Author3. 
*Conference Name (ACRONYM)* Year. 
```

### Adding lab members

Edit `members.qmd`:

```markdown
**Student Name** (PhD, 20XX-)  
Research: Topic description  
```

### Updating research interests

Edit the bullet points in `index.qmd` under "Research Interests"

## 📧 Contact

Youngjin Kwon  
Associate Professor  
KAIST School of Computing  
Email: yjkwon@kaist.ac.kr

---

**Template inspired by**: [Chris von Csefalvay](https://chrisvoncsefalvay.com/)  
**Built with**: [Quarto](https://quarto.org/)
