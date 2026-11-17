# Made for You by Sahara 🌸

Next.js starter website with original product photography, a responsive catalogue, filtering, search, product detail overlays, quantity/colour/customisation inputs, FAQs, brand story and Google Forms ordering hooks.

## Start locally

```bash
npm install
cp .env.example .env.local
npm run dev
```

Open http://localhost:3000. Run `npm run build` before deployment.

## Configure order form

1. Create a Google Form with the customer, product and delivery fields from the project brief. Mark essential fields required, and include a privacy/consent checkbox.
2. In Google Forms, select **Responses → Link to Sheets** and create a **private** response sheet. Enable email notifications under Responses menu.
3. Copy the published respondent-facing form URL into `NEXT_PUBLIC_ORDER_FORM_URL` in `.env.local`.
4. Optional prefill: use Google Forms **Get pre-filled link** and inspect the resulting URL for each `entry.123456` identifier. Copy the numeric identifier (without `entry.`) into the matching `NEXT_PUBLIC_FORM_*_ENTRY` variable. Ensure the Google Form option text matches the website product name. If you use a dropdown with mismatched options, prefilling may not work.
5. Restart the development server. Test with a real sample order. Submitting the form is an **order request**, not a confirmed sale.
6. Set `NEXT_PUBLIC_REVIEW_FORM_URL` to a separate review form. Do not publish submitted reviews automatically. Only publish genuine reviews with permission after moderation.

## Social links

Set `NEXT_PUBLIC_INSTAGRAM_URL`, `NEXT_PUBLIC_WHATSAPP_NUMBER` (international digits, e.g. country code then number) and `NEXT_PUBLIC_BUSINESS_EMAIL`. Missing links are intentionally hidden.

## Update products

Edit `lib/catalog.ts` and replace/add original photos in `public/products`. The current flower-keychain and bow-keychain prices follow the latest uploaded specification (₹50 and ₹39); **confirm these before launch**, as earlier messages contained different prices.

## Deployment

Push the project to GitHub and import it into Vercel. Add the same environment variables in the Vercel project settings. Redeploy after changes. Connect a custom domain in Vercel when ready.

## Important launch limitations

- Google Forms and social links require real owner-supplied URLs; without them, order buttons show a clear setup-pending message.
- The review section displays no fabricated testimonials. Live review publication is not configured.
- Delivery, payment, customisation fees, privacy retention and returns require owner confirmation.
- No payment collection, authentication or admin dashboard is included in this first version. Product content is edited in `lib/catalog.ts`.
- This is a working **initial website build**, not yet a tested live deployment.

## Confirmed product prices (17 November 2026)
- Crochet Flower Keychain: ₹150 each
- Crochet Bow Keychain: ₹39 each
- Handmade Crochet Hairband: ₹50 each
- Crochet Flower Hair Garland: ₹99 each

## Step 3: Google Forms setup
Create a Google Form for order requests and connect its Responses tab to a private Google Sheet. Add the form public URL to `NEXT_PUBLIC_ORDER_FORM_URL` in `.env.local`. The optional prefill entry IDs can be configured after obtaining a prefilled Google Form URL. Do not put private Google Sheets credentials in public environment variables.

## Step 4: Genuine customer reviews
See [REVIEWS-SETUP.md](REVIEWS-SETUP.md) for the separate Google feedback form, private Sheet, consent-based moderation, and test instructions. Public testimonials are manually curated in `lib/reviews.ts` and start empty. Set `NEXT_PUBLIC_REVIEW_FORM_URL` to enable the feedback button.

## Customer feedback form (connected)
The Share Your Experience button opens the owner-provided Google Feedback Form. The URL is in `.env.local`, `.env.example`, and the fallback configuration in `lib/catalog.ts`. Customer reviews remain private until individually approved and manually added to `lib/reviews.ts`. See `REVIEWS-SETUP.md`.


## Step 5
See `STEP-5-LAUNCH-GUIDE.md` for publishing prerequisites, mobile QA and deployment instructions.

## Customer contact (confirmed)
Business email: **madeforyoubysahara@gmail.com**. Contact section uses `mailto:`. Instagram and WhatsApp are not enabled.

## Returns policy update (Step 5)
The `/delivery` page now contains a case-by-case cancellation, return and refund policy. See `STEP-5-RETURNS-AND-PUBLISHING.md` for owner review and launch steps.
