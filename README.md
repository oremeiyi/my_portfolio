# Amina Kabir — Personal Portfolio

A responsive personal portfolio built with plain HTML and CSS. It uses Amina's supplied graduation portrait and intentionally marks unprovided details, project examples, and social links as placeholders.

## Open the website

1. Open the `My portfolio` folder in Visual Studio Code.
2. Open `index.html`.
3. If you have the **Live Server** extension, right-click `index.html` and select **Open with Live Server**. Otherwise, open `index.html` directly in a modern browser.
4. Keep the `css` and `images` folders next to `index.html`; the page uses their relative paths.

There is no build step, framework, or package to install. The Google Fonts link uses the internet when available; the page falls back to system fonts if it is offline.

## Files and folders

- **`index.html`** contains all page content and its semantic structure: navigation, hero, biography, skills, sample project cards, education, contact details, form, and footer.
- **`css/style.css`** contains all colors, type, spacing, layouts, hover states, small entrance animations, and responsive rules.
- **`images/profile.png`** is a local copy of the graduation photo supplied for this portfolio. The HTML image path is `images/profile.png`.
- **`assets/`** is reserved for optional extras you may add later, such as a favicon.

## Understanding the HTML

The document begins with `<!DOCTYPE html>`, which tells the browser to use modern HTML. `<html lang="en">` identifies the page language. The `<head>` contains page metadata, its title, font links, and the stylesheet reference. The viewport setting helps the layout fit phone screens.

The `<body>` contains what visitors see. `<header>` holds the sticky brand and navigation, `<main>` wraps the main page content, and `<footer>` contains the closing statement and links. Each `<section>` has a unique `id` and heading; navigation links such as `href="#about"` jump to the section whose `id` is `about`. `<article>` groups one self-contained card. These semantic elements make the page easier to understand for people, browsers, and assistive technology.

The first link, “Skip to content,” is a keyboard accessibility shortcut. The mobile menu uses the built-in HTML `<details>` and `<summary>` elements, so opening and closing it does not require JavaScript. The portrait's `alt` text describes the image for visitors who cannot see it. Decorative flourishes use `aria-hidden="true"` so screen readers can skip them.

The skills are presented as learning interests, not ratings. Project cards are explicitly labelled placeholders and their “View project” and “GitHub” labels are not fake links. Contact addresses and social profiles are editable text placeholders rather than invented personal details.

The contact form is deliberately disabled: static HTML and CSS alone cannot deliver a message, so the form does not claim to work or pretend to send anything. Once you choose a form service or build a backend, connect it before enabling the fields and send button.

## Understanding the CSS

At the top of `css/style.css`, `:root` defines reusable custom properties (variables): `--green`, `--gold`, `--paper`, font choices, page width, and spacing. Changing a variable there updates every place that uses it. The universal `box-sizing` rule makes element sizing more predictable. The global `body` rule sets the default background, text color, font, and line spacing.

The stylesheet is organised with section comments that mirror the page:

- **Header:** flexbox aligns the logo, desktop links, and call to action. On narrow screens the desktop navigation is replaced with the native disclosure menu.
- **Hero:** CSS Grid places the introduction and photo side by side. `clamp()` lets type and spacing scale between minimum and maximum sizes. `object-fit: cover` fills the portrait frame; `object-position: center 23%` shifts the crop upward to keep the graduation cap and face visible.
- **About, skills, projects, and education:** grid and flex layouts organise the copy and cards. Hover transitions add a small lift without changing the content.
- **Contact and footer:** clear color contrast, labelled form controls, and responsive layouts make the last sections readable on different screen sizes.
- **Motion and media queries:** `@keyframes` creates the gentle hero entrance. `prefers-reduced-motion` respects visitors who request less animation. The `@media` rules adjust the layout for tablets (900px), phones (700px), and small phones (480px).

## Personalise it

1. Replace the sample project titles, descriptions, technology tags, and CSS artwork when you have real projects to share. Add the real project and repository URLs only when they exist.
2. Replace the contact placeholders with your real email and professional profile links. Use actual profile URLs rather than a generic social home page.
3. Update the skills list to match what you are currently learning. The status text does not claim a particular skill level.
4. To change the portrait crop, edit `.portrait`'s `object-position` in `css/style.css`. To use another image, save it in `images/` and change the `src` on the portrait `<img>` in `index.html`.
5. To receive messages, choose a form service or backend, configure the form's submission endpoint and validation, test a real submission, and only then enable the form controls and button.
