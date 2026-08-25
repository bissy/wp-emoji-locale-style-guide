# Reviewing the Waiting queue for `art-xemoji` core

A read-through of the 304 pending suggestions on WordPress core, written up for discussion
in `#polyglots-emoji` before anything is approved or rejected in bulk.

- Reviewed: 2026-08-23
- Source: https://translate.wordpress.org/projects/wp/dev/art-xemoji/default/?filters%5Bstatus%5D=waiting
- Reviewer: bissy (core PTE for `art-xemoji`)

**Nothing has been rejected yet except three strings that would break WordPress if approved
(§1). Everything else is listed here for us to decide together.**

---

## Summary

| Category | Count | Suggested handling |
|---|---|---|
| §1 Would break WordPress | 3 | **rejected** |
| §2 Source text left untranslated | 67 | discuss |
| §3 Conflicts with the existing weekday/month system | 19 | discuss |
| §4 Glossary violations | 7 | discuss (fixable) |
| §5 Unreadable or padded with emoji | ~15 | discuss |
| §6 Plausible, worth approving | ~190 | spot-check, then approve |

The queue has been sitting since around 2016, so most of this predates any shared
conventions. None of it is anyone's fault, and none of these notes are a criticism of the
people who submitted them.

---

## 1. Would break WordPress (rejected)

These three are not style questions. Approving them changes behaviour.

| msgid | Suggestion | Problem |
|---|---|---|
| `words`<br>`msgctxt: Word count type. Do not translate!` | `🔤 📝 💬` | WordPress compares this value in code against `words`, `characters_excluding_spaces` or `characters_including_spaces`. Anything else breaks word counting. The source comment says *Do not translate* |
| `The blocks will be separated from the original template part … Future changes to the %s template part will not apply here.` | `🧱✂️📄(%s) ➜ ✏️🛠️✅ \| 🔮🔄📄(%s) ❌➡️📍` | The source has one `%s`; the suggestion has two. A duplicated placeholder throws at runtime |
| `Previous`<br>`msgctxt: datepicker: navigate to previous month` | `Anterior` | Spanish, submitted to the wrong locale |

Related: core itself had the same class of bug in already-approved strings, which I fixed
separately: `on → 🟢🟢` and `off → 🔴🔴` were sitting in the lowercase `on`/`off` config
literals. Worth keeping an eye out for.

---

## 2. Source text left untranslated (67)

The suggestion is byte-identical to the English source. Examples:

```
Display date          → Display date
Display author        → Display author
Edit gallery          → Edit gallery
Discussion            → Discussion
Separator             → Separator
Shortcode             → Shortcode
media                 → media
photo                 → photo
Legacy Widget         → Legacy Widget
Both registration and last updated dates must be valid dates.  → (unchanged)
```

Some of these are translatable straight from the glossary (`media → 🎶`), so they don't look
like deliberate decisions to leave them in Latin.

**A handful arguably should stay as-is**, which is why I'd rather not bulk-reject:

| msgid | Context | Why it might be correct |
|---|---|---|
| `a` | Lowercase letter A | it *is* the letter |
| `M` / `L` | size labels (medium / large) | initials; no emoji equivalent |
| `*` | character identifying required fields | a symbol already |
| `%1$s %2$d` | month name + 4-digit year | placeholders only |

**Question for the channel:** do we reject "source copied verbatim" as a category, or leave
them pending? Rejecting 60+ suggestions from a previous contributor felt like something to
agree on first.

---

## 3. Conflicts with the existing weekday/month system (19)

Core already has approved translations for some months. The pending suggestions use a
different scheme, so approving them would leave two systems side by side.

| Month | Already approved | Pending suggestion |
|---|---|---|
| January | ❄️1️⃣ | ☃️1️⃣ |
| February | ❄️2️⃣ | 🌨️2️⃣ |
| March | *(none)* | 🎆3️⃣ |
| April | 🌸4️⃣ | 🎉4️⃣ |
| May | 🌸5️⃣ | 🌹5️⃣ |
| June | ☀️ 6️⃣ | 🍒 6️⃣ |
| July | 7️⃣📆 | 🔥7️⃣ |
| August | ☀️ 8️⃣ | 🌴 8️⃣ |
| September | 🍂 9️⃣ | 📚 9️⃣ |
| October | 🍂 🔟 | ⚖️ 🔟 |
| November | 🍂 1️⃣1️⃣ | 🌧️ 1️⃣1️⃣ |
| December | ❄️1️⃣2️⃣ | 🍉1️⃣2️⃣ |

Two different ideas are in play: **season** (approved: ❄️ winter, 🌸 spring, ☀️ summer,
🍂 autumn) versus **month-specific symbol** (pending: 🎆 fireworks for March, 🍒 cherries for
June, 📚 books for September).

The weekdays are a bigger problem:

| Weekday | Already approved | Pending suggestion |
|---|---|---|
| Sunday | *(none)* | ☀️ 2️⃣ |
| Monday | ☀️1️⃣ | ☕3️⃣ |
| Tuesday | *(none)* | 🥗 4️⃣ |
| Wednesday | *(none)* | 🛍️5️⃣ |
| Thursday | *(none)* | 🍽️ 6️⃣ |
| Friday | *(none)* | 🌳 7️⃣ |
| Saturday | *(none)* | 📚 1️⃣ |

