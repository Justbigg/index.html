# Greatness by Design — Commerce Setup

The site now uses Stripe Checkout through Netlify Functions.

## Create these Stripe prices

- Greatness by Design — Vision Workbook — $19 USD
- Creator Launch Playbook — $29 USD
- Greatness Daily Planner — $9 USD

Copy each `price_...` ID.

## Add these Netlify environment variables

- `STRIPE_SECRET_KEY`
- `STRIPE_PRICE_VISION_WORKBOOK`
- `STRIPE_PRICE_CREATOR_LAUNCH_PLAYBOOK`
- `STRIPE_PRICE_GREATNESS_DAILY_PLANNER`

Never place the Stripe secret key in browser code or commit it to Git.

## Test before going live

Use Stripe test mode and a `sk_test_...` key with test-mode price IDs. Stripe's standard test card is `4242 4242 4242 4242`, with any future expiry, any three-digit CVC, and a valid-looking ZIP.

A successful test should return to `success.html` and reveal the purchased PDF only after Stripe reports the session as paid.

## Go live

Create live-mode prices, replace the three price IDs, replace the secret key with the live secret key, and redeploy.

## Included commerce flow

Product button → Netlify Function → Stripe-hosted Checkout → verified paid session → purchased PDF.

For larger products, memberships, customer accounts, licenses, tax automation, or expiring download URLs, use dedicated digital-delivery/storage infrastructure rather than public static PDFs.

Also configure your Stripe business name, support email, statement descriptor, refunds, taxes, and receipt settings before launch.
