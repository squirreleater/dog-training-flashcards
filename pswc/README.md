# PSWC — design preview

**Peets Sport & Working Canines.** A private, non-live design preview built from
Scott's logo, mockup and brief.

## Status

- **Not live.** Nothing is announced, linked or submitted anywhere.
- **Not indexed.** Every page carries `noindex, nofollow, noarchive, nosnippet,
  noimageindex` for general crawlers plus named rules for Google, Bing, Yahoo,
  DuckDuckGo, Baidu, Yandex, GPTBot, CCBot and ClaudeBot. There are deliberately
  no Open Graph or Twitter card tags, so pasting the link into a chat or an email
  produces no preview card.
- A thin **"private design preview"** strip sits at the top of every page so it
  can't be mistaken for a live site. Delete that one `<div>` to remove it.

The URL is unguessable-ish but technically public — treat it as "unlisted",
not "secret".

## Viewing it locally

No build step, no server. Download the folder and double-click `index.html`.
All paths are relative, so it works straight from `file://`.

## Editing it

Plain HTML + one stylesheet. Nothing to compile.

| What | Where |
|---|---|
| Colours, type, spacing | `assets/css/site.css` (all tokens are at the top under `:root`) |
| Page copy | the `.html` file for that page |
| Nav and footer | repeated in each `.html` file — change all of them together |
| Logo | `assets/img/pswc-logo.*`, `pswc-mark.png`, `favicon.png` |

Palette is sampled from the seal: black `#000`, stone `#c9c3bb`, oxblood `#8f151d`.
Oxblood is used sparingly on purpose — buttons, hovers, hairlines only.

## Photography

The six dog photographs are **cropped out of `Web mock up.png`** and placed where
the mockup had them:

| File | Used on |
|---|---|
| `hero-dog` / `hero-dog-mobile` | home hero (full-bleed background) |
| `card-sport` | home card, Training › Sport |
| `card-working` | home card, Training › Working, Working Dogs › Detection |
| `card-companion` | home card, Training › Companion |
| `vesi-portrait` | home Vesi block, The Dogs |
| `about-scott` | home About block, About page, Working Dogs › Handler |

Each is exported as WebP with a JPEG fallback, via `<picture>`.

### The hero is a composite

The mockup's hero band has the logo and headline baked into it, so the only
text-free strip is the 351×502 piece containing the dog — nowhere near enough to
fill a full-width hero. `hero-dog.jpg` is therefore built by `make_hero.py`:
the sharp dog sits right of centre over a heavily blurred, darkened blow-up of
the same frame, feathered so there is no seam. The blur reads as depth of field.
`hero-dog-mobile.jpg` is a taller, tighter crop used below 1040px.

Replace the whole thing with one real wide photograph when you have it — that is
a single line in the CSS (`.hero.has-photo`), no compositing needed.

**Everything here is low resolution.** The mockup is 1024×1536, so the card crops
range from 312×168 to 462×242 and are displayed at or above native size. They
look soft on a high-DPI screen. Fine for judging the design; not fine for launch.
Replace with the original full-resolution files, or with real photographs of
Scott's own dogs, at roughly 2× the displayed size.

The PSWC seal is the exception — it is served at its native 1226px and is sharp.

Slots with no matching source image still show a labelled placeholder plate:

- Vesi's progress log — three dated shots (week 9, month 4, month 6)
- Working Dogs — environmental work at height / on grating, dog on an unstable surface

## Credential logos

The Highland Canine Training and IACP marks are on the About page, sitting on a
light plate so they appear in their own colours, unmodified. Both were taken
from iacpdogs.org.

They belong to their respective organisations. Before this goes live, check each
body's logo usage terms — IACP in particular sets out how members may display
the mark, and neither affiliation is active until December.

## Still to confirm

Everything marked with a dashed underline in the page is a placeholder:
email, phone, location, travel radius, social handles, programme formats and
pricing, and the stage date ranges on Vesi's record.

The contact form is **not connected** — it pops an alert. It needs a form
handler and a privacy notice before launch.

## Credentials

The About page states the Highland Canine Master Trainer Program (6 Jul –
18 Dec 2026, under Jason Purgason) as **in progress**, and IACP membership as
**on graduation**. Both are written as pending rather than held — worth keeping
that way until December.

Official Highland Canine and IACP marks are **not** included. Both have usage
terms for members; the logo slots are sized and ready once membership is active
and usage has been checked.

## Before this goes live

- [ ] Remove the preview strip from all 11 pages
- [ ] Remove the `noindex` meta block from all 11 pages
- [ ] Full-resolution photography in place of the low-res mockup crops
- [ ] Real contact details and social links
- [ ] Confirm Highland / IACP logo usage terms
- [ ] Connect the contact form + add a privacy notice
- [ ] Add Open Graph / Twitter card tags and a real share image
- [ ] Point `pswk9.com` at it, add a root `robots.txt` and a sitemap
