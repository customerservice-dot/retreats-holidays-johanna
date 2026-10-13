# MINYALA stock sale — Pierre d'Égypte

Materials for selling the MINYALA limestone stock on [pierredegypte.online](https://www.pierredegypte.online).
All public prices match the live store (Oct 2026): €35/m² stone only, 25 m² minimum, 30% deposit option, delivery and installation quoted from 100 m². Pickup by appointment in Gennevilliers (92) or Vernon (27) — Vernon is not yet shown on the store (see fixes). Trade / clearance price for professionals: €27/m² incl. VAT (€22.50 excl. VAT), quoted by message and invoice, not through the website checkout. Stock: 500–2,000 m².

## What's in `minyala/`

| File | What it is | How to use it |
|---|---|---|
| `index.html` | Standalone landing page in French, with an m² calculator (price, deposit, slab count, estimated weight). Its buttons go straight to Shopify checkout for the chosen surface. | Host it anywhere static (GitHub Pages, Netlify), then link it from ads, Instagram bio and WhatsApp. |
| `shopify-description-produit.html` | Replacement description for the MINYALA product page. It leads with **EN STOCK** and adds a full-payment button alongside the deposit one. | Shopify admin → Products → MINYALA → Description → `<>` (HTML view) → paste. |
| `kit-de-vente.md` | Ready-to-paste French copy: WhatsApp status (broadcast only to contacts who agreed), Instagram/Facebook post and story, pointer to the Leboncoin guide, email to trade buyers, Google Ads headlines and descriptions (length-checked). | Copy and paste. |
| `clients-potentiels.xlsx` / `.csv` | Snapshot of every potential client as of 13/10/2026: 249 rows (197 French trade buyers, 52 export buyer requests) in one sheet, plus the channels, Facebook groups, a summary with each sales channel's verdict, and an empty log for private buyers' requests (no personal details). It contains no trade price, so it can be shared or uploaded to ChatGPT; the CSV is the same list. | Day-to-day tracking stays in `prospects-minyala.xlsx`. |
| `prospects-minyala.xlsx` | Prospect tracker: 197 verified trade buyers in Île-de-France and Normandy (resellers, showrooms, marble workshops, pool and spa builders, landscapers, fitters, house builders, specifiers, hotels with announced works), where to reach private buyers (listings, forums, fairs, ads), 22 Facebook groups to approach with admin consent, 52 trade buyer requests (RFQs), B2B channels, and the French rules for contacting people. | Work through the yellow cells; the first tab counts contacts and m² sold. |
| `facebook-instagram.md` | Facebook & Instagram plan in French: site fixes to make before advertising, creating the Page / Instagram / business portfolio, connecting Shopify's official Meta app and cookie banner, three ad campaigns with length-checked copy, a GDPR-compliant lead form, Facebook group approach and a 4-week posting calendar. Every technical point is sourced. | Follow the steps in order. |
| `rfq-kit.md` | English / French kit for trade requests on StoneContact, StoneAdd and other B2B marketplaces: product sheet, reply templates, seller listing, what replying costs, requests to answer first, fraud checklist. Trade price €22.50 excl. VAT. | Fill the [bracketed] decisions first, then paste. |
| `leboncoin.md` | Leboncoin guide in French: Pro account steps, the one listing to publish first (Gennevilliers, 875 € lot of 25 m²), photos to take, costs (50 free postings in total, 12 % commission on online payment), why not to switch on Leboncoin's online payment yet, message templates and a 10-point check for listings written elsewhere. | Read section 2 first. Replaces the listing in `kit-de-vente.md` section 3. |
| `amazon.md` | Amazon decision note in French: not now (25 m² pallet lots don't fit, fees also apply to freight, one claim can hurt the account), margin table, and the CE marking / declaration of performance checklist to send to the supplier, which applies to every channel. | Send the supplier checklist (section 3) this week. |
| `allovoisins.md` | AlloVoisins guide in French: verdict (don't buy Premier or Booster; at most the one-time 14-day trial on one Gennevilliers area), real costs and 12-month lock-in, settings, profile text, reply templates, rules. | Read section 2 first. |
| `fret-zim.md` | What to enter in ZIM's sea-freight quote form for a 20' container of tiles from Damietta (Egypt) to Le Havre / Gennevilliers, plus the customs side: HS code, 0 % duty with EUR.1, EORI, import VAT, documents to get from the supplier. | Fill the form yourself on zim.com (it blocks automated access). |
| `visuels/` | Three ad images at Meta's recommended sizes: 4:5 feed (1440×1800), 1:1 price card (1440×1440), 9:16 Story/Reel (1440×2560, safe zones respected). They use the store's current image, labelled "Visuel indicatif". | Upload in Ads Manager; replace with real photos when available. Each image also exists as `.jpg` (Instagram posting accepts JPEG only). |

### Checkout links used

| Link | Result |
|---|---|
| `https://www.pierredegypte.online/cart/53078996779274:25` | Full payment, 25 m² = €875 (variant currently named "Pierre seule — retrait Gennevilliers": rename it, see fix 0) |
| `https://www.pierredegypte.online/cart/53073670603018:25` | 30% deposit, 25 m² = €262.50 (product "Acompte réservation MINYALA") |

Change the number after `:` to change the m². Both links were tested and redirect to checkout.

## Check before selling (all channels)

- **Business registration.** The public register lists SIREN 985 289 065 as a sole trader (entrepreneur individuel) whose main activity is 85.51Z (sports and leisure teaching), head office in Paris, with no craft trade registered ([register](https://recherche-entreprises.api.gouv.fr/search?q=985289065), checked 13/10/2026). Add the stone-trading activity (achat-revente) to the register before selling. "Pierre et retraites" is a trade name, not a separate company: the legal notice and invoices must name the business owner.
- **VAT.** Every price in these files assumes VAT is charged (35 € TTC; trade price 22,50 € HT / 27 € TTC). If the business is under the VAT exemption (franchise en base), prices must instead carry "TVA non applicable, art. 293 B du CGI", and the HT/TTC wording must change everywhere. Confirm with the accountant.
- **Installation ("pose").** The store and these files offer "livraison et pose sur devis dès 100 m²". Laying tiles as a business requires a tiling qualification (CAP/BP or 3 years' certified experience; 7,500 € fine otherwise) and, for terraces and pool surrounds, décennale insurance named on quotes and invoices ([F39050](https://entreprendre.service-public.gouv.fr/vosdroits/F39050), [F2034](https://www.service-public.gouv.fr/particuliers/vosdroits/F2034)). If the business doesn't have both, change the offer to "pierre seule — pose par votre carreleur" or have an insured installer quote and invoice the customer directly.
- **Online withdrawal button.** Since 19 June 2026, online sellers to consumers must offer a free online withdrawal function ([F33527](https://entreprendre.service-public.gouv.fr/vosdroits/F33527)). Add it with the French terms of sale (fix 0).
- **CE marking and declaration of performance (DoP).** Natural stone floor tiles are a construction product under Regulation (EU) 305/2011, which still applies to floorings in October 2026: they need the manufacturer's DoP (EN 12058:2004; EN 1341 for outdoor paving) and CE marking, and the importer or distributor must check them before selling. Online listings to consumers must also name the manufacturer and the EU responsible person (GPSR art. 19). Checklist to send to the supplier: `amazon.md`, section 3.
- **Construction-materials recycling scheme (REP PMCB).** Importers of building materials are in scope ([F37937](https://entreprendre.service-public.gouv.fr/vosdroits/F37937)), and Leboncoin asks professional sellers of building materials for their unique identifier (IDU). Join an eco-organisation for the sector (Valobat or Ecominéro; confirm in writing which one covers natural stone), then put the IDU in the terms of sale and on Leboncoin.
- **Never use "liquidation".** It is reserved for declared closing-down sales ([F37880](https://entreprendre.service-public.gouv.fr/vosdroits/F37880)). Use "fin de stock, prix fixe". None of these files use it.

## Fixes to make in the Shopify store

0. **Blocking — before sending any private buyer to the checkout links** (landing page, WhatsApp, Leboncoin, Google or Meta ads): rewrite the terms of sale and the refund policy under French law (Pierre et retraites, SIREN 985 289 065, address, VAT number, 14-day withdrawal right for consumers including how collected stone is returned, consumer mediator, info@pierredegypte.online). Today they are unfilled US Shopify templates with "[INSERT RETURN ADDRESS]" and an exclusiveyogaretreats.com e-mail. Also publish a legal notice (Mentions légales), translate the privacy policy into French, add the landing page's host (e.g. Netlify or GitHub Pages, with its address) to that legal notice — `index.html` links to it — and rename the checkout variant to "Pierre seule — retrait sur rendez-vous (Gennevilliers ou Vernon)" (or add a Vernon variant) and add Vernon's address to the Livraison & Retrait page.
1. **Homepage badge says "Sur commande" (made to order)**, while the MINYALA deposit page says "MINYALA est en stock". Buyers who want stone now will skip it. Change the homepage card to **"En stock"**.
2. **The product page only links to the deposit.** The new description adds a "Commander 25 m² — 875 €" link.
3. **Real photos.** The current product image is an AI render (file name `ChatGPT_Image_…`). Photos of the actual pallets, a close-up of a slab, and a laid sample build trust and prevent "not as pictured" disputes. Once you have them, replace the image URL in `index.html`.
4. **Track inventory in Shopify.** Enter the real m² in stock so the store can't oversell, and so you can honestly say "plus que X m²".
5. *(Not MINYALA, but hurts trust)* The homepage says "Acompte 30% seulement" while SINAI SAND asks for a 75% deposit.

## Assumptions to check

- **Weight ≈ 50 kg/m²** in the calculator and the Leboncoin text is an estimate for 2 cm limestone. Adjust `KG_PER_M2` in `index.html` and the text if you have the real figure.
- **No discount was added.** Discount options (volume pricing, a promo code in the checkout link, a deadline) are listed at the end of `kit-de-vente.md` for you to decide on.
- The landing page uses the store's existing product image and the WhatsApp number from the site (+33 7 58 50 41 73). The calculator is capped at 2,000 m² (top of the stock range); set `MAX` in `index.html` to the exact stock.
- **Colour and origin.** "Golden veining" was removed everywhere: it came from the AI image, not from the store. Describe the colour from real photos, and use Minya trade names (Sunny Menia, Menia limestone) only if the supplier's documents confirm the origin.
- The last line of `shopify-description-produit.html` (`<!-- MASTER inventory refresh 2026-09-24 -->`) is an HTML comment copied from the live description. It is invisible to customers; it was kept in case an inventory tool relies on it.
