# Amina Kabir — Personal Portfolio

A responsive personal portfolio built with plain HTML and CSS. It introduces Amina's background and current learning interests, and features the supplied Lusak Academy and portfolio screenshots as project previews.

## Open the website

1. Open the `My portfolio` folder in Visual Studio Code.
2. Open `index.html`.
3. If you have the **Live Server** extension, right-click `index.html` and select **Open with Live Server**. Otherwise, open `index.html` directly in a modern browser.
4. Keep the `css` and `images` folders next to `index.html`; the page uses their relative paths.

There is no build step, framework, or package to install. The Google Fonts link uses the internet when available; the page falls back to system fonts if it is offline.

## Files and folders

- **`index.html`** contains the semantic page structure: navigation, introduction, biography, learning interests, projects, education, contact links, and footer.
- **`css/style.css`** contains the visual styles, responsive layouts, hover states, and motion.
- **`images/profile.png`** is a local copy of the graduation photo supplied for this portfolio. The HTML image path is `images/profile.png`.
- **`images/lusak-academy.png`** and **`images/portfolio-preview.png`** are the supplied project screenshots used in the work section.
- **`assets/`** is reserved for optional extras you may add later, such as a favicon.

## Understanding the HTML

The document begins with `<!DOCTYPE html>`, which tells the browser to use modern HTML. `<html lang="en">` identifies the page language. The `<head>` contains page metadata, its title, font links, and the stylesheet reference. The viewport setting helps the layout fit phone screens.

The `<body>` contains what visitors see. `<header>` holds the sticky brand and navigation, `<main>` wraps the main page content, and `<footer>` contains the closing statement and links. Each `<section>` has a unique `id` and heading; navigation links such as `href="#about"` jump to the section whose `id` is `about`. `<article>` groups one self-contained card. These semantic elements make the page easier to understand for people, browsers, and assistive technology.

The first link, “Skip to content,” is a keyboard accessibility shortcut. The mobile menu uses the built-in HTML `<details>` and `<summary>` elements, so opening and closing it does not require JavaScript. The portrait's `alt` text describes the image for visitors who cannot see it. Decorative flourishes use `aria-hidden="true"` so screen readers can skip them.

The skills section describes current learning interests rather than ratings. The projects use the supplied screenshots; only the portfolio card links to a source repository. Contact links use email and profile URLs already present in the site.

## Understanding the CSS

At the top of `css/style.css`, `:root` defines reusable custom properties (variables): `--green`, `--gold`, `--paper`, font choices, page width, and spacing. Changing a variable there updates every place that uses it. The universal `box-sizing` rule makes element sizing more predictable. The global `body` rule sets the default background, text color, font, and line spacing.

The stylesheet is organised with section comments that mirror the page:

- **Header:** flexbox aligns the logo, desktop links, and call to action. On narrow screens the desktop navigation is replaced with the native disclosure menu.
- **Hero:** CSS Grid places the introduction and photo side by side. `clamp()` lets type and spacing scale between minimum and maximum sizes. `object-fit: cover` fills the portrait frame while keeping the graduation portrait in view.
- **About, skills, projects, and education:** grid and flex layouts organise the copy and cards. Project previews use the supplied screenshots.
- **Contact and footer:** the contact area offers direct email and profile links, with responsive layouts for smaller screens.
- **Motion and media queries:** a small `IntersectionObserver` reveals cards as they enter the viewport. The `prefers-reduced-motion` setting is respected, and the page remains visible if JavaScript or the observer is unavailable. The `@media` rules adjust the layout for tablets (900px), phones (700px), and small phones (480px).

## Personalise it

1. Update project descriptions and add demo or repository links when those URLs are available.
2. Keep the skills list aligned with what you're actually learning; the section is intentionally not a proficiency ranking.
3. To change the portrait crop, edit `.portrait`'s `object-position` in `css/style.css`. To use another image, save it in `images/` and change the `src` on the portrait `<img>` in `index.html`.
4. Update the email and profile URLs in `index.html` if your preferred contact details change.
