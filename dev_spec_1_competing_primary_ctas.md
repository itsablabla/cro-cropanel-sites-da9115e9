# Competing primary CTAs — dev spec
Site: allbirds.com · Priority 1 · Urgent · Effort: Medium (2-5 days)

## Problem
Two equally prominent CTAs in the hero split user attention and dilute the primary conversion path.

## Evidence (from the live site)
> Hero section contains both 'SHOP MEN' and 'SHOP WOMEN' CTAs, with no single primary action.
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN' and 'SHOP WOMEN' with no subheadline to clarify the brand's specific benefits.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Both CTAs are equally styled and placed, forcing users to choose a gender before seeing products.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Shop All; notes: Use a single primary CTA to 'Shop All' to reduce friction and let users explore without an initial gender choice.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Use a single primary CTA to 'Shop All' to reduce friction and let users explore without an initial gender choice.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_primary_ctas` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
