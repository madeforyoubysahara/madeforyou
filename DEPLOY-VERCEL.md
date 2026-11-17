# Deploy Made for You by Sahara on Vercel

## 1. Prepare a GitHub repository
1. Extract the ZIP and open the `made-for-you-sahara` folder.
2. Create a new **private** GitHub repository.
3. Upload the project files (including `app`, `lib`, `public`, `package.json`, `tsconfig.json`, `.gitignore`, `.env.example`). Do not upload `.env.local`.
4. Make sure GitHub shows `package.json` at the repository root, not nested in another folder.

## 2. Import to Vercel
1. Sign in to https://vercel.com with GitHub.
2. Choose Add New > Project and import the repository.
3. Framework preset: Next.js. Root Directory: `./` if package.json is at repository root.
4. Add these Environment Variables under Project Settings or during import:

NEXT_PUBLIC_ORDER_FORM_URL=https://docs.google.com/forms/d/e/1FAIpQLSdNj3kOocAoaQbGmkCGWs1fblndDvpymkbxLff22hJeydhlJg/viewform
NEXT_PUBLIC_REVIEW_FORM_URL=https://docs.google.com/forms/d/e/1FAIpQLSef226Bhg24ZPqyuRYNZCSFfVfcRnaRDBzsg09kXFejcr1tUg/viewform
NEXT_PUBLIC_BUSINESS_EMAIL=madeforyoubysahara@gmail.com
NEXT_PUBLIC_FORM_PRODUCT_ENTRY=882890060
NEXT_PUBLIC_FORM_QUANTITY_ENTRY=694796155
NEXT_PUBLIC_FORM_COLOR_ENTRY=1767508639
NEXT_PUBLIC_FORM_NOTES_ENTRY=129304157

Optional: NEXT_PUBLIC_INSTAGRAM_URL and NEXT_PUBLIC_WHATSAPP_NUMBER can remain unset.
5. Click Deploy. Wait for the deployment to show Ready and review the build logs.

## 3. Validate the production deployment
- Open your assigned `https://...vercel.app` URL on mobile and desktop.
- Verify catalogue images, product names, and prices ₹150/₹39/₹50/₹99.
- Check that each product's Order Now button opens Google Forms with the right prefilled product, quantity, colour, and notes.
- Submit a clearly marked test order and confirm a new row in your restricted Google Sheet.
- Open Share Your Experience, submit a test feedback response, and confirm it in the private feedback Sheet. Do not publish test reviews.
- Visit `/privacy` and `/delivery`, check customer support email and review policies.
- In the Google Order Form editor, replace `https://YOUR-SITE.com/privacy` in the consent text with your real Vercel `/privacy` URL.
- Remove test rows after verifying them.

## Build check
Run `npm install` and `npm run build` locally if desired. This environment may not have npm registry access; Vercel's build log is the definitive build test for the deployed revision.

## Security
Never commit `.env.local`. Google Forms are public responder links; Google Sheets should remain private. The site is a catalogue and order-request workflow, not a payment checkout.
