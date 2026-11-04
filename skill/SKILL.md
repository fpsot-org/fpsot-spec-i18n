---
name: fpsot-i18n
description: Internationalization rules for FPSOT products. Use when adding user-visible text, formatting dates, numbers or amounts, choosing the language of a page, handling translation files, or building name and address fields.
---

# FPSOT internationalization

Summary of the FPSOT internationalization specification. It adds no rules of its own.
The spec text in `spec/` wins on any difference. Each line cites its requirement ID.

## Language tags and locales

- Use valid BCP 47 tags in the usual case, such as `fr-CA` (LOC-001). Keep them short. Never send `fr_CA` out of the program (LOC-002).
- FPSOT products support `en-CA` and `fr-CA`. Other locales may come from CLDR data and contributed translations (LOC-003).
- Each deployment sets one default, `en-CA` or `fr-CA`. Québec deployments should use `fr-CA` (LOC-004).
- Choose the locale from the page choice, then the saved preference, then `Accept-Language`, then the default. Never guess from location (LOC-005).
- Fall back `fr-CA` → `fr` → default. Never show a key or an empty string (LOC-006).
- With both languages on one screen, French first in Québec, English first elsewhere (LOC-007).

## Formatting

- Format dates, numbers, amounts, units and lists with a CLDR library, never hand-written patterns (LOC-010). State the CLDR version, 49 or later (LOC-011).
- Show times in the zone of the person or place, named with a tz database name (LOC-012).
- Take the currency from the data, not the locale (LOC-013). Never parse formatted text back as data (LOC-014).
- Sort with CLDR collation for the reader's locale (LOC-015).

## Messages

- No user-visible text in code. Each message has a stable key (LOC-020). Never join fragments into a sentence (LOC-021).
- Use ICU MessageFormat syntax. MessageFormat 2 only where the library API is stable (LOC-022).
- Plurals come from CLDR plural categories, never `if (n == 1)` (LOC-023).
- Prefer gender-neutral wording. Never infer gender (LOC-024).
- Give each message a translator note. Same English, different meaning: two keys (LOC-025).

## Translation

- Every user-visible text exists in English and French before a release (LOC-030).
- Machine translation is a draft only. Mark it, and block the release until a person reviews it (LOC-031, WRT-033).
- Interface messages: platform catalogue, exchanged as XLIFF 2.1 (LOC-032). Long text: gettext PO, one entry per paragraph (LOC-033).
- No XLIFF 1.2 for new work. XLIFF 2.2 once it is an approved standard (LOC-034).
- Translation files are UTF-8, under version control, named with the language tag (LOC-035), and record the state of each entry (LOC-036).

## Markup and characters

- Declare the language of each page and passage, and set `Content-Language` on API responses (LOC-040).
- Link every page to the other languages by their own names, with no flags (LOC-041).
- Unicode in UTF-8 end to end. Never strip accents (LOC-042). Search in NFC, with or without accents (LOC-043).
- Set direction in markup, use `start`/`end` in style sheets, mirror direction icons (LOC-044). Isolate text of unknown direction with `bdi` or `dir="auto"` (LOC-045).
- No text in images. Leave room for longer French text (LOC-046).

## Names and addresses

- One full-name field. Optional parts only when a process needs them (LOC-050).
- Accept any Unicode letter, one character and up, no case change (LOC-051). No required title (LOC-052).
- Store addresses as fields with an ISO 3166-1 country code, formatted per country (LOC-053).
- Canadian addresses follow Canada Post: `A1A 1A1` postal codes (LOC-054). Never translate street or municipality names (LOC-055).
