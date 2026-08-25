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
| ✅ | enter (form submission), and in §3 also select/selected |

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
| `—` | introduces an explanation |
| `,` | list separator |

### 2-4. Numbers
| Kind | Form | Example |
|---|---|---|
| Quantity, order, ratio | keycap digits | `3️⃣ ⚙️` · `9️⃣:1️⃣6️⃣` · `🪜1️⃣2️⃣3️⃣` |
| **Version numbers, identifiers** | **plain digits** | `🐘📜 5.6` · `v1.0.1` · `782px` |

### 2-5. Negation: `🚫` prefix
`🚫📝` no coding needed · `🚫👥` no user data · `🚫✅📝🏷` no post type selected

### 2-6. Questions: `❓` at the front
English interrogatives (How / Where / What / Does) all collapse to `❓`, placed first.
No trailing `?`.

`❓🤝` (How can I contribute?) · `❓🆘` (Where can I get supported?)

### 2-7. Punctuation
No sentence-ending period. `,` `( )` `—` `/` `:` are used.

### 2-8. Preserved as-is (never emoji-fied)
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
| editor | ✏️ | same as edit |
| repository | 📦🏬 | |
| developer | 👨‍💻 | ZWJ sequence; may split on some platforms |

### Actions and states
| Term | Emoji | Note |
|---|---|---|
| select / selected | ✅ | collides with `enter` in the glossary. **Not** extended to active/enable, which would have made it a third meaning |
| manual | ✋ | |
| automatic | 🤖 | |
| install | 📥 | |
| activate / enable / active / On | 🟢 | verb and state are not distinguished, in line with §2-1. Continues the intent of core's earlier `on → 🟢🟢` |
| deactivate / disable / inactive / Off / disabled | 🔴 | paired with 🟢, so the opposition is self-evident |
| activate a plugin | ⚡🔌 | kept as a compound; ⚡ is not used for `activate` on its own |
| done / complete | ✔️ | core already used this. Kept distinct from 🟢: ✔️ is "finished", 🟢 is "switched on". Core had `Activate %s → ✔ %s`, which was changed to `🟢 %s` for consistency |
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
| support (compatibility) | 👍 | |
| contribute | 🤝 | |
| documentation | 📖 | from your `📖⚙️` |

### Proper nouns
| Term | Emoji | Note |
|---|---|---|
| Taro External Permalink | 🍠🌍🔗 | **plugin names get emoji-fied**, following `👨‍✈️📡📺`. Note this differs from most locales, where plugin names stay untranslated |
| Tarosky INC. | 🍠🌌 | Taro + sky |
| External Permalink (as a product name) | left in Latin | it's the plugin's display name in settings/editor headings |

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
| Keycap digits | `DIGIT` + `U+FE0F` + `U+20E3` | core had four month names with the sequence reversed (`U+20E3` before `U+FE0F`), which renders inconsistently |

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

| Source | Existing | Problem |
|---|---|---|
| Tall - 9:16 | 🚹 | unrelated to aspect ratio |
| Wide - 16:9 | 🌐 | same |
| Monday | ☀️1️⃣ | Tuesday–Sunday still in English (system incomplete) |
| Scheduled | ⏲️ / 📅☑️ | two different translations for one term |
| blog / blogs | ✍️✍️👥💛 | identical for singular and plural |

These might be worth fixing before adding new strings.

---

## 7. Suggested approach for core

Core is at **4.3%** (346 / 8,109) as of 2026-08-19, up from 3.2%.
The batches completed so far are all in the mechanical, low-risk categories:

| Batch | Category | Count |
|---|---|---|
| 1 | Date and time format strings (copied verbatim, including 4 with non-breaking spaces) | 20 |
| 2 | URLs (32 verbatim, 1 localized to `emoji.wordpress.org`) | 33 |
| 3 | Strings that break things if translated (HTML entities, numeric config values, tag delimiter, search stopwords, font preview string) | 16 |
| 4 | Language names → flags | 14 |

Remaining breakdown:

| Priority | Category | Count | Approach |
|---|---|---|---|
| ✅ | Date format strings | 20 | done: copied verbatim |
| ✅ | URLs | 33 | done: see §4 |
| 🥈 | 1–3 word UI labels | ~3,745 | where emoji works best |
| 🥉 | 4–8 word phrases | ~1,668 | possible, needs care |
| ⚠️ | Contains `%s` / HTML | ~1,313 | placeholder integrity is critical |
| ❌ | **9+ words** | ~1,583 | **suggest leaving alone**, since every unreadable example in §6 is from here |

### Systematic clusters worth targeting
- Language names → flags (done for all but three; see §3)
- Weekdays and months (`Monday → ☀️1️⃣` exists but the system is incomplete, so it needs a design)
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
| 6 | **How should weekdays and months be systematised?** The existing core attempt (`Monday → ☀️1️⃣`, `January → ❄️1️⃣`, but `July → 🗓️🗓️7️⃣`) is inconsistent and incomplete | undecided |
| 7 | Are plugin names emoji-fied, or left in Latin? I followed `👨‍✈️📡📺` and did `🍠🌍🔗` | emoji-fied |
| 9 | **How should languages without a state be handled?** Galician, Tagalog and Yiddish have no usable flag (see §3). Options: leave untranslated, allow a flag to be shared, or use a non-flag emoji | left untranslated |
| 8 | Should we fix the defects in §6 before adding new strings, or leave them? | undecided |
