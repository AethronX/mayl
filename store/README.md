# MAYL Store — Audit & Content

Store: **MAYL** (`mayl-plus.myshopify.com`) · Basic plan · Oman · OMR

## Applied via API

| # | Change | Detail |
|---|--------|--------|
| 1 | Product taxonomy set | `Apparel & Accessories > Clothing Accessories > Sunglasses` — was empty. Drives tax rules, Google Shopping, and marketplace sync. |
| 2 | Product handle cleaned | `classic-two-tone-sunglasses-...-%D9%86%D8%B8...` (≈300 chars of URL-encoded Arabic) → `mayl-two-tone-sunglasses` |
| 3 | Collection handle cleaned | Same problem → `mayl-sunglasses` |
| 4 | Variant weights set | All 4 variants were **0 kg** → 0.2 kg. Weight-based shipping rates cannot compute at 0. **Estimate — confirm against a real packed weight.** |
| 5 | Demo collection deleted | "Electronics and Accessories example products", 0 products — leftover from store setup |
| 6 | FAQ page created | `/pages/faq`, bilingual EN/AR |
| 7 | Footer menu updated | Added FAQ + Privacy Policy links |

## Not applied — needs Shopify admin

The connector lacks the `write_legal_policies` scope, so policies must be pasted manually.

**Only 1 of 4 legal policies exists.** Privacy Policy is present (Shopify default). Missing:

- `policies/refund-policy.html`
- `policies/shipping-policy.html`
- `policies/terms-of-service.html`

Paste each into **Settings → Policies** (paste as HTML via the `<>` source view). All three are bilingual EN/AR, matching the store's existing pattern.

A missing refund policy is the single biggest conversion and trust gap on a new store, and payment providers often require one.

After adding them, add footer links for `/policies/refund-policy`, `/policies/shipping-policy`, and `/policies/terms-of-service` alongside the Privacy Policy link.

## Assumptions baked into the policy text

Confirm these match how the business actually runs, and edit before publishing:

- 14-day return window
- Customer pays return shipping on change-of-mind; MAYL pays on defective/wrong items
- Order processing 1–2 business days (Sun–Thu)
- Delivery 1–3 business days Muscat, 3–6 other governorates
- Contact address `mind.balance77@gmail.com` (currently the store's only public contact)
- Governing law: Sultanate of Oman

## Remaining gaps worth closing

- **No custom domain.** Store runs on `mayl-plus.myshopify.com`. A branded domain is the largest remaining trust signal.
- **No shop description** set at the shop level.
- **No barcodes** on variants — needed if you ever sell through marketplaces or use a scanner.
- **Compare-at price is 15.900 against a 9.900 price** — a permanent 38% markdown on every variant. Effective as a launch tactic; it reads as a fake discount if it never ends.
- **Verify shipping zones and payment provider** are configured — not readable through the current connector scopes.
- **Single product, 20 units.** Catalog depth is the real ceiling on the store, not configuration.
