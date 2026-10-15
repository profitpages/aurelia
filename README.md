# Aurelia: Shopify OS 2.0 theme for premium jewellery

Built from the Canva design "Premium Aurelia jewellery ecommerce homepage". The design has three pages: home, product and collection.
The look is ivory paper with antique gold, set in uppercase Fraunces headings and Work Sans text. Corners are square and lines are hairline-thin, around editorial full-bleed photography.

- **Merchant setup, metafields, limitations and the QA checklist:** [GETTING-STARTED.md](GETTING-STARTED.md)
- **Canva source (codelets):** `_design-source/` (home, product, collection)

## Structure
```
assets/      theme.css (tokens, type, buttons, cards, header, footer, cart) · theme.js (vanilla, no dependencies) ·
             component-product.css · section-hero.css · section-aurelia.css (trust, tiles, image with text, editorial
             cards, social, statement, icon columns, testimonials, newsletter, reviews) · section-collection.css ·
             section-aurelia-extras.css (spotlight, gift & metal guides, engraving preview, bespoke, promise,
             boutiques, size guide) · section-content.css · section-features.css · section-extras.css · section-promo.css · section-routine.css
config/      settings_schema.json (8 color schemes, typography, layout, cards, cart, wishlist, social) · settings_data.json
layout/      theme.liquid · password.liquid
locales/     en.default.json
sections/    header-group.json · footer-group.json · Aurelia sections (hero, trust-bar, collection-grid, image-with-text,
             editorial-cards, social-gallery, statement-strip, icon-columns, …) + main-* templates and optional sections
snippets/    product-card (boxed / bordered / plain) · collection-tile · jewellery-details · price · badge · rating ·
             icon · product-form · variant-picker (size guide) · cart-item · cosmetic-art (jewellery line-art placeholders) · …
templates/   JSON templates + customers/* + gift_card.liquid
```

## Develop
```bash
shopify theme dev --store <store>.myshopify.com
shopify theme check
```
Push only the files you changed, so edits made in the theme editor aren't overwritten:
```bash
shopify theme push --store <store>.myshopify.com --theme <id> --only sections/hero.liquid
```
When a section gains new settings, push the section before (or separately from) the templates that use them.

## Release zip
Zip `assets config layout locales sections snippets templates` with forward-slash paths. Leave out
the `templates/index.sections-demo*.json` QA pages.

## Keeping in step with the store builder

The store builder's copy (`store-builder/themes/aurelia/src`) is the live version. It has these, applied there:
- the hardening passes
- the theme editor in nine languages (`t:` keys, `locales/*.schema.json`)
- the add-ons kits in `scripts/theme-addons`, including the product-information blocks: Emoji benefits, Urgency text, Clickable discount, Shipping checkpoints and Quantity selector

This repo was synced from that copy on 2026-10-15.

After changing files here:
1. Commit, then import the theme: `node scripts/import-theme.mjs aurelia ../aurelia-jewellery-theme`
2. Key and translate any new editor labels:
   - `node scripts/theme-schema-i18n.mjs aurelia`
   - `railway run node scripts/i18n-translate.mjs schema`
3. Copy `themes/aurelia/src` back here, so the two stay identical.

Never import an older checkout of this repo: it would undo the fixes made in the app.
