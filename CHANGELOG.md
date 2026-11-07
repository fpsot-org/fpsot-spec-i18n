# Changelog

All notable changes to this specification are listed here.
The format follows [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/),
and versions follow [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.2.0] - 2026-11-07

### Changed

- LOC-046 now has an exception: a diagram, a chart or another picture with significant other visual content is not an image of text, under the WCAG 2.2 definition. Its text stays real text, as the FPSOT diagrams specification sets out.
- The skill states the LOC-046 exception.

### Fixed

- The BCP 47 link in LOC-001 now goes to the BCP 47 page, not to RFC 5646. BCP 47 joins the references with an archived copy.
- Link texts now name the standard, such as "CLDR 49", "XLIFF 2.1", "UTS #35", the Time Zone Database and the Language Subtag Registry, instead of words such as "data" or "version 2.1".
- The French pages link the French Canada Post addressing guidelines, with an archived copy.
- UTS #35 Part 9 (MessageFormat) now has an archived copy of its revision 79 page.

## [0.1.2] - 2026-11-05

### Fixed

- The Québec policy on French in information technology now has a current archived copy of its quebec.ca page, instead of a 2011 copy of an older page.

## [0.1.1] - 2026-11-04

### Changed

- Each page links the outside standards it names, including the conformance RFCs, and lists them under References.
- The Sources table of the index page is now its References section, split into normative and informative sources.
- English text uses US spelling, with Merriam-Webster as the reference.
- The repository turns on the references and US spelling checks in `.fpsot-checks`.

## [0.1.0] - 2026-11-04

### Added

- Language tags and locales: BCP 47 tags, `en-CA` and `fr-CA`, the default locale, negotiation, fallback and language order (LOC-001 to LOC-007).
- Formatting with CLDR data: dates, times, numbers, amounts, lists and sorting (LOC-010 to LOC-015).
- Messages: text outside the code, ICU MessageFormat, plurals, gender-neutral wording and translator notes (LOC-020 to LOC-025).
- Translation: English and French in every product, reviewed machine drafts, XLIFF 2.1 and PO files (LOC-030 to LOC-036).
- Text, markup and direction: language declaration, language links, UTF-8, right-to-left readiness and text expansion (LOC-040 to LOC-046).
- Names and addresses: personal names, postal addresses and Canada Post formats (LOC-050 to LOC-055).
- Comparison data with an international baseline, Canada and Québec rows.
- A how-to guide, the agent skill, `llms.txt` and a book per language.

### Known gaps

- The Québec comparison does not yet cover the Charter of the French language, as amended by Bill 96 in 2022.
