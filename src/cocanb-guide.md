# Cocánb Guide

## Translation Rules

For the purpose of demonstration, the following sentence will be translated:

```
The quick brown fox jumps over the lazy dog.
```

**Step 1:** Remove the last letter of each word:

```
Th quic brow fo jump ove th laz do.
```

**Step 2:** To the end of the sentence, add the string `non`. (referred to as the "separator-`non`") Then, for each word of the initial sentence, add the previously removed letter as well as a character (or characters) corresponding to the length of the initial word. (e. g. if the word was one character long, `a` is to be added, and if the word was two characters long, `b` and etc...) In the case of a word that was longer than 26 characters, add the character `å` as many times as needed before the length character: (e. g. if the word was 27 characters long, `åa` is to be added, if the word was 28 characters long, `åb` is to be added, and if the word was 53 characters long, `ååa` is to be added.)

```
Th quic brow fo jump ove th laz do non ec ke ne xc se rd ec yd ge.
```

**Step 3:** Remove the spaces:

```
Thquicbrowfojumpovethlazdononeckenexcserdecydge.
```

**Step 4:** Add spaces, punctuation (cf. [below](#rules-regarding-punctuation)), and diacritics as you see fit. You may also alter the capitalisation of individual letters, but the first letter of the sentence shall remain capitalised: (Referred to as "Decoration" in this document)

```
Thquîc browföjum povethlàz dóno necken exčserd ecydğe.
```

## Additional Rules

### Rules regarding the separator

It is crucial that the separator-`non` can be determined from the translated sentence alone. This means:
- You may not add diacritics to the separator-`non` (regardless of the existence of further `non`s) when translating. However, you may add spaces and permitted punctuation between the letters of the separator.
- Any other `non` must contain diacritics. This also implies if a substring like `nonon` consisting of the separator is formed, this must be decorated accordingly to distinguish the separator.

For example:
- `anonymous` becomes `anôným ounonsi`
- `not` becomes `nônontč`

### Rules regarding punctuation

Texts are translated sentence-by-sentence, so terminal punctuation shall be left as-is.

If a sentence has substrings within quotes or brackets, they shall be translated recursively. For example:
- `I said "hello" to you.` becomes `Saí "hellnonoe" työn oniád dobûc.`

Otherwise, punctuation is ignored during translation and can be added during decoration.

### Rules regarding numbers

If a word is entirely numeric, it is to be left in the sentence without translation. For example:
- `I have 27 apples.` becomes `Háv 27 ap pléno niaècsf.`

If numbers, as digits, are embedded into a word, the number is to be treated as a single letter. For example:
- `html5` becomes `html non 5e`
- `help2man` becomes `help2 manonnh`

### Conventions

#### Cocánb Convention

If the substring `cocan` appears in the translated text, decorate like `Cocán` and do not split the substring.
