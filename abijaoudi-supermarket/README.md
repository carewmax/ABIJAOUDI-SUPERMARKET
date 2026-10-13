# Abijaoudi Supermarket website

A multi-page supermarket storefront built in React. It is one self-contained `index.html`, so there is no build step.

Pages: Home, Shop (categories, sorting, load more), Search, Deals & Offers, Product detail (gallery, quantity, reviews), Cart (page and drawer), Checkout, Order confirmation, Account (profile, wishlist, demo orders), About and Contact.

## Run it

Open `index.html` in a browser. It loads React, htm and Google Fonts from a CDN, so it needs an internet connection.

## Put it on GitHub Pages

1. Create a new repository on GitHub and upload everything in this folder (or unzip and drag the files in).
2. In the repository go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
4. After a minute the site is live at `https://<your-username>.github.io/<repository-name>/`.

It also works on Netlify: drag the folder onto the Netlify dashboard.

## Edit the store details

Open `index.html` and search for `const CONFIG`. Everything the store still has to confirm lives there:

| Setting | What it does |
| --- | --- |
| `contact.phone`, `email`, `address`, `hours`, `mapsUrl` | Shown on Contact and in the footer. Empty values show "to be confirmed". |
| `contact.whatsapp` | Adds a WhatsApp button (digits with country code). |
| `contact.social` | Footer links, e.g. `[{label:'Facebook',url:'https://...'}]`. |
| `fulfilment` | e.g. `['Delivery','Store pickup']` once confirmed. Adds a choice to checkout. |
| `deliveryFee` | A number once confirmed. Until then the cart shows "To be confirmed". |
| `announcement` | The top bar text. Set it to `''` to remove it. |

Products are in the `PRODUCTS` list (search for `const PRODUCTS`). Each line is `P(id, name, size, category, price, imageKey, tags, oldPrice)`. Add `oldPrice` only for a confirmed offer, and the discount percentage is calculated for you. Categories are in `CATS`.

## Replace the images

The photos and product packs are embedded in `index.html` as data, so the site works as a single file. The same pictures are in `assets/`. They were cropped from the design mockup, so they are soft at large sizes. To use your own photos, replace the matching entries in the `window.ASSETS` list near the bottom of `index.html`, or point those entries to files such as `assets/logo.png`.

## Prototype notes

- Products, prices and discounts are samples from the mockup and must be confirmed before launch.
- The cart, wishlist, reviews, profile and demo orders are saved in the visitor's browser only.
- Checkout and the contact form are demos. They send nothing and take no payment. Connect an ordering system, email service and payment provider before going live.

## Folder

```
index.html        the whole site
assets/           the logo, photos and product images used by the site
.nojekyll         tells GitHub Pages to serve the files as they are
README.md         this file
```
