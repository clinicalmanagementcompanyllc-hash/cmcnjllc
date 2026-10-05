# CMCNJ static site

Portable HTML/CSS/JavaScript site. No WordPress, PHP, Node, or database is required.

## Configure GA4
Edit `index.html` and replace `G-XXXXXXXXXX` with the site's GA4 Measurement ID.

## A/B testing
The built-in experiment is `homepage_hero_v1`. Visitors are randomly assigned A or B and the choice is persisted.

Force a variant:
- `?variant=A`
- `?variant=B`

Campaign example:
`?utm_source=linkedin&utm_medium=organic_social&utm_campaign=img_ascp&variant=B`

## Form / documents
The original form endpoint is preserved: `https://formspree.io/f/myknylaw`.
Formspree currently documents native file uploads as available on Personal, Professional, and Business plans. Its current system limits include up to 10 files per submission, 25 MB per file, and a 100 MB request size. The current Free plan starts at 50 submissions/month.

For a no-cost pilot, the form can still be used for no-file intake, or document collection can be separated into a workflow specifically designed for sensitive documents.

## Deployments
### GitHub Pages
Push this repository to GitHub, then Settings -> Pages -> Source: GitHub Actions. The included workflow publishes it automatically from `main`.

### GitLab Pages
Push to GitLab with the included `.gitlab-ci.yml`. Every push to the default branch runs Pages deployment.

### Cloudflare Pages
Import this repository as a static site. Build command: blank. Output directory: `/`. Then enable Cloudflare Web Analytics from Metrics.

### Netlify
Import the repository or drag/drop the folder. Publish directory: `.`. Build command: blank.

## Recommended setup
Use one Git repository as the source of truth and connect it to Cloudflare Pages, GitHub Pages, GitLab Pages, and Netlify. Use Cloudflare as primary and the others as secondary/preview/failover environments. Keep a customer-facing domain pointed at one canonical host at a time.

Do not place private API keys or provider admin credentials in this static repository.
