# Shipping delay warning — dev spec
Site: allbirds.com · Priority 2 · Urgent · Effort: Medium (2-5 days)

## Problem
The prominent 'orders may take up to 30 days to ship' warning creates immediate purchase hesitation and undermines trust in delivery reliability.

## Evidence (from the live site)
> Body sample: 'Due to increased demand, orders may take up to 30 days to ship.' appears prominently near the top of the page.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Warning is displayed without context or mitigation, likely scaring off potential buyers.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Replace with a reassuring message like 'Free shipping on orders over $100' or 'Most orders ship within 2-3 days' and move any delay notice to a less prominent location or provide an option for expedited shipping.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Replace with a reassuring message like 'Free shipping on orders over $100' or 'Most orders ship within 2-3 days' and move any delay notice to a less prominent location or provide an option for expedited shipping.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_shipping_delay_warning` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
