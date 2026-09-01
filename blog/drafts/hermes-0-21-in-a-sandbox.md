# Hermes 0.21 in a Sandbox

**Date:** 2026-09-01
**Tag:** release
**Slug:** hermes-0-21-in-a-sandbox

---

Nous Research shipped [Hermes Agent v0.21.0](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.8.31) on August 31. They called it the Pantheon release, this is the version where one Hermes install stops being one agent. Welcome to the multiplayer agent era.

## Agents that talk to each other

**Bot Mode** is now bundled and on by default in the desktop app. Each bot gets its own role, model, memory, skills and avatar, and they deliberate together in group chats. The avatars are drawn from the bot's name, so as the docs put it: same name, same face, forever.

**`hermes peer`** is the mechanism underneath. Any Hermes agent can now message any other by handle, across profiles and across gateways. The message lands in the receiving bot's canonical Bot Chat and the reply comes back to the sender, so a thread between two agents survives a restart.

**Cron jobs now remember.** Cron agents load and update persistent memory like every other agent, and `continuity=true` carries each run's output into the next. A daily job stops being a daily stranger.

**Subagents are steerable while they run.** `delegate_task` gained live orchestration: list the running children and steer one mid-flight with a course correction.

There is also an MCP Command Center that merges your servers and the catalog into one page with drag-in import, six new model providers, a Ctrl+P fuzzy command palette, and terminal pets, because as Nous puts it, a companion should have a companion.

## Running Hermes using Clawstainer is easy.

```bash
cargo install clawstainer

clawstainer create --name hermes-box --memory 4096 --cpus 2 --linger
clawstainer provision <id> --components hermes-agent

clawstainer shell <id>
hermes setup
```

That is a full Hermes 0.21 install in an isolated Linux box on your laptop. No Docker, no cloud account, everything installed on a disposable linux container. Give it 4GB, since Hermes wants the room while it installs.


[clawstainer on GitHub](https://github.com/friscobrisco/clawstainer) · [Docs](https://github.com/friscobrisco/clawstainer/blob/main/docs.md) · [Hermes v0.21.0 release notes](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.8.31)
