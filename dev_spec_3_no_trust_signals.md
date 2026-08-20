# No trust signals — dev spec
Site: example.com · Priority 3 · High · Effort: Medium (2-5 days)

## Problem
The homepage lacks reviews, guarantees, or security badges, so first-time visitors have no reason to trust the site.

## Evidence (from the live site)
> This domain is for use in documentation examples without needing permission.

## Current state
h1: This domain is for use in documentation examples; cta: Learn more; notes: No trust signals present.

## Required change
h1: Explicit product/service and key benefit; cta: Descriptive CTA naming the outcome; notes: Add customer testimonials, trust badges, or a satisfaction guarantee near the primary CTA.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add customer testimonials, trust badges, or a satisfaction guarantee near the primary CTA.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_trust_signals` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
