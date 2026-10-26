# 🛡️ Powerful Homoglyph Attack Engine (Decensor)

A lightweight, zero-dependency, client-side text obfuscation tool that leverages multi-script Unicode homoglyphs (Cyrillic, Latin, Greek, Coptic, and mathematical symbols) to defeat keyword blacklists, automated regex scanners, and NLP moderation models.

---

## ⚡ Features

- **Bidirectional Mirroring**: Paste mixed Ukrainian, English, or any script into either field — the counterpart field transforms automatically.
- **Dual Threat-Level Modes**:
  - **Stealth Mode (Default)**: Employs 100% visually indistinguishable glyphs. Undetectable to the naked eye while disrupting raw character-level tokenizers (Byte-Pair Encoding).
  - **Combat Mode (Aggressive)**: Unlocks expanded Unicode domains — ancient Greek (`α`, `β`, `Γ`, `Δ`), Coptic (`ⲇ`), mathematical set theory symbols (`∈`), and rare phonetic/regional alphabets (`һ`, `ԁ`, `ӏ`, `ԝ`, `ԛ`). Designed for total pattern destruction.
- **Zero Dependencies**: Pure HTML5, CSS3, and Vanilla JavaScript in a single standalone file.
- **100% Private & Client-Side**: No telemetry, no API calls, no backend. Works entirely inside your browser cache or offline.
- **Mobile-Optimized (Single-Screen UI)**: Responsive layout utilizing modern `100dvh` viewport handling without unwanted page scrolling.

---

## 🔬 How It Works

Automated moderation platforms (Meta, TikTok, X, YouTube, Telegram bots) rely heavily on string matching, regex filters, and NLP tokenizers (like WordPiece or BPE). 

When a standard English or Ukrainian word is passed through this engine:
1. Visually identical or near-identical Unicode code points replace standard characters.
2. The sequence signature is shattered into distinct Unicode byte ranges.
3. NLP tokenizers fail to resolve known dictionary stems, causing censorship algorithms to ignore the string.
4. Human cognitive reading remains seamless due to gestalt visual perception.

### Mode Comparison Matrix

| Target Character | Stealth Mode Glyph | Combat Mode Glyph |
| :---: | :---: | :---: |
| **`а` (Cyrillic)** | `a` (U+0061 Latin) | `α` (U+03B1 Greek Alpha) |
| **`h` (Latin)** | *Excluded (anti-artifact)* | `һ` (U+04BB Cyrillic Shha) |
| **`s` (Latin)** | `ѕ` (U+0455 Cyrillic Dze) | `ѕ` (U+0455 Cyrillic Dze) |
| **`d` (Latin)** | *Excluded (anti-artifact)* | `ԁ` (U+0501 Cyrillic Komi De) |
| **`k / к`** | *Excluded (font ascender)* | `k` ↔ `к` (Full cross-swap) |
| **`є` (Cyrillic)** | *Excluded* | `∈` (U+2208 Element of) |
| **`w` (Latin)** | *Excluded* | `ԝ` (U+051D Cyrillic We) |
