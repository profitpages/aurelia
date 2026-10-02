# Aurelia: setup guide

A premium jewellery theme for Shopify Online Store 2.0. All products, prices, collections, filters, the cart and search come from your store. Nothing is hard-coded.

## 1. Install
1. Go to **Online Store › Themes › Add theme › Upload zip file** and choose `aurelia-jewellery-theme.zip`.
2. Click **Customize**. Every section, block, colour and font can be changed there.
3. *(Developers)* Run `shopify theme dev --store your-store.myshopify.com` for a live preview.

**External dependencies:** none. No JavaScript libraries are used. The fonts (Fraunces and Work Sans) load from Google Fonts. To use Shopify's
font library instead, untick *Theme settings › Typography › Use Aurelia fonts*. *Typography › Section headings* switches headings between
uppercase (as in the Canva design) and as typed.

## 2. Your photography
Until you add images, the theme shows fine gold line drawings of jewellery. Replace them with:

| Where | Image | Tip |
|---|---|---|
| Hero | Wide lifestyle photo, plus an optional mobile crop | 2800px+ wide. Keep the subject away from the text side |
| Shop by category | One per collection tile | Uses the collection image by default (portrait 5:6) |
| The everyday collection / Crafted to be remembered / Signature collection | Lifestyle photos | Full-bleed |
| Shop by moment | Four portrait photos | Defaults to each card's collection image |
| As seen on you | Six square photos | Each can link to a product or post |
| Collection banner | Defaults to the **collection image** | Landscape |
| Product gallery | Product media | Portrait 4:5. Video and 3D are supported |

## 3. Colour schemes
| Scheme | Name | Used for |
|---|---|---|
| 1 | Ivory | Page background |
| 2 | Paper | Header, trust strip, icon columns |
| 3 | Linen | Best sellers band, testimonials, reviews |
| 4 | Sand | "The everyday collection" panel, collection banner panel |
| 5 | Ink | Announcement bar, newsletter |
| 6 | Onyx | Footer |
| 7 | Espresso | "The art of layering" block |
| 8 | Champagne | Collection newsletter band |

The accent colour of each scheme is the antique gold used for eyebrows, stars and the "New" badge.

## 4. Menus (Online Store › Navigation)
- **Main menu**, for example: Shop · Collections · New arrivals · Best sellers. Nested links become dropdowns, or a mega menu when there's a third level.
- **Footer**: the footer has four menu/text columns (Shop, About, Help, Customer). Pick a menu for each column in the theme editor.
- The country/currency and language selectors appear in the footer automatically when you sell to more than one market or language.

## 5. Product page
The info column holds, in order:
- collection label
- title
- rating
- price with compare-at price and a "% off" badge
- short description
- **gift line**
- **materials line**
- size pills with a **Size Guide** link
- **complimentary engraving**
- quantity
- **Add to bag** and **Buy it now**
- shipping lines and secure-checkout note
- accordions: Shipping & Delivery, Returns, Jewellery Care, Materials & Details

Below the info column come: the trust strip, the product story, icon columns, Style it with, Reviews, You may also like, Recently viewed and the newsletter.

- **Size guide:** shown beside any option whose name contains "Size". Add the guide text in the Variant picker block, or pick a page.
- **Engraving:** saved on the order as a line-item property (`Engraving: A & J`). Remove the block if you don't offer engraving.
- **Style it with:** uses complementary products from the Search & Discovery app. The section hides until you set them.

## 6. Product metafields (optional)
**Settings › Custom data › Products › Add definition.** Rows and lines without values hide automatically.

| Name | Namespace & key | Type | Used by |
|---|---|---|---|
| Material | `custom.material` | Single line text | Materials line, Jewellery details |
| Metal type / colour | `custom.metal_type`, `custom.metal_color` | Single line text | Jewellery details (metal type also feeds the materials line) |
| Stone type / size | `custom.stone_type`, `custom.stone_size` | Single line text | Jewellery details, materials line |
| Carat | `custom.carat` | Decimal or text | Jewellery details |
| Weight | `custom.weight` | Weight | Jewellery details |
| Dimensions | `custom.dimensions` | Single line text | Jewellery details, Dimensions accordion |
| Finish / plating | `custom.finish`, `custom.plating` | Single line text | Jewellery details, materials line |
| Hypoallergenic | `custom.hypoallergenic` | True/false | Jewellery details, materials line |
| Water resistance | `custom.water_resistance` | Single line text | Jewellery details |
| Care | `custom.care` | Multi-line or rich text | Jewellery Care accordion |
| Shipping note | `custom.shipping_note` | Single line text | Shipping lines, Shipping accordion |
| Product story | `custom.product_story` | Multi-line or rich text | "Made to catch the light" story section |
| Collection label | `custom.collection_label` | Single line text | Label above the title (defaults to the first collection) |
| Gift note | `custom.gift_note` | Single line text | Gift line |
| Badge | `custom.badge` | Single line text | Card and gallery badge ("Best seller", "Gift ready"). A `badge:Best seller` tag also works; products tagged `new` show "New" |

