# Final launch checklist

1. Extract this ZIP and upload the **contents** of the `made-for-you-sahara` folder to a private GitHub repository (do not upload `.env.local`).
2. Import the repository into Vercel as a Next.js project; use the repository root directory.
3. Set public variables from `.env.example` for the Google order/feedback forms and prefilling IDs. Set server-only `ADMIN_PASSWORD`, `GITHUB_TOKEN`, `GITHUB_REPO`, `GITHUB_BRANCH` as explained in `ADMIN-SETUP.md`.
4. Deploy and confirm a successful Vercel production build; if it fails, copy the build log for troubleshooting.
5. Open the live website on mobile and desktop; check images (no human models), product details, prices, form prefilling, customer contact email and policy pages.
6. Submit a test order and test feedback, verify each in its private Google Sheet, then delete the test rows. No fake reviews should be published.
7. Test `/admin` by signing in, changing a product tagline, saving, and checking that Vercel redeploys the change. Restore the original tagline afterward.
8. Update the Google order form's privacy consent link from `https://YOUR-SITE.com/privacy` to your actual Vercel domain + `/privacy`.
9. Review and finalise your delivery and returns policy for the business before accepting orders.
10. Do not publish your admin password, GitHub token, customer contact records or private Google Sheets.
