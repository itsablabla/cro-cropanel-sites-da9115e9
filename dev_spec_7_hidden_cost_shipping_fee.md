# Hidden cost: shipping fee — dev spec
Site: allbirds.com · Priority 7 · High · Effort: Medium (2-5 days)

## Problem
Free shipping threshold is not clearly communicated on product pages, risking surprise at checkout.

## Evidence (from the live site)
> Product page shows 'Get Notified' and 'Learn More' CTAs but no mention of free shipping threshold; cart drawer shows 'Shipping $5.00' and 'Spend more to earn free shipping!'

## Current state
h1: Anytime Ankle Sock; cta: Get Notified / Learn More; notes: No shipping cost or threshold displayed on the product page.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Display 'Free shipping on orders over $100' near the price or add-to-cart button to set expectations and encourage larger orders.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Display 'Free shipping on orders over $100' near the price or add-to-cart button to set expectations and encourage larger orders.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_hidden_cost_shipping_fee` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
