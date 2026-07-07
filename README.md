# dj-study

A Claude Code skill that studies DJ technique from YouTube: pulls tutorial and remix-breakdown
transcripts (via the companion [yt-vault](https://github.com/devanshc777/yt-vault) CLI), distills
them into technique notes, and converts described transitions into reproducible settings for
[dj-holo](https://github.com/devanshc777/dj-holo), a hand-tracked browser DJ deck.

Video → transcript → technique note → practice recipe. The whole loop stays local.

## What it produces

1. **Technique notes** — structured breakdowns (what the DJ did, when, why it works) saved to your vault
2. **Practice recipes** — concrete dj-holo parameter settings that reproduce a described transition

## Requires

- [yt-vault](https://github.com/devanshc777/yt-vault) for transcript fetching
- [dj-holo](https://github.com/devanshc777/dj-holo) if you want the practice-recipe half

## Install (Claude Code)

```powershell
New-Item -ItemType Junction -Path "$env:USERPROFILE\.claude\skills\dj-study" -Target "<clone-path>"
```

Part of a personal music-learning pipeline; paths inside `SKILL.md` assume that setup — adjust to yours.

## License

MIT
