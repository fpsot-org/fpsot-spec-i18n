# Terms needed in the writing term base

These entries are not yet in `fpsot-spec-writing/termbase/terms.yaml`.
They use the format of that file.
The ids `iana` and `utf-8` match the ids proposed by the FPSOT data types specification, so the two proposals merge into one entry each.

```yaml
  - id: iana
    kind: abbreviation
    en: {short: "IANA", full: "Internet Assigned Numbers Authority", definition: "The body that keeps the shared registries of Internet identifiers, such as language subtags and time zone names."}
    fr: {short: "IANA", full: "Internet Assigned Numbers Authority", definition: "Organisme qui tient les registres communs des identifiants d'Internet, comme les sous-étiquettes de langue et les noms de fuseaux horaires."}
    source: {name: "TERMIUM Plus", url: "https://www.btb.termiumplus.gc.ca/tpv2alpha/alpha-eng.html?lang=eng&srchtxt=IANA", checked: "2026-11-04"}
  - id: icu
    kind: abbreviation
    en: {short: "ICU", full: "International Components for Unicode", definition: "Open source libraries for C, C++ and Java that format, sort and translate text with Unicode locale data."}
    fr: {short: "ICU", full: "International Components for Unicode", definition: "Bibliothèques libres pour C, C++ et Java qui mettent en forme, trient et traduisent le texte avec les données régionales d'Unicode."}
    source: {name: "ICU", url: "https://unicode-org.github.io/icu/", checked: "2026-11-04"}
  - id: po
    kind: abbreviation
    en: {short: "PO", full: "Portable Object", definition: "The plain-text translation file format of GNU gettext, with one source string and its translation per entry."}
    fr: {short: "PO", full: "Portable Object", definition: "Format de fichier de traduction en texte brut de GNU gettext, avec une chaîne source et sa traduction par entrée."}
    source: {name: "GNU gettext manual", url: "https://www.gnu.org/software/gettext/manual/html_node/PO-Files.html", checked: "2026-11-04"}
  - id: utf-8
    kind: abbreviation
    en: {short: "UTF-8", full: "8-bit Unicode Transformation Format", definition: "The Unicode character encoding that uses one to four bytes per character and matches ASCII for basic Latin letters."}
    fr: {short: "UTF-8", full: "format transformé d'Unicode 8 bits", definition: "Codage des caractères Unicode qui emploie de un à quatre octets par caractère et reprend l'ASCII pour les lettres latines de base."}
    source: {name: "TERMIUM Plus", url: "https://www.btb.termiumplus.gc.ca/tpv2alpha/alpha-eng.html?lang=eng&srchtxt=Unicode%20Transformation%20Format", checked: "2026-11-04"}
  - id: xliff
    kind: abbreviation
    en: {short: "XLIFF", full: "XML Localization Interchange File Format", definition: "The OASIS standard file format for passing text to translate, and its translations, between tools."}
    fr: {short: "XLIFF", full: "format XLIFF (XML Localization Interchange File Format)", definition: "Format de fichier normalisé par OASIS pour échanger entre outils le texte à traduire et ses traductions."}
    source: {name: "OASIS, XLIFF Version 2.1", url: "https://docs.oasis-open.org/xliff/xliff-core/v2.1/os/xliff-core-v2.1-os.html", checked: "2026-11-04"}
  - id: locale
    kind: term
    en: {full: "locale", definition: "A language together with the conventions of a region for dates, numbers, sorting and similar items."}
    fr: {full: "paramètre régional", definition: "Langue associée aux conventions d'une région pour les dates, les nombres, le tri et d'autres éléments semblables."}
    source: {name: "TERMIUM Plus", url: "https://www.btb.termiumplus.gc.ca/tpv2alpha/alpha-eng.html?lang=eng&srchtxt=locale", checked: "2026-11-04"}
```

## Notes for the French review

- **iana.** TERMIUM Plus, subject Internet and Telematics: EN "Internet Assigned Numbers Authority" (IANA, correct); FR "IANA" (correct, masculine noun). No French full form exists, so the English name stays. The Vitrine linguistique search could not be read by an automated client.
- **icu, po.** Neither TERMIUM Plus nor the GDT has a record for these product and format names, as far as the TERMIUM open data shows. The owners' names are kept in both languages.
- **utf-8.** TERMIUM Plus gives "format transformé d'Unicode" for UTF (correct, masculine noun). The words "8 bits" are added to name UTF-8. Prefer the data types proposal if it cites a fuller French record.
- **xliff.** No TERMIUM record. The French full form follows the pattern of the `svg` entry, "format SVG (…)".
- **locale.** TERMIUM Plus, subject Computer Programs and Programming: EN "locale" (correct), FR "paramètre régional" (correct, masculine noun), with "paramètre de lieu" as a synonym. The GDT record, if any, was not checked, because its search page did not answer an automated client. Please check it by hand.
- **Language tag.** The pages write "étiquette de langue", the term of the W3C French translation of "Language tags in HTML and XML". It is not added as a defined term.

TERMIUM Plus records were read from the Translation Bureau open data release (extract dated February 2026, subject file Electronics and Informatics), because the TERMIUM search pages refuse automated clients.
The URLs above are the search pages a reviewer can open by hand.
