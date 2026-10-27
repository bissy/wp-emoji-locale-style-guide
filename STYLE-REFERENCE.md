# art-xemoji (Emoji locale): Working Style Reference

A draft shared reference for the WordPress Emoji locale, reverse-engineered from the
official glossary and existing translations.

- Drafted by: bissy (Tarosky), 2026-08-18
- Status: **draft for review**. Please correct anything that doesn't match your conventions
- Sources: official glossary + the `art-xemoji` translation of Captain Feed for YouTube

---

## 0. Source of authority

When two sources conflict, prefer the higher one.

| Priority | Source |
|---|---|
| 1 | [Official glossary](https://translate.wordpress.org/locale/art-xemoji/default/glossary/) (27 entries) |
| 2 | Existing coherent translations (e.g. Captain Feed for YouTube) |
| 3 | This document's additions (rationale noted for each) |
| — | ❌ The older "grammar-encoding" core translations (see §6) |

Context: `art-xemoji` is an experimental/testing locale. GTEs are assigned but the locale is
effectively unmaintained (most glossary entries date from 2016). Since there's no strict
authority, **what we establish becomes the de facto standard**, which is why a shared
reference seems worth writing down.

---

## 1. Official glossary (27 entries)

Transcribed as-is, with parts of speech and comments.

| Term | POS | Emoji | Comment |
|---|---|---|---|
| date | noun | 📅 | |
| down | adverb | ⬇️ | |
| edit | verb | ✏️ | |
| email | noun | 📧 | |
| enter | verb | ✅ | form submission |
| error | noun | ⛔️ | |
| feed | noun | 📃 | feed of data, not "to feed someone" |
| file | noun | 📁 | **folder emoji**, not 📄 |
| found | adjective | 🔎 | |
| here | adverb | 🎯 | |
| hide | verb | 🙈 | |
| invalid | adjective | 👎 | |
| key | noun | ⌨️ | **keyboard keys only** |
| key | noun | 🔑 | otherwise |
| keyboard | noun | ⌨️ | |
| link | noun | 🔗 | |
| mail | noun | 📧 | |
| media | noun | 🎶 | |
| no | adverb | 🙅 | |
| plugin | noun | 🔌 | |
| profile | noun | 📝😀 | **official precedent for compound emoji** |
| result | noun | 🎯 | |
| search | noun | 🔎 | |
| tag | noun | 🏷 | **no variation selector**: U+1F3F7 alone, not `🏷️` |
| theme | noun | 🎨 | |
| to | preposition | ➡️ | in the sense of "do x to cause y" |
| up | adverb | ⬆️ | |

### Emoji with more than one assigned meaning

Worth being aware of, since these need disambiguation by context.

| Emoji | Assigned to |
|---|---|
| 🔎 | found (adj) / search (noun) |
| 🎯 | here (adv) / result (noun) |
| 📧 | email / mail |
| ⌨️ | key (keyboard context) / keyboard |
| ✅ | enter (form submission) / done, complete (§3). select/selected uses ☑️ instead |

---

## 2. Conventions

Inferred from the `art-xemoji` translation of Captain Feed for YouTube.

### 2-1. Drop function words
`a` `the` `this` `that` `you` `will` `is` are omitted. Only content words get translated.

> ❌ `👉 ▶️ 🏭 ⬇️ 📤:` (This will produce the following output:)
> ✅ `⬇️📤:`

### 2-2. Compound concepts = unspaced emoji clusters
`👤📡` channel feed · `🌐🏢` Google · `⚡💾` cache · `🗑️🧼` uninstall · `🛠️💻` admin dashboard

### 2-3. Connectors
| Symbol | Use |
|---|---|
| `➡️` | to / for / leads to (the main connector) |
| `/` | or (literal half-width slash) |
| `➕` | and / with |
| `( )` | parenthetical clarification (used often) |
| `—` | **only when the source has one.** Captain Feed's `**label** — description` lines mirror the same punctuation in its English readme, so this is source-preservation rather than an invented device. Don't add one where the source has none |
| `,` | list separator |

### 2-4. Numbers
| Kind | Form | Example |
|---|---|---|
| Quantity, order, ratio | keycap digits | `3️⃣ ⚙️` · `9️⃣:1️⃣6️⃣` · `🪜1️⃣2️⃣3️⃣` |
| **Version numbers, identifiers** | **plain digits** | `🐘📜 5.6` · `v1.0.1` · `782px` |

### 2-5. Negation: `🚫` prefix
`🚫📝` no coding needed · `🚫👥` no user data · `🚫☑️📝🏷` no post type selected

### 2-6. Questions: `❓` at the front
English interrogatives (How / Where / What / Does) all collapse to `❓`, placed first.
No trailing `?`.

`❓🤝` (How can I contribute?) · `❓🆘` (Where can I get supported?)

### 2-7. Punctuation and spacing
No sentence-ending period. `,` `( )` `/` `:` are used.

**Between sentences, use `.`** and drop the final one:

```
🧩 ✂️ 📄🧩 ➡️ ✏️🆓. 🔮🔄 %s 📄🧩 🙅 ➡️ 🎯
                  ↑ separator          ↑ nothing at the end
```

The pending queue shows three habits here (`.`, `|`, and bare space). `.` wins
because it maps one-to-one onto the sentences in the source, so a reader can
follow which clause is which.

**Space between words, no space inside a compound.** This is not decoration:
spacing is the only thing marking word boundaries. `🧩✂️📄🧩` could be one
compound or three words; `🧩 ✂️ 📄🧩` can only be three.

### 2-8. Modifiers and variation selectors

**No skin tone modifiers.** Use the base emoji: `🙅` not `🙅🏻`, `👋` not `👋🏻`. Picking a
skin tone means representing one group of people in a locale that isn't tied to any.
The official glossary uses unmodified forms throughout.

**No variation selector on 🏷.** The glossary entry is U+1F3F7 alone. `🏷️` (with U+FE0F)
is a different byte sequence and shows up as an inconsistency in exports.

**Keycap digits are `DIGIT` + `U+FE0F` + `U+20E3`.** Core had four month names with the
last two reversed, which renders inconsistently across platforms.

### 2-9. No plural marking

The locale is declared `nplurals=1`, so singular and plural share one form, as in Japanese
or Korean. Don't reduplicate to mark number:

```
Tag  → 🏷        Tags  → 🏷        (not 🏷🏷)
Link → 🔗        Links → 🔗        (not 🔗🔗)
```

English marks plurals; most languages don't. Doubling the emoji reproduces an English
feature that the locale's own configuration says it doesn't have.

### 2-10. Preserved as-is (never emoji-fied)
- HTML tags: `<strong>` `<code>` `<a href="...">`
- Placeholders: `%s` `%1$s` `%link%` `%rel%`
- Code and function names inside `<code>`
- HTML attribute names / code identifiers: `href` `rel` `target`
- **Trailing spaces in the source string** (`e.g. ` → `👉 `). These matter because the UI
  concatenates the next element

---

## 3. Additions beyond the glossary

Rationale noted. All open to correction.

### WordPress concepts
| Term | Emoji | Note |
|---|---|---|
| post | 📝 | |
| page | 📄 | doesn't collide with file (📁) |
| post type | 📝🏷 | post + tag |
| permalink | 🔗♾️ | link + permanence |
| external | 🌍 | |
| URL | 🌐 | |
| content | 🗒️ | |
| section | 📑 | |
| settings / option | ⚙️ | core has `Settings → ⚙️⚙️` but that's the doubling style (§6) |
| attribute | 🔖 | |
| anchor element | ⚓ | kept distinct from 🔗 (link in general) |
| widget | 🧩 | |
| block / Gutenberg | 🧩 | from Captain Feed. Collides with widget, so context-dependent |
| archive | 🗄️ | |
| template | 📐 | set square: the mold a page is drawn from. Sits beside 📄 page and 📝 post. Page template `📄📐`, post template `📝📐` |
| template part | 📐🧩 | template + part. Was 📄🧩 until 2026-10-27, changed when template got its own emoji |
| future | 🔮 | the pending queue independently reached the same emoji |
| free / editable | 🆓 | `✏️🆓` for "fully editable" |
| editor | ✏️ | same as edit |
| repository | 📦🏬 | |
| developer | 👨‍💻 | ZWJ sequence; may split on some platforms |
| aspect ratio (a specific ratio) | shape + keycap ratio | `↔️ 1️⃣6️⃣:9️⃣` wide, `↕️ 9️⃣:1️⃣6️⃣` tall, `🟩 1️⃣:1️⃣` square. The ratio is what tells options apart; keycaps follow §2-4 |
| aspect ratio (the setting name) | ↔️↕️ | the label of the control, not a ratio itself. Was 📐 until 2026-10-27, which now belongs to template |
| news | 📰 | e.g. a "News" menu item. Not 🆕, which is the adjective new |
| user roles | 👤 + role | `👤🛠️` Administrator, `👤✏️` Editor, `👤✍️` Author, `👤🤝` Contributor, `👤👀` Subscriber. 👤 marks a person's role, so Editor the role and the editor screen (✏️) don't collide. Decided by poll in #polyglots-emoji (3–0) |
| list | 🧾 | items on a receipt. Was 📋 in the glossary until 2026-10-27; 📋 now belongs to paste/clipboard |
| paste / clipboard | 📋 | the clipboard icon editors use for paste |
| copy / duplicate | 👯 | making a twin; the two verbs are not distinguished (§2-1) |
| show / hide | 👁️ / 🙈 | show is the same as view |
| manage | ⚙️ | same as settings |
| scheduled | ⏲️ | `Scheduled Date → ⏲️📅` |
| recovery mode | ⛑️ | rescue helmet. ⚠️ no precedent found, my own guess. Write it with the variation selector (`⛑️`, not `⛑`) |

### Actions and states
| Term | Emoji | Note |
|---|---|---|
| select / selected | ☑️ | a ticked checkbox, which is literally what selecting is. ✅ is reserved for done/enter |
| manual | ✋ | |
| automatic | 🤖 | |
| install | 📥 | |
| activate / enable / active / On | 🟢 | verb and state are not distinguished, in line with §2-1. Continues the intent of core's earlier `on → 🟢🟢`. Also covers open/closed as a state (`Comments are open → 🟢`); 🔓 is avoided because 🔒 is taken by constant |
| deactivate / disable / inactive / Off / disabled | 🔴 | paired with 🟢, so the opposition is self-evident |
| activate a plugin | ⚡🔌 | kept as a compound; ⚡ is not used for `activate` on its own |
| done / complete | ✅ | shares ✅ with `enter` in the official glossary, which is close enough in meaning to live with. Kept distinct from 🟢: ✅ is "finished", 🟢 is "switched on" |
| click | 🖱️👆 | from Captain Feed |
| use | 🔧 | |
| override / update / change | 🔄 | |
| generate | 🏭 | ⚠️ no precedent found, my own guess |
| save | 💾 | |
| upload | 📤 | |
| delete / remove | 🗑️ | |
| new | 🆕 | |
| separate | ✂️ | |
| constant (PHP) | 🔒 | ⚠️ no precedent found, my own guess |
| release | 🚀 | **First release → `🚀🆕🌍`** (your convention, adopted) |
| fix | 🛠️🪛 | changelog convention |
| improvement | 📈 | changelog convention |
| add / new feature | 🆕 | changelog convention |

### Technical terms (translated rather than left in Latin)
| Term | Emoji | Rationale |
|---|---|---|
| GitHub | 🐙🐱 | Octocat |
| PHP | 🐘📜 | elePHPant + script |
| jQuery | 💲📜 | `$` + script |
| PDF | 📄📕 | |
| issue / ticket | 🎫 | |
| pull request | 🔀🙏 | merge + request |
| support (help) | 🆘 | |
| support (compatibility) | 👍 | also `Supports`, the features a post type supports |
| contribute | 🤝 | |
| documentation | 📖 | from your `📖⚙️` |
| fatal error | ‼️⛔️ | `‼️` intensifies the glossary's ⛔️ (error), since a fatal error is the severe case. ⚠️ no precedent found, my own guess |

### Proper nouns
| Term | Emoji | Note |
|---|---|---|
| Taro External Permalink | 🍠🌍🔗 | **plugin names get emoji-fied**, following `👨‍✈️📡📺`. Note this differs from most locales, where plugin names stay untranslated |
| Tarosky INC. | 🍠🌌 | Taro + sky |
| External Permalink (as a product name) | left in Latin | it's the plugin's display name in settings/editor headings |

### Weekdays → classical planets

Agreed in `#polyglots-emoji`, 2026-09-15. The Babylonian planetary week spread west into
Greek and Latin and east into Persian, Indian, Chinese and Japanese, so French `mardi` and
Japanese 火曜日 line up one to one. English is the outlier, having swapped in Norse gods.

The clinching argument came from a comment on the Polyglots blog: a weekday system with a
genuinely different origin probably isn't a seven-day week at all, and core can only render
seven-day weeks. So there is no tradition this excludes.

| Day | Full name | Abbreviation | Initial |
|---|---|---|---|
| Sunday | 🗓️☀️ | 🗓️☀️ | ☀️ |
| Monday | 🗓️🌙 | 🗓️🌙 | 🌙 |
| Tuesday | 🗓️🔥 | 🗓️🔥 | 🔥 |
| Wednesday | 🗓️💧 | 🗓️💧 | 💧 |
| Thursday | 🗓️🌳 | 🗓️🌳 | 🌳 |
| Friday | 🗓️⭐ | 🗓️⭐ | ⭐ |
| Saturday | 🗓️🌍 | 🗓️🌍 | 🌍 |

The 🗓️ prefix keeps ☀️ 💧 ⭐ 🌍 available for other strings, which matters when the glossary
has 27 words in it. Initials drop the prefix because they sit seven across in a narrow
calendar header, and the column context already says they are weekdays.

Note there is no Unicode or CLDR standard for weekday emoji, so this is our own convention.

### Months → season + number

| | | | | | |
|---|---|---|---|---|---|
| ⛄1️⃣ | ⛄2️⃣ | ☘️3️⃣ | ☘️4️⃣ | ☘️5️⃣ | 🌻6️⃣ |
| 🌻7️⃣ | 🌻8️⃣ | 🍂9️⃣ | 🍂1️⃣0️⃣ | 🍂1️⃣1️⃣ | ⛄1️⃣2️⃣ |

No space between the season and the digit. Same form for the genitive and abbreviated
variants, since emoji have neither case nor abbreviation.

The seasons are northern-hemisphere and we know it. The digit carries the meaning, so ⛄1️⃣
still reads as January in Buenos Aires in midsummer; the season emoji is decoration that
makes a list of months scannable.

⛄ rather than ❄️ and 🌻 rather than ☀️: ☀️ is Sunday now, and both ❄️ and ☀️ are wanted for
weather and light/dark strings. ⛄ and 🌻 have few other uses, so reserving them costs less.

Where these four come from: the macOS Japanese input method offers them as conversion
candidates for the season words. はる (spring) suggests ☘️, なつ (summer) 🌻, あき (autumn) 🍂,
ふゆ (winter) ⛄. Not universal (Google Japanese Input doesn't do this), but it means the
association already exists somewhere rather than being four emoji we picked ourselves.

Fitting, given emoji were designed in Japan to begin with. ☘️ also happens to work outside
that context: it's a March symbol in Ireland and the US through St Patrick's Day, landing
on roughly the same part of the year.

### AM / PM → 🌅 / 🌇

Not accurate: PM starts at noon, so 12:30PM renders as dusk. Chosen anyway because it reads
instantly, where the accurate form (`1️⃣2️⃣⬅️` / `1️⃣2️⃣➡️`, before noon / after noon) does not.

### Language names → flags
An excellent existing system in core: one language, one country flag. Worth completing.

Already in core (35): `Japanese → 🇯🇵` · `Italian → 🇮🇹` · `Ukrainian → 🇺🇦` · `Spanish → 🇪🇸` …

Added (14):

| Language | Flag | Note |
|---|---|---|
| Afrikaans | 🇿🇦 | |
| Arabic | 🇸🇦 | spoken across many states; Saudi Arabia is the conventional choice |
| Catalan | 🇦🇩 | Catalonia has no flag emoji and 🇪🇸 is taken by Spanish. Andorra is the one state where Catalan is the sole official language |
| English | 🇬🇧 | chosen over 🇺🇸 so it sits alongside Welsh 🏴󠁧󠁢󠁷󠁬󠁳󠁿 |
| Filipino | 🇵🇭 | |
| Finnish | 🇫🇮 | |
| Hebrew | 🇮🇱 | |
| Hindi | 🇮🇳 | |
| Indonesian | 🇮🇩 | |
| Korean | 🇰🇷 | |
| Malay | 🇲🇾 | |
| Persian | 🇮🇷 | |
| Swahili | 🇹🇿 | Tanzania, where Kiswahili is the national language |
| Welsh | 🏴󠁧󠁢󠁷󠁬󠁳󠁿 | subdivision flags exist in RGI for England, Scotland and Wales only |

No flag is used twice.

#### Deferred: languages without a usable flag

Three languages don't fit the one-language-one-flag system. They are **intentionally left
untranslated** rather than forced into a bad match:

| Language | Why |
|---|---|
| Galician | A regional language of Spain. Galicia has no flag emoji and 🇪🇸 is taken by Spanish. 🇵🇹 would be linguistically arguable but politically contested, and is taken by Portuguese |
| Tagalog | 🇵🇭 is assigned to Filipino, which is standardised Tagalog. Same state, so any flag would duplicate |
| Yiddish | A diaspora language, not tied to a state. 🇮🇱 is taken by Hebrew, and a religious symbol (✡️) would be inconsistent with how every other language is handled |

See open question 9 below.

---

## 4. URL localization

Only swap when a locale version actually exists, otherwise you create a dead link.

| Swap | Don't swap |
|---|---|
| `wordpress.org/plugins/{slug}/` → `emoji.wordpress.org/plugins/{slug}/` | GitHub, make.wordpress.org, hackerone |
| | `downloads.wordpress.org` |
| | vendor sites |

---

## 5. Strings that must NOT be translated

Particularly important for core.

| Kind | Action | Why |
|---|---|---|
| **Date format strings** | **copy verbatim** | `F j, Y`, `F j, Y g:i a`. Emoji-fying these breaks date output |
| `number_format_thousands_sep` | `,` | |
| `number_format_decimal_point` | `.` | |
| `html_lang_attribute` | `art-xemoji` | |
| `ltr` | `ltr` | |
| Font specs (`Noto Serif:400,...`) | copy verbatim | |
| **`on` / `off` config literals** | **copy verbatim** | Lowercase `on`/`off` with a msgctxt like `Comment number declension: on or off` are values WordPress compares in code, not display text. Core previously had `🟢🟢` / `🔴🔴` here, which was a functional bug. The capitalised display strings `On` / `Off` are separate entries and *do* get translated |
| `html_lang_attribute` | `art-xemoji` | |
| `words` (Word count type) | `words` | emoji are word-separated, so `words` is correct |

---

## 6. The older style in core (worth avoiding)

Core contains translations from an earlier approach that tried to encode grammar in emoji.
The results are unreadable, so I'd suggest not following them.

Markers: **doubled emoji** (`➡️➡️` `📄📄`), `💛` as a part-of-speech marker,
`⚫️⚫️` as sentence-end.

```
Display the total number of results in a query
  → 🕑👇 🤲👁️ ➡️➡️ #️⃣#️⃣💯💛 📦📦 ⬅️⬅️ 🗣️❓⚫️

Error while sideloading file %s to the server
  → 🤲🚶‍♂️➡️➡️📄📄%s➡️➡️🏡🏡🕑⏳❌💛⚫️⚫️
```

### Known defects in existing core translations

| Source | Existing | Problem | Status |
|---|---|---|---|
| Tall - 9:16 | 🚹 | unrelated to aspect ratio | fixed: `↕️ 9️⃣:1️⃣6️⃣` |
| Wide - 16:9 | 🌐 | same, and it occupies 🌐 which is wanted for URL | fixed: `↔️ 1️⃣6️⃣:9️⃣` |
| other aspect ratio names | 📏, 🏛️, 🖼️, 🖼️🎨👤, 🟩 | no ratio shown, so the options can't be told apart | fixed: shape + keycap ratio, see §3 |
| Scheduled | ⏲️ / 📅☑️ / 🗓 | three different translations for one term | fixed: unified on ⏲️ |
| Settings, blog and 7 more (9 strings) | ⚙️⚙️, ✍️✍️👥💛, … | doubling style (§2-9, §6) | fixed |
| Monday | ☀️1️⃣ | the rest of the week was still in English | fixed, see §3 |
| months | mixed spacing, `7️⃣📆` reversed, `🔟` for October | inconsistent within itself | fixed, see §3 |
| `on` / `off` config literals | 🟢🟢 / 🔴🔴 | emoji in values WordPress compares as text | fixed |
| four month names | `U+20E3` before `U+FE0F` | malformed keycaps | fixed |
| various | 🙅🏻, 👋🏻, 👎🏻 | skin tone modifiers | fixed |
| Tag Cloud, Label | 🏷️ | variation selector on 🏷 | fixed |

All known defects are now fixed. New ones go here as they turn up.

---

## 7. Suggested approach for core

Core is at **10%** (832 strings) as of 2026-10-20, up from 8% on 2026-09-15 and 3.2% before that.
The batches completed so far are all in the mechanical, low-risk categories:

| Batch | Category | Count |
|---|---|---|
| 1 | Date and time format strings (copied verbatim, including 4 with non-breaking spaces) | 20 |
| 2 | URLs (32 verbatim, 1 localized to `emoji.wordpress.org`) | 33 |
| 3 | Strings that break things if translated (HTML entities, numeric config values, tag delimiter, search stopwords, font preview string) | 16 |
| 4 | Language names → flags | 14 |
| 5 | Fixes to already-approved strings: `on`/`off` config literals that had emoji in them, four month names with malformed keycaps | 6 |
| 6 | Active/inactive states unified on 🟢 / 🔴 | 11 |
| 7 | Weekdays, all three forms | 21 |
| 8 | Months, all three forms | 36 |
| 9 | Fixes to approved strings: plural doubling and the older style (§2-9, §6) | 9 |
| 10 | Fixes to approved strings: aspect ratio names and Scheduled (§6) | 14 |
| 11 | UI labels that map one-to-one onto a glossary term | 135 |
| 12 | Previously held terms: news, supports, manual, comments open, aspect ratio | 6 |
| 13 | User roles, after the poll | 5 |
| 14 | Template: new 📐, template part and aspect ratio moved to match, plus template labels | 24 |
| 15 | Copy, paste, list, show, hide, manage: list moved to 🧾, plus labels | 34 |

A separate pass over the 302 pending suggestions fixed 11 of them in place (glossary
mismatches, variation selectors, plural doubling, skin tone modifiers) rather than
rejecting them.

Remaining breakdown:

| Priority | Category | Count | Approach |
|---|---|---|---|
| ✅ | Date format strings | 20 | done: copied verbatim |
| ✅ | URLs | 33 | done: see §4 |
| 🥈 | 1–3 word UI labels | ~3,745 | where emoji works best |
| 🥉 | 4–8 word phrases | ~1,668 | possible, needs care |
| ⚠️ | Contains `%s` / HTML | ~1,313 | placeholder integrity is critical |
| ❌ | **9+ words** | ~1,583 | **suggest leaving alone**, since every unreadable example in §6 is from here |

### Review priority

With most of core still untranslated, effort should go where it changes what users see.
When reviewing suggestions or existing translations, sort issues into three tiers:

| Tier | What | Examples | Action |
|---|---|---|---|
| 1. Fix now | Breaks output or misleads the reader | missing or altered placeholders (`%s`, `###DEBUG###`), another language mixed in (`Previous → Anterior`), English copied verbatim, a meaning unrelated to the source (`Tall - 9:16 → 🚹`) | reject, or fix before approving |
| 2. Align early | Contradicts the glossary or §3 | `Video → 🎞` (glossary: 🎬), `URL → 🔗` (glossary: 🌐), plural doubling (§2-9) | fix when touched; the longer these stay, the more strings repeat them |
| 3. Leave for later | Equivalent wording that already reads correctly | `⌛️` vs `⏳`, a different but understandable compound | approve as-is; don't spend review time swapping one valid choice for another |

Tier 1 is not a matter of taste. A missing placeholder silently drops content: the fatal
error email, for instance, loses its WordPress, theme, plugin and PHP version lines if
`###DEBUG###` is gone, because core fills them in with `str_replace`.

### Systematic clusters worth targeting
- Language names → flags (done for all but three; see §3)
- Weekdays and months (done, see §3)
- Percentages (`100% → 💯` exists; `25%` `50%` `75%` could follow)

---

## 8. Open questions (would love your input)

These are conventions I couldn't derive from the glossary or existing translations, so I
guessed. Corrections very welcome.

| # | Question | My current guess |
|---|---|---|
| 1 | **What does trailing `❗` mean?** I saw `❓🔌 🧩❗` (Does plugin work with blocks?) but couldn't work out whether it marks "can/does", or is just emphasis | not used |
| 2 | Is `⏰` acceptable for "when" / "if"? | using it |
| 3 | Is `〰️` acceptable for "and so on / etc."? | using it |
| 4 | Is `🏭` acceptable for "generate"? | using it |
| 5 | Is `🔒` acceptable for "constant"? | using it |
| 6 | ~~How should weekdays and months be systematised?~~ **Settled.** Planetary weekdays and season+number months, see §3 | resolved |
| 7 | Are plugin names emoji-fied, or left in Latin? I followed `👨‍✈️📡📺` and did `🍠🌍🔗` | emoji-fied |
| 9 | **How should languages without a state be handled?** Galician, Tagalog and Yiddish have no usable flag (see §3). Options: leave untranslated, allow a flag to be shared, or use a non-flag emoji | left untranslated |
| 8 | Should we fix the defects in §6 before adding new strings, or leave them? | proposed: tier 1 and 2 defects first, tier 3 later (see §7, Review priority) |
| 10 | **How should user roles look?** Currently mixed: Administrator in English, Editor `👤✍`, Author `😌✍`, Contributor and Subscriber untranslated. Options: person + role (`👤🛠️` `👤✏️` `👤✍️` `👤🤝` `👤👀`), single emoji (`👑` `✏️` `✍️` `🤝` `👀`), or extend the existing faces resolved: person + role, by poll (3 votes to 0). See §3 |
