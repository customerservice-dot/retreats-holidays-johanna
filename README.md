# MINYALA stock sale — Pierre d'Égypte

Materials for selling the MINYALA limestone stock on [pierredegypte.online](https://www.pierredegypte.online).
All prices and terms match the live store (Oct 2026): €35/m² stone only, 25 m² minimum, 30% deposit option, pickup in Gennevilliers, delivery and installation quoted from 100 m².

## What's in `minyala/`

| File | What it is | How to use it |
|---|---|---|
| `index.html` | Standalone landing page in French, with an m² calculator (price, deposit, slab count, estimated weight). Its buttons go straight to Shopify checkout for the chosen surface. | Host it anywhere static (GitHub Pages, Netlify), then link it from ads, Instagram bio and WhatsApp. |
| `shopify-description-produit.html` | Replacement description for the MINYALA product page. It leads with **EN STOCK** and adds a full-payment button alongside the deposit one. | Shopify admin → Products → MINYALA → Description → `<>` (HTML view) → paste. |
| `kit-de-vente.md` | Ready-to-paste French copy: WhatsApp broadcast, Instagram/Facebook post and story, Leboncoin Pro listing, email to trade buyers, Google Ads headlines and descriptions (length-checked). | Copy and paste. |
| `prospects-minyala.xlsx` | Prospect tracker: 197 verified trade buyers in Île-de-France and Normandy (resellers, showrooms, marble workshops, pool and spa builders, landscapers, fitters, house builders, specifiers, hotels with announced works), where to reach private buyers (listings, forums, fairs, ads), B2B channels, and the French rules for contacting people. | Work through the yellow cells; the first tab counts contacts and m² sold. |

### Checkout links used

| Link | Result |
|---|---|
| `https://www.pierredegypte.online/cart/53078996779274:25` | Full payment, 25 m² = €875 (variant "Pierre seule — retrait Gennevilliers") |
| `https://www.pierredegypte.online/cart/53073670603018:25` | 30% deposit, 25 m² = €262.50 (product "Acompte réservation MINYALA") |

Change the number after `:` to change the m². Both links were tested and redirect to checkout.

## Fixes to make in the Shopify store

1. **Homepage badge says "Sur commande" (made to order)**, while the MINYALA deposit page says "MINYALA est en stock". Buyers who want stone now will skip it. Change the homepage card to **"En stock"**.
2. **The product page only links to the deposit.** The new description adds a "Commander 25 m² — 875 €" link.
3. **Real photos.** The current product image is an AI render (file name `ChatGPT_Image_…`). Photos of the actual pallets, a close-up of a slab, and a laid sample build trust and prevent "not as pictured" disputes. Once you have them, replace the image URL in `index.html`.
4. **Track inventory in Shopify.** Enter the real m² in stock so the store can't oversell, and so you can honestly say "plus que X m²".
5. *(Not MINYALA, but hurts trust)* The homepage says "Acompte 30% seulement" while SINAI SAND asks for a 75% deposit.

## Assumptions to check

- **Weight ≈ 50 kg/m²** in the calculator and the Leboncoin text is an estimate for 2 cm limestone. Adjust `KG_PER_M2` in `index.html` and the text if you have the real figure.
- **No discount was added.** Discount options (volume pricing, a promo code in the checkout link, a deadline) are listed at the end of `kit-de-vente.md` for you to decide on.
- The landing page uses the store's existing product image and the WhatsApp number from the site (+33 7 58 50 41 73).
