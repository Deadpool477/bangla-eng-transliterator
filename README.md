# Bangla to Roman Transliterator

A single-file web page that converts Bangla (বাংলা) script into Roman letters, following how the words are actually pronounced. It uses the same spelling convention commonly used for Hindi in English letters (`a` / `aa`, `i` / `ee`, `u` / `oo`), with optional dotted letters (ṭ ḍ ṇ ś ṣ ṅ ñ ṛ) in the style used for Sanskrit-derived scripts.

No build step, no dependencies, no server. Open `index.html` in a browser.

## Features

- Live conversion as you type or paste
- Two styles: **Pronunciation** (অ is `o`, as in কলম = *kolom*) and **Hindi-style** (অ is `a`, *kalam*)
- Optional dotted letters so look-alike letters stay distinct (ত/ট, দ/ড, ন/ণ, শ/ষ, ঙ/ঞ, ড়/ঢ়)
- Clickable reference tables for vowels, vowel signs, consonants and conjuncts; tapping a letter inserts it into the input box
- One-tap copy of the result
- Works on desktop and mobile, with light and dark themes

## Spelling scheme

| Bangla | Roman | Sounds like |
|---|---|---|
| আ / া | aa | father |
| ই / ি | i | city |
| ঈ / ী | ee | sheep |
| উ / ু | u | put |
| ঊ / ূ | oo | moon |
| এ / ে | e | day |
| ঐ / ৈ | oi | boy |
| ও / ো | o | go |
| ঔ / ৌ | ou | house |
| অ | o (or `a` in Hindi-style) | hot |
| অ্যা | ae | cat |

With dotted letters on: ট ṭ, ঠ ṭh, ড ḍ, ঢ ḍh, ণ ṇ, শ ś, ষ ṣ, ঙ ṅ, ঞ ñ, ড় ṛ, ঢ় ṛh, ং ṃ, ঃ ḥ. Chandrabindu (ঁ) is written `~`.

## Pronunciation rules applied

- A consonant at the end of a word has no vowel: নাম = *naam*. A word ending in a conjunct keeps it: বন্ধ = *bondho*.
- ্য and ্ব after a consonant double it: সত্য = *shotto*, বিশ্ব = *bishsho*. At the start of a word, ্য sounds like `ae`.
- স is `s` before ক খ ট ঠ ত থ প ফ (স্টেশন = *steshon*) and `sh` elsewhere.
- ক্ষ is `kh` at the start of a word and `kkh` elsewhere; ক্ষ্ম drops the ম (লক্ষ্মী = *lokkhee*). জ্ঞ is `gy` or `gg`.
- র্য and র্ব do not double: সূর্য = *shoorjo*, সর্ব = *shorbo*.
- হ্ন, হ্ম, হ্ল swap to `nh`, `mh`, `lh`: চিহ্ন = *chinho*.
- ত্ম, দ্ম, গ্ম double the first letter: পদ্ম = *poddo*.
- ঃ doubles the next consonant: দুঃখ = *dukkho*, নিঃস্ব = *nishsho*.

## Limitations

This is rule-based, with no dictionary, so it follows regular spelling-to-sound patterns.

- Words with irregular vowel colouring (for example এক said as *aek*) come out in their regular form.
- Vowel harmony, where a neighbouring vowel changes how a অ or ও is pronounced, is not modelled.
- A very small exception list exists (currently শুভ = *shubho*). Pull requests with more words are welcome.

## Run locally

```bash
git clone https://github.com/Deadpool477/bangla-transliterator.git
cd bangla-transliterator
# then open index.html in your browser
```

The page loads fonts from Google Fonts. Offline, it falls back to your system's Bengali font.

## Host it on GitHub Pages

1. Push the repo with `index.html` in the root.
2. Go to **Settings → Pages**.
3. Under **Branch**, choose `main` and `/ (root)`, then **Save**.
4. After about a minute the page is live at `https://Deadpool477.github.io/bangla-transliterator/`.

## Contributing

Found a word that comes out wrong? Open an issue with the Bangla word, what the page gave, and what it should be. The rules live in the `cluster()` and `word()` functions near the bottom of `index.html`.

## License

Add a license of your choice (MIT is a common default).