## 7. Apps (free)
- **Shopify Search & Discovery:** collection filters (category, metal, stone, price, availability), plus complementary products for "Style it with".
- **A reviews app** (Judge.me, Okendo, Shopify Product Reviews…): stars on cards and the review score come from the standard `reviews.rating`
  metafields. Add the app's block inside the **Reviews** section, and set the "Write a review" link. The theme never shows invented reviews.
- **Wishlist apps:** the built-in wishlist saves to the shopper's browser. Turn it off in *Theme settings › Wishlist* if you install an app.

## 8. Collection page
- **Collection banner:** the collection image beside a sand panel with the title, description, a support line and "Shop the collection".
- **Statement strip:** one serif line and a link.
- **Product grid:** "34 pieces" count, a Filter & sort drawer, sort menu, and grid density buttons (3 / 4 / 5 per row, remembered per browser).
  Below the grid: active-filter chips, then Load more with "Showing 12 of 34 pieces".
- Then **The art of layering**, **Crafted for your every day**, **Complete the look** and a champagne newsletter band.

## 9. Sections
**Home (Canva order):**
1. Hero
2. Trust strip
3. Shop by category
4. Best sellers
5. The everyday collection
6. New arrivals
7. Crafted to be remembered
8. Shop by moment
9. The signature collection
10. Loved by thousands
11. As seen on you
12. Newsletter

**Also included:**
- **Merchandising:** Slideshow, Featured product, Collection tabs, Promotional cards, Countdown, Scrolling text, Logos.
- **Discovery:** Shop the look (hotspots), Complete the set (bundle), Gift finder quiz, Shop by occasion, Material tabs, Comparison table.
- **Storytelling:** Multirow, Multicolumn, Rich text, Timeline, Founder's note, Editorial collage, Styling appointment, Steps, FAQ, Benefits.
- **Media:** Video, Video reviews, Shoppable gallery, Blog posts, Custom Liquid.

## 10. Known limitations
- Review cards and rating breakdown bars come from your reviews app's block, because Shopify doesn't expose them to themes.
- The wishlist and recently viewed lists live on the shopper's device.
- `templates/index.sections-demo*.json` are QA pages (`?view=sections-demo`, `-2`, `-3`) and are excluded from the release zip.

## 11. QA checklist (verified on a development store)
- [x] Online Store 2.0: JSON templates, header/footer section groups, schemas with settings, blocks and presets, app blocks (product info, reviews)
- [x] Dynamic products, collections, menus, prices, compare-at prices, sale/sold-out/new badges
- [x] Product page: gallery with thumbnails and zoom, variant pills (unavailable struck through), engraving property, quantity, Add to bag, Buy it now
- [x] Cart drawer: free-shipping bar, line properties, quantity, remove, promo code, checkout. Cart page
- [x] Collection: filter drawer (submits Search & Discovery filters), chips, sorting, density toggle, Load more with progress
- [x] Search page and predictive search
- [x] Footer country/currency and language selectors (Shopify localization form) and payment icons
- [x] Responsive at 1534 / 390 / 375 / 320: no horizontal overflow, tap targets 24px or larger, text 9.5px or larger
- [x] Accessibility: landmarks, one h1 per page, labelled controls, keyboard dialogs (size guide, zoom, drawers), focus rings, reduced motion
- [x] SEO: titles and meta, canonical URLs, Open Graph, Product / Breadcrumb / Organization structured data
- [x] Performance: no frameworks, deferred vanilla JS, per-section CSS, responsive `image_url` srcsets, lazy loading below the fold
- [x] Shopify Theme Check: 0 offenses
