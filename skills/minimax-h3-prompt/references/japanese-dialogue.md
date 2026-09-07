# Japanese Dialogue and Lip-Sync

Apply this guide to every Japanese line that MiniMax H3 will speak, sing, whisper, shout, or narrate. These rules override the upstream instruction to preserve spoken text verbatim because they are the user's permanent pronunciation preference.

## Normalize Only Audible Text

Normalize the content that will actually be vocalized. Do not change:

- `<d>`, `<scenetrans>`, `<cutoff>`, `[Japanese]`, speaker IDs, shot labels, or field names
- reference tags such as `<Picture 1>`, `<Video 1>`, `@image1`, and `画像1`
- URLs, file names, paths, model IDs, API names, or other non-spoken identifiers
- exact on-screen text, captions, labels, logos, or quoted source text unless the same string is also spoken

Inside a `<d>` block, include only the language tag and the normalized words the character actually says.

## Required Transformations

### Difficult Kanji to Hiragana

Convert rare, technical, literary, irregularly read, or contextually ambiguous kanji to hiragana when a speech model may misread them. Also convert proper-name readings when pronunciation is not obvious.

Keep common, unambiguous kanji when they improve readability. Do not mechanically convert the whole sentence to hiragana. Preserve the original meaning, word order, tone, and punctuation.

Examples:

| Before | After |
| --- | --- |
| `躊躇しないで。` | `ちゅうちょしないで。` |
| `今日の進捗を共有します。` | `きょうの進ちょくを共有します。` |
| `彼は暫く黙った。` | `彼はしばらく黙った。` |

When a reading is uncertain, ask the user or include the intended reading in hiragana. Do not guess a person's name.

### Numbers to Arabic Numerals

Write every spoken numeric value with Arabic numerals, not kanji numerals. Use separators and punctuation natural for the target line.

| Before | After |
| --- | --- |
| `二千年` | `2,000年` |
| `一九二回` | `192回` |
| `三人で二時間待った` | `3人で2時間待った` |
| `令和八年九月七日` | `令和8年9月7日` |

Do not convert words that only look numeric but are part of a fixed non-numeric expression. Keep version strings, URLs, IDs, and reference labels unchanged when they are not spoken.

### Spoken English to Katakana

Render every English word, brand name, acronym, initialism, and borrowed phrase that will be spoken in katakana according to the intended pronunciation.

| Before | After |
| --- | --- |
| `AI` | `エーアイ` |
| `OpenAI` | `オープンエーアイ` |
| `YouTube` | `ユーチューブ` |
| `SNS` | `エスエヌエス` |
| `coffee break` | `コーヒーブレイク` |

When a product or person's preferred pronunciation is unclear, ask instead of inventing one. Leave English unchanged when it is visible text but not spoken.

## H3 Speech Placement

Define the speaking subject and stable ID outside the dialogue block, then place the normalized line inside it:

```text
The presenter with a clear, measured voice (S1) physically speaks with natural lip movement: <d>[Japanese] きょうは、エーアイの進ちょくを192回目として共有します。</d>
```

For an on-screen speaker, explicitly request natural lip movement and keep the mouth visible long enough for the line. After the line, describe the mouth closing before a new expression or cut when timing matters.

For voiceover, label it as off-screen and state that visible characters' lips remain closed. Do not ask for lip-sync on off-screen narration.

Keep a line short enough to fit the assigned time at a natural speaking rate. If it cannot fit, shorten the wording, extend the duration, or split it across planned shots without changing speaker IDs.

## Final Read-Aloud Check

Before returning the prompt, read each audible line mentally from left to right and verify:

1. Every difficult or ambiguous kanji has a clear hiragana reading.
2. No spoken number remains in kanji.
3. No spoken English remains in Latin letters.
4. Punctuation creates natural pauses without changing meaning.
5. The line fits the available seconds and the correct speaker.
6. Non-spoken tags, IDs, URLs, and visible text remain untouched.
