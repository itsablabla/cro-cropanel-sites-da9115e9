# Vague hero copy — dev spec
Site: allbirds.com · Priority 3 · Urgent · Effort: Low (0.5-2 days)

## Problem
The hero headline 'Wildly Comfortable. Super Natural.' is abstract and doesn't directly address the visitor's intent to find comfortable, sustainable shoes, leaving them to infer the value proposition.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN' and 'SHOP WOMEN' with no subheadline to clarify the brand's specific benefits.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: The hero lacks a clear subheadline that ties comfort and sustainability to specific product benefits, and the CTAs are generic.

## Required change
h1: Shoes That Feel Like Clouds, Made from the Earth; cta: Shop Men's Shoes / Shop Women's Shoes; notes: A more concrete headline that directly states the dual benefit of comfort and sustainability, with CTAs that specify the product category.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN A more concrete headline that directly states the dual benefit of comfort and sustainability, with CTAs that specify the product category.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_hero_copy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
