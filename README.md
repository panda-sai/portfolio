# Portfolio Templates

Two ready-to-use, single-file portfolio websites. No build tools, no installs. Open the `.html` file in a browser, edit the text and publish.

| File | Who it's for | Style |
|---|---|---|
| `fresher-portfolio.html` | Students and recent graduates looking for a first job or internship | Dark, glowing gradients, glass cards |
| `freelancer-portfolio.html` | Freelancers and independent studios looking for clients | Light, editorial, magazine-style |

---

## Quick start (5 minutes)

1. **Make a copy** of the file you want, e.g. `freelancer-portfolio.html` → `index.html`.
2. **Open it in a code editor.** [VS Code](https://code.visualstudio.com/) is free; any text editor works.
3. **Find and replace the placeholders.** Everything you need to change is in `[square brackets]`.
   In VS Code, press `Cmd+Shift+F` (Mac) or `Ctrl+Shift+F` (Windows) and search for `[` to find them all.
4. **Open the file in your browser** to preview. Refresh after each save.
5. **Publish it** (see [Publishing](#publishing-for-free)).

> **Tip:** Replace the whole placeholder, brackets included.
> `[Your Name]` → `Priya Sharma`, not `[Priya Sharma]`.

---

## What's in each template

### Fresher portfolio
| Section | What to put there |
|---|---|
| Hero | Name, job titles you're aiming for, a 2–3 line summary, CV link, social links |
| Skills strip | 8 skills that scroll across the page |
| About | Your story, CGPA, project and certification counts, location, interests, languages |
| Skills | Skill bars (with a percentage), tools grid, soft skills |
| Projects | 4 project cards with category filters, tech tags, demo and code links |
| Journey | Education timeline and an internships/activities timeline |
| Certifications | 6 cards for certificates, awards, hackathons, papers |
| Resume | Download button for your CV |
| Contact | Email, phone, location, LinkedIn and a contact form |

### Freelancer portfolio
| Section | What to put there |
|---|---|
| Loader and header | Your name, booking availability ("Booking March 2027") |
| Hero | Value proposition, rotating words, 3 stats |
| Client logos | Names of clients you've worked with |
| About | Your portrait, intro paragraph, philosophy, ideal clients |
| Services | 4 services with a description and deliverables |
| Selected work | 4 case studies with a result badge ("+240% conversions") |
| Process | 4 steps with how long each one takes |
| Pricing | 3 plans with per-project and monthly prices |
| Testimonials | Client quotes (as many as you like) |
| FAQ | Questions and answers |
| Contact and footer | Email, phone, Calendly, enquiry form, social and freelance-platform links |

---

## Common edits

### Change your name and initials
- Search for `[Your Name]` and `[YOUR NAME]` (the large faded text in the footer).
- **Fresher:** the `YN` initials appear in the nav logo and the photo circle. Search for `YN`.
- Update the `<title>` and `<meta name="description">` at the top of the file. They show in browser tabs and Google results.

### Change the colours
All colours are set at the top of the `<style>` block in `:root`.

**Fresher**
```css
--bg: #05060a;   /* page background */
--a1: #7c5cff;   /* purple accent */
--a2: #22d3ee;   /* cyan accent */
--a3: #f472b6;   /* pink accent */
```

**Freelancer**
```css
--cream: #f3efe7;    /* light background */
--ink: #0f0f0e;      /* dark text and dark sections */
--accent: #ff5b2e;   /* orange highlight */
--accent-2: #d4ff3a; /* lime highlight */
```
Change these values and the whole site updates. [coolors.co](https://coolors.co) is a good place to find palettes.

### Change the fonts
1. Pick fonts on [Google Fonts](https://fonts.google.com) and copy the `<link>` tag it gives you.
2. Replace the existing `<link href="https://fonts.googleapis.com/css2?...">` in the `<head>`.
3. Search the CSS for the old font names and replace them:
   - Fresher: `'Space Grotesk'` (headings), `'Inter'` (body), `'JetBrains Mono'` (small labels)
   - Freelancer: `'Instrument Serif'` (italic accents), `'Manrope'` (everything else)

### Add your photo and project images
Put your images in the same folder as the HTML file (or an `images/` folder) and reference them by path.

**Fresher: profile photo.** Replace the contents of `<div class="avatar-inner">`:
```html
<div class="avatar-inner">
  <img src="images/me.jpg" alt="Your Name" style="width:100%;height:100%;object-fit:cover;border-radius:50%" />
</div>
```

**Fresher: project screenshot.** Replace the `<div class="mock">…</div>` inside a project's `.thumb`:
```html
<div class="thumb t1">
  <img src="images/project1.png" alt="Project 1" style="width:100%;height:100%;object-fit:cover" />
</div>
```

**Freelancer: portrait.** Replace the text `[Your Portrait — 4:5]` (keep the sticker `<div>` after it):
```html
<div class="portrait rv">
  <img src="images/me.jpg" alt="Your Name" style="position:absolute;inset:0;width:100%;height:100%;object-fit:cover" />
  <div class="sticker">…</div>
</div>
```

**Freelancer: case-study image.** Replace the contents of `<div class="inner w1">`:
```html
<div class="inner w1">
  <img src="images/case1.jpg" alt="Project One" style="width:100%;height:100%;object-fit:cover" />
</div>
```

**Freelancer: testimonial photo.** Replace `[Client Photo]` inside `.t-avatar` with an `<img>` and add `overflow:hidden` to the `.t-avatar` div.

> Compress images before adding them ([squoosh.app](https://squoosh.app)). Aim for under 300 KB each so the site loads quickly.

### Animated numbers
Numbers count up when they scroll into view. They only animate when the value is a **plain number**:

```html
<div class="num" data-count="8.7">8.7</div>        <!-- fresher -->
<strong data-n="120">0</strong>                    <!-- freelancer -->
```
- **Fresher:** decimals are kept (`8.7` counts to `8.7`), and a `+` is added to whole numbers of 10 or more (12+, 300+).
- **Freelancer:** values are rounded to whole numbers, and a `+` is added to values above 50 (120+).
- If the value isn't a number, it simply shows as typed.

### Skill bars (fresher)
Set the percentage in **two** places, the label and `data-w`:
```html
<div class="bar-top"><span>JavaScript</span><span>85%</span></div>
<div class="bar-track"><div class="bar-fill" data-w="85"></div></div>
```

### Typing job titles (fresher)
In the `<script>` at the bottom of the file, edit this list:
```js
const words = ['Software Engineer', 'Frontend Developer', 'Data Analyst', 'Problem Solver'];
```

### Rotating hero word (freelancer)
Edit the `<span>`s inside `id="rotator"`. Keep `class="on"` on the first one:
```html
<span class="rotator" id="rotator"><span class="on">brands</span><span>websites</span><span>apps</span></span>
```
Short words look best.

### Project filters (fresher)
Each filter button's `data-f` must match a project's `data-cat`:
```html
<button class="filter" data-f="web">Web</button>
<article class="card project tilt reveal" data-cat="web">…</article>
```
Keep the `data-f="all"` button as it is.

### Pricing toggle (freelancer)
Each price has two values. `data-p` is per project and `data-m` is monthly:
```html
<span class="val" data-p="$1,500" data-m="$800">$1,500</span>
```
If a per-project price contains the word `Custom`, the "/ project" label is hidden.

### Add or remove items
Most lists are built from repeated blocks. To add one, copy a block and edit it. To remove one, delete the block.

| To add a… | Copy this block |
|---|---|
| Project (fresher) | `<article class="card project …">…</article>` |
| Timeline entry | `<div class="tl-item card">…</div>` |
| Certification | `<div class="card cert …">…</div>` |
| Service | `<div class="service rv">…</div>` |
| Case study | `<a … class="work rv">…</a>` (the staggered layout is designed for 4) |
| Testimonial | `<div class="t-slide">…</div>` (dots are created automatically) |
| FAQ | `<div class="faq-item">…</div>` |

The scrolling skills strip and client-logo strip list their items **twice** so the loop is seamless. Keep both copies identical.

### Remove a whole section
1. Delete the `<section>…</section>`.
2. Delete its link in the navigation menu.
3. **Don't delete elements the script uses** without also deleting the matching lines in the `<script>`. Otherwise the page's animations may stop working:

| Fresher IDs used by the script | Freelancer IDs used by the script |
|---|---|
| `typed`, `progress`, `spotlight`, `nav`, `menuBtn`, `contactForm`, `toast`, `yr` | `loader`, `count`, `rotator`, `cursor`, `top`, `menu`, `burger`, `scrubText`, `toggle`, `knob`, `tTrack`, `tDots`, `tPrev`, `tNext`, `clock`, `cform`, `toast`, `yr`, `backTop` |

The simplest way to hide a section safely is to add `style="display:none"` to it instead of deleting it.

---

## Make the contact form send emails

Out of the box, the forms only show a "thank you" message. They **don't send anything**. The easiest fix is [Formspree](https://formspree.io), which has a free plan:

1. Create a Formspree form and copy its endpoint, e.g. `https://formspree.io/f/abcdwxyz`.
2. Give every input a `name` so its value is sent:
   ```html
   <input type="email" id="e" name="email" placeholder=" " required />
   ```
   For the freelancer checkboxes, use `name="services" value="Web Design"` and so on.
3. Replace the form's submit line in the `<script>`.

**Fresher.** Replace the line starting `document.getElementById('contactForm').onsubmit`:
```js
document.getElementById('contactForm').onsubmit = async e => {
  e.preventDefault();
  const res = await fetch('https://formspree.io/f/YOUR_ID', {
    method: 'POST', body: new FormData(e.target), headers: { Accept: 'application/json' }
  });
  if (res.ok) { e.target.reset(); showToast('Message sent, thank you! ✓'); }
  else showToast('Something went wrong. Please email me directly.');
};
```

**Freelancer.** Replace the line starting `$('#cform').onsubmit`:
```js
$('#cform').onsubmit = async e => {
  e.preventDefault();
  const res = await fetch('https://formspree.io/f/YOUR_ID', {
    method: 'POST', body: new FormData(e.target), headers: { Accept: 'application/json' }
  });
  const t = $('#toast');
  t.textContent = res.ok ? "Thanks! I'll be in touch soon ✦" : 'Something went wrong. Please email me.';
  if (res.ok) e.target.reset();
  t.classList.add('show'); setTimeout(() => t.classList.remove('show'), 2600);
};
```
[EmailJS](https://www.emailjs.com/) and [Web3Forms](https://web3forms.com/) work in the same way.

---

## Publishing for free

Rename your file to **`index.html`** first. Hosts open that name by default.

| Option | How |
|---|---|
| **Netlify Drop** (easiest) | Go to [app.netlify.com/drop](https://app.netlify.com/drop) and drag your folder onto the page. It's live in seconds. |
| **GitHub Pages** | Create a repository, upload `index.html` (plus any images), then go to **Settings → Pages → Deploy from branch → main**. |
| **Vercel** | Import the GitHub repository at [vercel.com](https://vercel.com). Every push updates the site. |
| **Custom domain** | Buy a domain (Namecheap, Cloudflare, etc.) and connect it in your host's domain settings. |

---

## Create your own version

These files are meant to be a starting point. Some ideas:

- **Mix and match.** Copy a section from one template into the other. Bring its CSS rules from the `<style>` block too (search for the section's class names), and its script if it has one.
- **Make a new theme.** Change the `:root` colours and fonts, then adjust `border-radius` values (rounder means friendlier, sharper means more serious).
- **Add a blog or case-study page.** Duplicate the file, delete everything except the header and footer, and write your content in between. Link to it from the menu.
- **Add a dark/light switch.** Both templates keep their colours in CSS variables, so you can swap the `:root` values with a class on `<body>`.

### Rules that keep things working
- Everything (HTML, CSS, JS) lives in one file. Keep `<style>` in the `<head>` and `<script>` just before `</body>`.
- Elements with `class="reveal"` (fresher) or `class="rv"` (freelancer) fade in on scroll. Add that class to new elements to animate them, or remove it to show them straight away.
- The freelancer script is wrapped in `(() => { … })();`. Keep new code **inside** that wrapper.
- **Don't name a script variable after a browser built-in** at the top level of a script, e.g. `top`, `name`, `location`, `history`, `status`, `parent`, `self`. Chrome may refuse to run the whole script, and the page appears frozen.
- Both templates turn animations off for visitors whose device is set to "reduce motion". Keep the `@media (prefers-reduced-motion: reduce)` block.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Freelancer page stuck on the black loading screen | A script error is stopping the page. Open DevTools (`Cmd+Option+J` on Mac, `Ctrl+Shift+J` on Windows), read the red error and fix that line. |
| Changes don't show up | Hard-refresh with `Cmd+Shift+R` (Mac) or `Ctrl+Shift+R` (Windows). |
| Fonts look plain | Fonts load from Google, so you need an internet connection. |
| Image doesn't appear | Check that the path and file name match exactly, including capital letters. `Me.JPG` is not the same as `me.jpg` on most hosts. |
| A number doesn't count up | The value must be a plain number with no brackets or text (see [Animated numbers](#animated-numbers)). |
| Layout breaks on mobile | Test with DevTools' device toolbar (`Cmd+Shift+M` on Mac, `Ctrl+Shift+M` on Windows). Very long words or URLs are the usual cause. |
