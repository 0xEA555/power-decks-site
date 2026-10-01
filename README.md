# Power Decks landing page (mockup v1)

Single static page. No build step, no framework. Open `index.html` in a browser to preview.

```
index.html      all HTML, CSS and a small inline script
assets/         six PNGs: two real box fronts, four real card faces (rendered from the Vervante print PDFs)
```

## What to ask Claude Code to do

1. **Serve it.** Static host. The project already uses Netlify (powerdecks.netlify.app): drop this folder in as the publish directory, no build command. Point usepowerdecks.com at it when ready.
2. **Wire the email form.** There are two forms (`#join-hero`, `#join-final`) and one `wire()` function at the bottom of `index.html`. Today it validates the address and prints "Mockup only…". Replace the handler body with a real POST to the email provider (Mailchimp, ConvertKit, Klaviyo, or a Netlify Function). On success show "You're on the list. One email on Nov 27." Keep the field to email only. Remove the "Mockup only" message.
3. **Keep the fonts.** Libre Franklin (500/700/800/900) and Libre Caslon Text (400, 400 italic, 700) load from Google Fonts in `<head>`. They are the only two faces in the Power Decks system. For speed, self-hosting them is fine; do not swap them.
4. **Do not change the proportions of the boxes or cards.** Box fronts are 2.875 x 4.875 in (aspect 2875:4875). Cards are 2.75 x 4.75 in. Box and card images are real print renders. The Nº 03 box is a CSS concept render (`.cbox`) built to the same proportions. When the real Game of Life box is built, export its front face the same way (front panel only, no closure) to `assets/front-gol.png` and replace the two `.cbox` blocks with `<img>` tags like the other two decks.
5. **Add** analytics, a favicon (the concentric-diamond mark in colour b works), and a social share image (`og:image`, 1200x630: the three boxes on the night ground).

## Design rules (from the design spec, do not break)

- Colours are tokens in `:root`. Night `#1b1718`, cream `#f7f1e1`, deck colours amber `#d67c20` (Nº 01), green `#6fb950` (Nº 02), teal `#2fa79a` (Nº 03 placeholder).
- Radius is 0. No shadows. One rule weight. No gradients. No emoji. No stock photos.
- Headings are Libre Franklin 900 uppercase. Quotes are Libre Caslon Text.
- One call to action, repeated: "Get the launch note".
- Card words are quoted verbatim from the source texts. Do not edit any quote on the page.
- The tagline is LEARN THE PRINCIPLE. / USE THE TOOL. / DAILY. with DAILY. in the deck colour.

## Content to confirm before it goes live

- Launch lineup. The Sept 11 Black Friday plan launches Nº 01 and Nº 02 only and holds Game of Life. The page shows all three launching Nov 27. Decide, then cut or relabel Nº 03.
- Nº 03 palette (plum, teal, gold) is a placeholder.
- Price and where to buy: not on the page by design. Add when decided.
- "Not affiliated with or endorsed by the Napoleon Hill Foundation" line in the FAQ and footer: have the IP attorney review before launch.
- No testimonials, ratings or sales numbers appear because none exist yet. Do not add invented ones.
- Run the copy through the AI-pattern check once more before launch.
