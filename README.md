# latin-pls

[![License](https://img.shields.io/badge/License-See%20LICENSE-blue.svg)](./LICENSE)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

Public Latin pronunciation lexicons in the [W3C Pronunciation Lexicon Specification (PLS) 1.0](https://www.w3.org/TR/pronunciation-lexicon/) format, intended for text-to-speech (TTS) systems.

## What this project is

This repository collects pronunciation lexicons for Latin words and phrases using standards-compliant PLS XML files (`.pls`).  
The main goal is to improve pronunciation quality in TTS engines that can consume external lexicons, such as Azure Speech.

## Current status 🚧

This project is a work in progress.

- Only one lexicon has been started so far: an **Ecclesiastical (Italianate)** pronunciation lexicon.
- The file currently lives at `lexicons/ecclesiastical.pls`.
- More pronunciation schemes and broader vocabulary coverage are planned, and community contributions are encouraged.

## Why PLS 📘

PLS provides a portable, structured way to define pronunciation entries (`lexeme` values with `grapheme` and `phoneme` forms).  
By following the W3C specification, these lexicons are easier to reuse across tools and pipelines that support PLS.

## Using these lexicons with Azure Speech 🔊

Azure Speech supports referencing a public custom lexicon via SSML using the `<lexicon>` element.  
Microsoft documents this here: [Pronunciation with SSML - custom lexicon examples](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/speech-synthesis-markup-pronunciation#custom-lexicon-examples).

To use a lexicon from this repository:

1. Host the `.pls` file at a publicly accessible URL (for example, GitHub raw URL, Blob storage, or another public endpoint).
2. Reference that URL in SSML with `<lexicon uri="..."/>`.

Example:

```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xml:lang="it-IT">
  <voice name="it-IT-IsabellaNeural">
    <lexicon uri="https://example.com/lexicons/ecclesiastical.pls"/>
    Ave Maria, gratia plena.
  </voice>
</speak>
```

## Repository layout

- `lexicons/` - PLS lexicon files
- `lexicons/ecclesiastical.pls` - Initial Ecclesiastical (Italianate) Latin lexicon

## Contributing 🤝

Contributions are very welcome. If you care about Latin pronunciation quality in speech synthesis, this project can use your help.

If you contribute entries, please aim to keep:

- Valid PLS 1.0 XML structure
- Consistent phoneme notation within a lexicon
- Reasonable grapheme coverage (for example, capitalization variants where helpful)

## License

See `LICENSE`.
