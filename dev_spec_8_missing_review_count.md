# Missing review count — dev spec
Site: allbirds.com · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
The product page shows a reviews section but lacks a visible review count or rating summary, reducing social proof and increasing uncertainty about product quality.

## Evidence (from the live site)
> H2s include 'Reviews for Anytime Ankle Sock' but no review count or star rating is visible in the provided content.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: Reviews section exists but no aggregate rating or count is displayed near the product title or CTA.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Add a star rating and review count (e.g., '4.8/5 from 1,200+ reviews') directly under the product title or near the price to provide immediate social proof.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a star rating and review count (e.g., '4.8/5 from 1,200+ reviews') directly under the product title or near the price to provide immediate social proof.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_review_count` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
