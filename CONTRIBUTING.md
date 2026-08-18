# Contributing

## Ground rules

1. **Cite evidence.** The order of authority is:
   1. The [official glossary](https://translate.wordpress.org/locale/art-xemoji/default/glossary/)
   2. Existing coherent translations (link to them)
   3. Reasoned proposals
2. **Mark guesses as guesses.** If a convention has no precedent, say so rather than
   presenting it as settled.
3. **Consistency beats cleverness.** A slightly worse emoji used consistently is better than
   two good ones used interchangeably.

## Proposing a vocabulary addition

Include:

- The English term
- The proposed emoji
- Rationale
- Any collision with an existing assignment (the glossary already reuses 🔎, 🎯, 📧, ⌨️, ✅)

## Things that are settled

These come from the official glossary and shouldn't be changed here:

- `tag` is `🏷`: U+1F3F7 with **no** variation selector
- `file` is `📁` (folder), not `📄`
- `key` is `⌨️` only in a keyboard context, otherwise `🔑`

## Things that must never be translated

- Date format strings (`F j, Y`). Emoji-fying these breaks date output
- Placeholders (`%s`, `%1$s`, `%link%`)
- HTML tags and code identifiers (`href`, `rel`, `target`)
- Trailing spaces in the source string
