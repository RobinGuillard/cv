# Robin Guillard - Personal Academic Website

This repository hosts the source code for [robinguillard.github.io](https://robinguillard.github.io/), a personal academic website for Robin Guillard.

## How to Edit This Website

The website is a single-page static site hosted on GitHub Pages. All content is in `index.html` and can be edited directly on GitHub or locally.

---

### Quick Edits on GitHub (No Setup Required)

1. Go to [github.com/RobinGuillard/robinguillard.github.io](https://github.com/RobinGuillard/robinguillard.github.io)
2. Click on `index.html`
3. Click the pencil icon (Edit this file) in the top right
4. Make your changes
5. Click "Commit changes" at the bottom
6. The site will update automatically within 1-2 minutes

---

### Local Editing (Recommended for Larger Changes)

#### Prerequisites
- [Git](https://git-scm.com/downloads) installed on your computer
- A text editor (e.g., [VS Code](https://code.visualstudio.com/))

#### Setup (First Time Only)
```bash
git clone https://github.com/RobinGuillard/robinguillard.github.io.git
cd robinguillard.github.io
```

#### Edit, Preview, and Publish
```bash
# 1. Open index.html in your text editor and make changes

# 2. Preview locally (optional) - open index.html in a browser, or:
python3 -m http.server 8000
# Then visit http://localhost:8000 in your browser

# 3. Push changes
git add .
git commit -m "Describe your changes"
git push
```
The site will update at robinguillard.github.io within 1-2 minutes after pushing.

---

## What to Edit and Where

### Profile Photo
- Replace the file `images/avatar.svg` with your photo
- Recommended: name it `images/headshot.jpg` (or `.jpeg`, `.png`)
- Update the `<img>` tag in `index.html` (search for `avatar.svg`):
  ```html
  <a href="#" class="image avatar">
    <img src="images/headshot.jpg" alt="Robin Guillard" />
  </a>
  ```

### About Section
Search for `<section id="about">` in `index.html`. Edit the `<p>` paragraphs inside.

### Research Interests
Search for `<section id="research">`. Each research topic is an `<article>` block:
```html
<article class="col-6 col-12-xsmall work-item">
  <h3>Your Research Topic Title</h3>
  <p>Description of the research...</p>
</article>
```
To add a new topic, copy-paste an `<article>` block and modify the content.

### Publications
Search for `<section id="publications">`. Publications are in an ordered list `<ol>`:
```html
<li>
  <i>Paper Title.</i>
  <b>R. Guillard</b>, Co-Author1, Co-Author2.
  <a href="URL" class="button primary icon xsmall solid fa-external-link-alt">Journal, Year</a>
</li>
```
To add a new publication, insert a new `<li>` at the desired position.

For papers under review, they are in a `<ul>` list under the "Under Review / Submitted" heading.

### Education & Positions
Search for `<section id="education">`. Positions and education are HTML tables.
To add a new row:
```html
<tr>
  <td>Date Range</td>
  <td>Position/Degree</td>
  <td>Institution</td>
</tr>
```

### Awards
Search for `<section id="awards">`. Same table format as education.

### Contact Information
Search for `<section id="contact">`. Update the address, links, and social media URLs.

### Social Media Links
In the About section, update the `href` attributes:
```html
<a href="https://scholar.google.fr/citations?user=YOUR_ID" target="_blank">Google Scholar</a>
<a href="https://orcid.org/YOUR_ORCID" target="_blank">ORCID</a>
<a href="https://www.linkedin.com/in/YOUR_LINKEDIN/" target="_blank">LinkedIn</a>
<a href="https://github.com/YOUR_GITHUB" target="_blank">GitHub</a>
```

### Page Title and Description
At the top of `index.html`, update:
```html
<title>Robin Guillard | Stanford University</title>
<meta name="description" content="Your description here" />
```

### Color Scheme
The accent color is `#6050DC` (purple). To change it:
1. Open `assets/css/custom.css`
2. Find-and-replace `#6050DC` with your preferred hex color
3. Also replace the variant shades: `#7B6FE3` (lighter), `#4E40C0` (darker), `#8A7DE8` (lightest), `#3D2F8A` (darkest)

### Institution Logo (Footer)
Replace `images/stanford_logo.svg` with your institution's logo, and update the link in the footer section of `index.html`.

---

## File Structure

```
robinguillard.github.io/
  index.html              -- Main (and only) page content
  images/
    avatar.svg            -- Profile photo (replace with your headshot)
    stanford_logo.svg     -- Institution logo in sidebar
  assets/
    css/
      custom.css          -- Main stylesheet (purple theme)
      fontawesome-all.min.css  -- Icon library
      main.css            -- Original blue theme (backup)
      images/
        overlay.png       -- Background overlay texture
    js/
      main.js             -- Site behavior (navigation, parallax, etc.)
      util.js             -- Utility functions
      jquery.min.js       -- jQuery library
      (other .min.js)     -- Vendor plugins
    webfonts/             -- FontAwesome icon fonts
  .nojekyll               -- Tells GitHub Pages not to process with Jekyll
  .gitignore              -- Files to exclude from git
  README.md               -- This file
```

---

## Tips

- **Bold your name** in publication lists using `<b>R. Guillard</b>`
- **Add links** with `<a href="URL" target="_blank">Link Text</a>`
- **Special characters**: Use HTML entities like `&eacute;` for e, `&ndash;` for en-dash, `&amp;` for &
- **Icons**: Browse available icons at [Font Awesome 5](https://fontawesome.com/v5/search?o=r&m=free). Use them as `<i class="fas fa-icon-name"></i>` (solid) or `<i class="fab fa-icon-name"></i>` (brands)
- **Test before pushing**: Always preview locally by opening `index.html` in a browser before committing changes

---

## Credits

Template based on the [Flatiron Institute Public User Page](https://github.com/flatironinstitute/flatiron-user-page) (Strata theme by @ajlkn). Licensed under Apache 2.0.
