# Strategic Pause Advisory website: project notes for Claude Code

This folder builds the marketing website for Strategic Pause Advisory Ltd (www.strategicpauseadvisory.com). It replaces an existing Wix site. The site is static HTML and CSS, hosted free on GitHub Pages.

## Source material

- `content/spa-website.md` is the master copy for every page. Use its wording; don't invent claims, figures or testimonials. `[TODO: …]` items are open decisions, so ask about them rather than guessing.
- `images/` holds web-ready images that are already resized and named. Reference them from here.
- `fonts/` holds the licensed FF Good Headline Pro web fonts and `fonts/fonts.css`.
- `files/` holds the article PDFs linked from the Watch & Listen section of My Story.
- `brand/` holds originals and the brand guidelines PDF. It is private (git-ignored). Read it for reference, but never link to it from the site.
- `marketing/` is private (git-ignored).

## Pages and URLs (must match the old Wix addresses)

| Page | URL | File |
|---|---|---|
| Home | `/` | `index.html` |
| About (includes the "Why pause?" section, `#why-pause`) | `/about` | `about/index.html` |
| Services | `/spaservices` | `spaservices/index.html` |
| My Story (includes the "Watch & Listen" section, `#watch-listen`) | `/mystory` | `mystory/index.html` |
| Contact | `/contact` | `contact/index.html` |
| Privacy Policy | `/privacypolicy` | `privacypolicy/index.html` |
| Legal Notice | `/legalnotice` | `legalnotice/index.html` |

The header navigation has five pages: Home, About, Services, My Story, Contact. The old addresses `/watchlisten` and `/whypause` are small redirect pages (`watchlisten/index.html`, `whypause/index.html`) that forward to `/mystory#watch-listen` and `/about#why-pause`. They are not in the navigation or `sitemap.xml`. The process diagram images (`process-full.webp`, `process-pause-think-plan-thrive.webp`) are not used anywhere on the site.

Use one shared stylesheet (`css/styles.css`). Every page has the same header, navigation and footer. Use page-relative links (`about/` from the home page, `../about/` from other pages) so the site works both at `username.github.io/spa-website/` and on www.strategicpauseadvisory.com. `404.html` sets a `<base>` with a small script because it can be served at any address. Canonical URLs, Open Graph URLs and `sitemap.xml` use the full www address. Add the `CNAME` file only when the domain is connected.

## Brand rules (from brand/SPA Brand Guidelines)

- **Colours.** The main colours are Steel Grey `#CDCFD0`, True Black `#000000` and Pure Gold `#AF7C31`. The accents are Butter Yellow `#ECC962` and Deep Gold `#9E7B3A`. Powder White is `#FFFFFF`. Gold is for emphasis and buttons, not large blocks of text. Check text contrast: gold text on white is weak, so use black text with gold accents.
- **Headings** use FF Good Headline Pro Medium (`FFGoodHeadlineProMedium`), with Bold (`FFGoodHeadlineProBold`) for emphasis. Load them via `/fonts/fonts.css`.
- **Body text** uses Avenir (licensed for web; Book weight for body text, Heavy for emphasis). [TODO: Avenir web font files or embed code still to be added. Until then use the stack `"Avenir Next", Avenir, "Segoe UI", sans-serif`.]
- **Logos**
  - `logo-white.png` or `logo-white-gold.png` on dark or gold backgrounds
  - `logo-black.png` or `logo-black-gold.png` on light backgrounds
  - Never stretch the logo, recolour it or crowd it. Keep clear space of about half a letter height around it.
- **Brandmark.** The triangle (`brandmark-gold.png`) is used on its own only for the favicon and small decorative touches.
- **Hero.** The gold triangle texture (`hero-gold.webp`) is the hero background, with a dark overlay so the white logo and text read clearly.
- **Tone and spelling.** The tone is calm, reassuring and personal, written in the first person as Philip. Use British English.

## Functionality

- **No cookies and no cookie banner, ever.** Nothing that sets cookies may load when a page opens: no analytics, no tracking, and no third-party embeds that load automatically.
- **Booking.** The "Book a call" button links to `https://calendly.com/philip-feibusch-spa-ukltd/30min` and opens in a new tab. It is a plain link, not the Calendly embed. It appears in the header and in the footer on every page.
- **No contact form.** There is no contact form and no Formspree.
- **Videos.** Show each video as a YouTube thumbnail with a play button. Only when it is clicked, swap in the `youtube-nocookie.com` player. Self-host the thumbnails in `images/` rather than loading them from YouTube.
- **Podcast.** The podcast is a plain text link to Spotify, with no embed and no image.

## Quality bar

- Responsive and good on phone and desktop, with a mobile menu.
- Accessible: alt text on every image, a visible focus state, sensible heading order and good contrast.
- Every page has a unique `<title>` and meta description, and Open Graph tags using `images/og-share.jpg`.
- Include the favicons `favicon.ico`, `favicon-32.png` and `apple-touch-icon.png`.
- Add `sitemap.xml`, `robots.txt` and a `404.html` page that matches the site.
- Use no build tools or frameworks: plain HTML, CSS and minimal JavaScript (only for the mobile menu and video thumbnails).
