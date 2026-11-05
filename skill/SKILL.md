---
name: fpsot-i18n
description: Internationalization rules for FPSOT products. Use when adding user-visible text, formatting dates, numbers or amounts, choosing the language of a page, handling translation files, or building name and address fields.
---

# FPSOT internationalization

Summary of the FPSOT internationalization specification. It adds no rules of its own.
The spec text in `spec/` wins on any difference. Each line cites its requirement ID and keeps its strength: must, should or may.

## Language tags and locales

- Tags must be valid BCP 47 tags in the usual case, such as `fr-CA` (LOC-001). Tags should be as short as possible. `fr_CA` must never leave the program (LOC-002).
- FPSOT products must support `en-CA` and `fr-CA`. They may support other locales that have CLDR data (LOC-003).
- Each deployment must set one default, `en-CA` or `fr-CA`. Québec deployments should use `fr-CA` (LOC-004).
- The locale must come from the page choice, then the saved preference, then `Accept-Language`, then the default. It must not be guessed from location (LOC-005).
- Messages must fall back `fr-CA` → `fr` → default. A key or an empty string must never show (LOC-006).
- With both languages on one screen or document, the deployment must set the order: French first in Québec, English first elsewhere (LOC-007).

## Formatting

- Dates, numbers, amounts, units and lists must be formatted with a CLDR library, never hand-written patterns (LOC-010). Products should use CLDR 49 or later, and must state the version (LOC-011).
- Times must be shown in the zone of the person or place, identified by its IANA tz name. People must see the CLDR localized zone name; the zone should be shown when readers may be elsewhere (LOC-012).
- The currency must come from the data, not the locale (LOC-013). Formatted text must never be read back as data (LOC-014).
- Text for people must be sorted with CLDR collation for their locale, never by code point (LOC-015).

## Messages

- User-visible text must not be in code. Each message must have a stable key (LOC-020). Sentences must not be joined from fragments (LOC-021).
- Messages must use ICU MessageFormat syntax. They may use MessageFormat 2 where the library API is stable (LOC-022).
- Plurals must come from CLDR plural categories, never `if (n == 1)` (LOC-023).
- Wording should be gender-neutral. Gender must never be inferred (LOC-024).
- Each message must have a translator note. Same English, different meaning: two keys must exist (LOC-025).

## Translation

- Every user-visible text must exist in English and French before a release (LOC-030).
- Machine translation may make a draft only. It must be marked, and the release must block until a person reviews it (LOC-031, WRT-033).
- Interface messages must be in the platform catalog and must be exchanged as XLIFF 2.1 (LOC-032). Long text should use gettext PO, one entry per paragraph (LOC-033).
- New work must not use XLIFF 1.2. Projects may move to XLIFF 2.2 once it is an approved standard (LOC-034).
- Translation files must be UTF-8, under version control, named with the language tag (LOC-035), and must record the state of each entry (LOC-036).

## Markup and characters

- Each page and passage must declare its language, the one actually shown. API responses must set `Content-Language` for text whose language the product chose; data with its own language tags needs none (LOC-040).
- Every page must link to the other languages by their own names, with no flags (LOC-041).
- Text must be Unicode in UTF-8 end to end. Accents must never be stripped (LOC-042). Search should use NFC and match with or without accents (LOC-043).
- Products should be ready for right-to-left: direction in markup, `start`/`end` in style sheets, mirrored direction icons (LOC-044). Text of unknown direction must be isolated with `bdi` or `dir="auto"` (LOC-045).
- Text must not be in images. Layouts must leave room for longer French text (LOC-046).

## Names and addresses

- Products must not assume a first and a last name. They should ask for one full-name field, and may ask for parts only when a process needs them; parts must not be mandatory (LOC-050).
- Name fields must accept any Unicode letter and diacritical mark, one character and up, with no case change (LOC-051). A title must not be required (LOC-052).
- Addresses must be stored as fields with an ISO 3166-1 country code, formatted per country (LOC-053).
- Canadian addresses must follow Canada Post, with `A1A 1A1` postal codes (LOC-054). Street and municipality names must never be translated (LOC-055).
