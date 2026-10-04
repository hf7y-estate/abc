# abc

Music for **Abecedarian** — three feature films meant to play simultaneously.
This repo holds the notation. Everything else lives where it is named below.

    lilypond -dno-point-and-click b1m-plunge.ly     # from the repo root; the paths are relative

## Naming

    b1m1-gewissensruf.ily
    ^^^^                     canonical, machine-read: film b, reel 1, cue 1
        ^^^^^^^^^^^^         human flavour, affects nothing

A reel is an act. Cue numbers restart per reel, so the film letter is part of
the identity, not decoration. A file's prefix must agree with its own
`\header opus` field — the one mismatch this repo has actually shipped.

**Partially applied.** Reel 1 is `b1m-plunge.ly`, `b1m1-gewissensruf.ily`,
`b1m2-serendipity.ily`, with `opus` fields `B1M1` / `B1M2`. Reel 2 is still
`2m.ly`, `2m1.ily`, with no film letter on its `opus` field; it waits on
[#2](https://github.com/hf7y/abc/issues/2), because naming a file for music
it does not contain is a false claim like any other. Tracked in
[#15](https://github.com/hf7y/abc/issues/15).

## Where the rest of it is

| what | where |
|---|---|
| every relationship, timestamp and cue↔scene link | `abcdb` — the NocoDB instance on dexter |
| takes, sketches, picture, renders | dexter, split by kind |
| the notation library | `lib/core`, a submodule of [hf7y/zly](https://github.com/hf7y/zly) |
| house style, timing vocabulary | `lib/project/` |
| open work | `gh issue list --repo hf7y/abc` |

Git holds schema and migrations, never rows. Media never enters git.

## Where the rules live

Nowhere in prose, deliberately.

| what | where it is enforced |
|---|---|
| this repo is an agent project | `.agent-project`, read by realisateur's verb build |
| media stays out of git | `.gitignore` |

Every root `.ly` compiling, a cue's prefix agreeing with its `opus`, and no
file referencing a path that does not exist are **not** enforced yet. They are
issues, not claims: `gh issue list --repo hf7y/abc --milestone "The score
compiles and a check says so"`.
