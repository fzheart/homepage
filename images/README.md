# Images Directory

## Required Images

### profile.jpg
- **Usage**: Main profile photo, displayed large on the left side of home page
- **Size**: 500x500px or larger, square format recommended
- **Position**: Left side of the page, 250px display width

### group-photo.jpg
- **Usage**: Lab group photo, displayed at bottom of home page
- **Size**: 800-1200px width recommended
- **Position**: Centered, below the main content

## How to Add Images

### From Google Sites:

1. Visit https://sites.google.com/view/yjkwon
2. Right-click on your profile photo
3. "Save image as..." → Save as `profile.jpg` in this folder
4. Right-click on the group photo
5. "Save image as..." → Save as `group-photo.jpg` in this folder

### Using wget (if you have URLs):

```bash
# Profile photo
wget "YOUR_PROFILE_PHOTO_URL" -O profile.jpg

# Group photo
wget "YOUR_GROUP_PHOTO_URL" -O group-photo.jpg
```

### Optimization (optional):

If images are very large, you can resize them:

```bash
# Install ImageMagick first
# brew install imagemagick  (Mac)
# sudo apt install imagemagick  (Linux)

# Resize profile photo
convert profile.jpg -resize 800x800 profile.jpg

# Resize group photo
convert group-photo.jpg -resize 1200x group-photo.jpg
```

## Verify

After adding images, check they exist:

```bash
ls -lh
# Should show:
# profile.jpg
# group-photo.jpg
```

Then preview the site:

```bash
cd ..
quarto preview
```
