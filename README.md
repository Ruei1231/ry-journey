# Your Travel Journal Site

A set of plain HTML / CSS pages — no framework required, ready to deploy on a free host.

## File structure

```
index.html            Homepage (three entries: About / Journal / Contact)
about.html             About Me — single-page bio
journal.html           Photo Journal — list of entries
entry-kyoto.html        Example article
entry-portugal.html     Example article
entry-hokkaido.html     Example article
entry-jordan.html       Example article
contact.html            Contact form
styles.css              Shared styles
```

## Deploying (recommended: Netlify — free, custom domain, built-in form handling)

1. Sign up at [netlify.com](https://netlify.com).
2. Drag this whole folder into Netlify's deploy page (no Git required, though you can connect a GitHub repo later).
3. Netlify gives you a free `xxxx.netlify.app` address right away.
4. In **Domain settings**, add the domain you've purchased (e.g. from Cloudflare, Namecheap, or Porkbun) and follow the DNS instructions.
5. `contact.html` already has the attributes Netlify Forms needs (`data-netlify="true"`). Once deployed on Netlify, no extra setup is required — submissions show up automatically under the **Forms** tab in your Netlify dashboard.

### If you'd rather use GitHub Pages

GitHub Pages is also free and supports a custom domain, but it doesn't provide a form backend. Steps:

1. Create a GitHub repository and upload these files.
2. Go to **Settings → Pages** and choose the branch to publish.
3. Under **Settings → Pages → Custom domain**, add your domain.
4. For the form: replace the `<form>` tag in `contact.html` with one pointed at [Formspree](https://formspree.io) (the free tier is plenty for a personal site) — set `action="https://formspree.io/f/your-form-id"` following their setup guide.

## Making it yours

- **Name / domain**: search every file for `Your Name`, `yourdomain.com`, and `@yourhandle`, and swap in your own.
- **About page photo**: `.about-portrait` in `about.html` is currently a gradient placeholder. Swap it for a real photo:
  ```css
  .about-portrait{ background-image: url('images/your-photo.jpg'); background-size: cover; background-position: center; }
  ```
- **Journal thumbnails / article images**: same idea — swap the gradient on `.entry-thumb` and `.figure-block` for `url('images/xxx.jpg')`. It's worth keeping all photos in a new `images/` folder to stay organized.
- **Adding a new entry**: duplicate any `entry-*.html` file, update the title, location, date, and body copy, and save it under a new filename. Then go to `journal.html`, copy one `<a class="entry-card">` block, point it at the new file, and swap in a thumbnail colour and description.

## Design notes

- The wordplay: **Portrait** (About Me), **Wander** (Photo Journal), **Hello** (Contact) — each big vertical word names what that section actually does.
- The small circular "postmark" in the corner is the site's one signature flourish, tying back to the travel-journal theme. It has a gentle stamp-in animation on load (and respects reduced-motion preferences).
- Hovering a homepage panel reveals a themed gradient behind the text, standing in for a real photo — swap those gradients for actual photography whenever you're ready.
