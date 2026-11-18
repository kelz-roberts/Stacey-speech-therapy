# Stacey Wall Speech-Language Therapy website

Static site, no build step. Pages are views inside `index.html` (Home, How we help, For parents, About us, FAQs and fees, Contact, Privacy), switched by the URL hash, e.g. `/#faqs`.

## Files
- `index.html`: all page content, plus two settings at the top of the main script
- `style.css`: styles and brand colours
- `img/`: logo, photos and illustrations
- `.nojekyll`: tells GitHub Pages to serve files as they are

## Publish on GitHub Pages
1. Create a new repository on GitHub and upload all files in this folder (keep the `img` folder).
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After a minute or two the site appears at `https://<your-username>.github.io/<repo-name>/`.

## Custom domain (staceyspeechtherapy.co.za)
1. In **Settings > Pages > Custom domain**, enter `staceyspeechtherapy.co.za` and save. This adds a `CNAME` file.
2. At the domain's DNS host (currently Squirrel Media), add A records for `@` pointing to 185.199.108.153, 185.199.109.153, 185.199.110.153 and 185.199.111.153, and a CNAME record for `www` pointing to `<your-username>.github.io`.
3. Once DNS has updated, tick **Enforce HTTPS**.
4. Check the email (MX) records are left alone, so info@ mail keeps working.

## Make the enquiry form send email
GitHub Pages can't send email itself, so use a form service:
1. Sign up at https://formspree.io (free plan is fine) and create a form with Stacey's email as the recipient.
2. Copy the endpoint (looks like `https://formspree.io/f/abcdwxyz`).
3. In `index.html`, set `var FORM_ENDPOINT = 'https://formspree.io/f/abcdwxyz';`
4. Submit a test enquiry and confirm the first email in Formspree.

The form requires a name and at least a phone number or an email. A hidden honeypot field filters out simple spam bots.

## Before going live
- Set `var SHOW_PROTOTYPE_NOTES = false;` in `index.html` to hide the prototype bar and the yellow "to confirm" tags.
- Search `index.html` for `class="confirm"` and replace each one with Stacey's real details (fees, hours, session length, languages, parking, Facebook link, Jasmika's HPCSA number).
- Have Stacey review the privacy notice.
