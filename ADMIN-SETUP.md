# Product admin dashboard — Made for You by Sahara

The owner dashboard is at `/admin`. It supports adding, editing, removing products, changing prices, and uploading product photographs. **It is not a database**: it commits the edited `lib/products.json` and uploaded images to your GitHub repository. Vercel automatically rebuilds the website after each commit when Git integration is enabled.

## Required Vercel environment variables (server-side, NOT NEXT_PUBLIC_)

- `ADMIN_PASSWORD`: a long unique secret (at least 20 characters recommended). Do not reuse your Gmail password.
- `GITHUB_REPO`: `your-github-username/made-for-you-by-sahara` (replace with actual owner/repo).
- `GITHUB_BRANCH`: `main` (or your production branch).
- `GITHUB_TOKEN`: a GitHub **fine-grained personal access token**, restricted to the one website repository, with **Contents: Read and write**. Store it only in Vercel environment variables, never in GitHub files or chat.

Vercel project → Settings → Environment Variables → add variables for Production. Redeploy after saving variables.

## Usage

1. Visit `https://YOUR-SITE.vercel.app/admin`.
2. Enter the admin password. The password is kept in the page's memory and sent only to the server over HTTPS; it is not saved in localStorage.
3. Edit an existing product or click **Add product**. Each product requires a unique ID, name, price, category, description, tagline, colour description, and at least one image.
4. Upload JPG/PNG/WebP images smaller than 4 MB; wait for the upload success message. Uploaded images are committed to GitHub immediately; then click **Save catalogue** to attach them to a product.
5. Vercel will rebuild and redeploy when GitHub commits arrive. Wait for the build to finish before checking the live shop. This may take a few minutes.
6. To remove a product, click **Remove**, then **Save catalogue**. Its image files remain in GitHub; removing a product does not delete assets.

## Security and limitations

- Never set `NEXT_PUBLIC_ADMIN_PASSWORD` or `NEXT_PUBLIC_GITHUB_TOKEN`; these would leak secrets into client code.
- The admin API rejects requests without the password. The GitHub token stays on the server.
- Protect the admin password and GitHub token; rotate them if compromised. Restrict repository token permissions.
- This is a simple single-owner dashboard, not multi-user role-based authentication. It has no audit log, rate limiter or managed login service. For a higher-traffic store, use a managed authenticated CMS and database.
- The admin reads from the production branch of GitHub. Concurrent edits from two browser tabs can overwrite each other; avoid simultaneous edits.
- The storefront uses a bundled catalogue; changes become public only after a successful Vercel rebuild.
- GitHub/Vercel integration and production deployment must be configured and tested by the owner. No live deployment is performed by this project ZIP.
