# Profile Image Download Instructions

## Image URL

Your profile image URL:
```
https://lh3.googleusercontent.com/sitesv/APaQ0STCrVX99sOXJgWJiwPm8a4SYKNf29vM06VviukLHU22NaPKVDIMCNlKvXEkO2u8a9qEzay29wQt5GRFVtNmV478vZWj39YM4Qc_xhTLZqTy8WPQyqb1jQKJ5_f32__T08bmJMI-E4cOQG8NykcrA7q4qxUwIDm1hVryA4pToRpg-ljCGOFLSA8Dmd_ByaNRqI8lxA=w1280
```

## How to Download

### Method 1: Direct Browser Download

1. Open the URL above in your browser
2. Right-click on the image
3. "Save image as..." → Save as `profile.jpg`
4. Move the file to `images/profile.jpg` in this directory

### Method 2: From Google Sites

1. Visit https://sites.google.com/view/yjkwon
2. Right-click on your profile photo
3. "Save image as..." → Save as `profile.jpg`
4. Move the file to `images/profile.jpg`

### Method 3: Using wget (if network allows)

```bash
cd images/
wget "https://lh3.googleusercontent.com/sitesv/APaQ0STCrVX99sOXJgWJiwPm8a4SYKNf29vM06VviukLHU22NaPKVDIMCNlKvXEkO2u8a9qEzay29wQt5GRFVtNmV478vZWj39YM4Qc_xhTLZqTy8WPQyqb1jQKJ5_f32__T08bmJMI-E4cOQG8NykcrA7q4qxUwIDm1hVryA4pToRpg-ljCGOFLSA8Dmd_ByaNRqI8lxA=w1280" -O profile.jpg
```

## Verify

After downloading, check that the file exists:

```bash
ls -lh images/
# Should show profile.jpg
```

## Preview

After adding the image:

```bash
quarto preview
```

Your profile photo should now appear on the left side of the homepage!