**The numbers don't line up with any ordering I can see.** Saturday is 1️⃣, Sunday 2️⃣,
Monday 3️⃣. If that's ISO-week-adjacent it doesn't match, and it collides with the approved
`Monday → ☀️1️⃣`.

The existing approved set is also incomplete and internally inconsistent: `July → 7️⃣📆` puts
the digit first where every other month puts the symbol first, `October → 🍂 🔟` uses 🔟
where November uses `1️⃣1️⃣`, and the space between symbol and digit comes and goes.

Also note the season problem: a season-based scheme assumes the northern hemisphere.

**Questions for the channel:**
1. Season-based or month-symbol-based?
2. Symbol first or digit first, and space or no space?
3. `🔟` or `1️⃣0️⃣` for ten?
4. What ordering should weekday digits use, if any?
5. Do we re-do the already-approved months to match whatever we pick?

This feels like the first thing worth settling, since dates appear everywhere.

---

## 4. Glossary violations (7)

Close but not glossary-compliant. All easily fixed rather than rejected.

| msgid | Suggestion | Glossary says |
|---|---|---|
| `Close search` | `🔍❌` | `search → 🔎` (different codepoint from 🔍) |
| `Move up` | `⤴️` | `up → ⬆️` |
| `Move down` | `⤵️` | `down → ⬇️` |
| `Add Media` | `➕💿` | `media → 🎶` |
| `You do not have permission to install plugins.` | `🔒🚫🧩📦⬇️…` | `plugin → 🔌`; 🧩 is already used for block/widget |
| `Plugins cannot be installed here…` | `🧩📦🚫⬇️…` | same |
| `Tag` / `Tag:` | `🏷️` | `tag → 🏷`, **without** the variation selector (U+1F3F7 alone) |

The 🏷 / 🏷️ distinction is easy to get wrong. I shipped one myself before catching it.

Separately, `Disconnect → 🔌❌` reuses 🔌 (plugin) for "disconnect". Readable, but it means
🔌 no longer only means *plugin*. Worth a decision.

---

## 5. Unreadable or padded with emoji (~15)

Two patterns here.

**Emoji padding.** Several near-synonymous emoji in a row where one would do:

```
Uncategorized  → 🗃️ 🗂️ 🧩 📂
Document       → 📑 📜 📃 📄
Preview        → 👁️🔍📄
```

**The older grammar-encoding style.** Doubled emoji, `💛` as a part-of-speech marker,
`⚫️⚫️` as sentence-end:

```
New version available.  → 🕑👇🆕🆕 📦📦🐛🦋 ✅✅⚫️⚫️
```

There are already approved strings in core in this style (e.g. `Display the total number of
results in a query → 🕑👇 🤲👁️ ➡️➡️ #️⃣#️⃣💯💛 📦📦 ⬅️⬅️ 🗣️❓⚫️`). I can't read them, but I
also don't want to unilaterally declare a previous contributor's system wrong.

And one that seems to have given up on meaning entirely:

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pra…
  → 😀😂😚😂🙂😐🌜😴😈🤢🤬😴🌜🤢😤😴🌚😪🙊☠️🤠🤖🤥😇👹👐💪🙌🤛🙌🦷
```

(Placeholder text, so arguably anything goes. Still.)

**Questions for the channel:**
1. Is the doubling / `💛` / `⚫️` system something we keep, or retire?
2. If we retire it, do we fix the already-approved strings that use it?

---

## 6. Plausible, worth approving (~190)

A large number are reasonable and consistent with the glossary. Examples:

```
song                  → 🎵
lyrics                → 🎵📝
stanza                → 🎼📄
Homepage updated.     → 🏠 🔄 ✨
Set homepage          → 🏠 ⚙️ ✨
Reply                 → 💬↩️
Next                  → ➡️▶️
Previous              → ⬅️◀️
Akismet Anti-spam     → 🛡️🚫📨🦠
Revisions %1$s–%2$s   → 📄🔄 %1$s ↔️ %2$s
```

A few still have English left inside, which I'd fix rather than reject:

```
Delete "%s"?   → 🗑️❓Delete \"%s\"?
%s (Copy)      → 📄 %s (📝 Copy)
```

---

## What I'd suggest we do

1. **Settle dates first** (§3). They're the largest coherent cluster and they block each other
2. **Decide the policy on source-copied suggestions** (§2): reject as a category, or leave
3. **Decide whether the old grammar-encoding style is retired** (§5), and whether that applies
   retroactively to approved strings
4. Fix and approve §4 and §6
5. Only then look at the long-sentence strings

I'm happy to do all of the mechanical work: the bulk rejections, the fixes, the approvals,
and re-doing the already-approved date strings if we change the scheme. Just say which way
you want each call to go and I'll run it.

The only reason I haven't already is that bulk-rejecting another contributor's suggestions on
my own judgement, a day after getting PTE, felt like the wrong way to start. If you'd rather
I just use my judgement and get on with it, that works too.
