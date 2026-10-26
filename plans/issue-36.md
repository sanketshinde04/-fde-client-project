# Plan for Issue #36: Build holiday package catalog and retrieval service

## Goal
Build a holiday package catalog schema, seed dataset, and retrieval service to query packages and travel FAQs by destination, budget, and dates.

## Steps
1. Define package and travel FAQ data schemas with fields for destination, duration, base price, dates, and inclusions.
2. Create a representative seed dataset of holiday packages and travel FAQs.
3. Implement a retrieval service supporting structured filtering by destination, budget, and travel dates.
4. Add graceful fallback handling when queries return no matching packages.
5. Write unit tests covering catalog queries, empty results, and fixture loading.

## What could go wrong
- Filter logic may fail to handle flexible or ambiguous search inputs like broad date ranges.
- Schema might miss pricing or metadata fields needed downstream for currency conversion (#39) or LLM state (#37).
- Fixture loader or queries may encounter formatting inconsistencies in mock data.

## Done when
- [ ] Holiday package and FAQ schemas are defined.
- [ ] Seed dataset with initial packages and FAQs is created and loadable.
- [ ] Retrieval service filters packages by destination, budget, and dates.
- [ ] Fallback handling handles zero-match scenarios gracefully.
- [ ] Unit tests pass for retrieval logic and fixture loading.
