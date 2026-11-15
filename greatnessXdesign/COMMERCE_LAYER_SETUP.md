# Commerce Layer Setup

Adds cart, Starter System bundle, Stripe coupons/promotion codes, paid order confirmation, cart upsells, and post-purchase upsells.

## Netlify environment variables

Existing: `STRIPE_SECRET_KEY`, `STRIPE_PRICE_VISION_WORKBOOK`, `STRIPE_PRICE_CREATOR_LAUNCH_PLAYBOOK`, `STRIPE_PRICE_GREATNESS_DAILY_PLANNER`

New: `STRIPE_PRICE_STARTER_BUNDLE` — create a $49 Stripe Price for the Starter System Bundle.

## Coupons
Create a percentage Stripe Coupon, then create a customer-facing Promotion Code such as `WELCOME10`. The browser asks the server to validate it; the server passes the real Stripe Promotion Code into Checkout.

## Test
Use Stripe Test Mode and card `4242 4242 4242 4242`. Test product cart, bundle, invalid coupon, valid coupon, cancelled checkout, successful checkout, order confirmation, and upsells.

## Deployment
Deploy as a Netlify project or via Netlify CLI because the package uses Netlify Functions. Static drag-and-drop is not sufficient for the server-side Stripe layer.

## Digital-file protection
The existing PDFs are static public files. For stronger protection, move paid files to private object storage and issue short-lived signed URLs after the paid-session check.
