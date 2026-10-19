# maintainers/ — Ludea only

Procedures for Ludea's own agents. This folder is **not** part of the engine layer: it is never
synced into the games, and a game created with "Use this template" deletes it (new-game).

- `triage-upstream.md` — the **engine agent** (scheduled task « Ludea – agent moteur », 03:55 Paris):
  engine inbox → one batch PR on this repo, tried on the Nebula test bench → the owner's OK →
  merge → propagation to Nebula and every Ludea catalogue game.
- The **catalogue agent** (« Ludea – agent catalogue », 05:55 Paris) follows
  `.claude/skills/review-submission/` in `ludea-ai/ludea-ai.github.io`.

## Scope rule — Ludea and Encrine (owner decision, 2026-10-19)
Encrine (the owner's other project) is a separate scope: never look at, check or change it from
Ludea. The only link: when something built for Ludea could help Encrine, send a short note (what,
why, where in our repo) to the Encrine main session with `send_message`
(`session_01Uxi6vTyZY4CiKFDutfBqKC`); Encrine does the same for us, and we decide with the owner
whether to take it up.
