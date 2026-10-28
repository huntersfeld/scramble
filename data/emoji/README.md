# Emoji data

The Link Up and Common Thread drills run on a tagged emoji set.

- **Source:** [emojibase-data](https://github.com/milesj/emojibase) 18.0.0 (MIT), which packages the Unicode CLDR English names and keywords. Pulled in as a dev dependency, never shipped to players.
- **`tags.txt`:** the hand-written layer. It defines 78 connections in four difficulty levels (what it is and its color, what it's like, what it has or does, wordplay and team names) and tags 374 emoji with every connection they fit. A trailing `?` marks a tag a player could argue, which keeps that emoji out of any puzzle where it would be ambiguous.
- **`emoji-tagged.json`:** generated. Every emoji up to Emoji 13.1 with its name, group, CLDR keywords and, where tagged, our nouns, adjectives, descriptors and wordplay.

Only Emoji 13.1 and older are used, so the glyphs render on nearly every phone.

To change the tags, edit `tags.txt`, then:

```
npm install
npm run build:emoji
```

The build checks every emoji against emojibase, fails on unknown tags or connections with fewer than four sure members, rewrites `emoji-tagged.json`, and regenerates the `EMOJI-TAGS` block inside `index.html`.
