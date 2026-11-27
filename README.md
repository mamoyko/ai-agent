# My AI Office

_A small starter for your own AI team in Claude Code: a **Chief of Staff**, a numbered brain, and an optional 3D office you can see. One room for now. You name the office and the Chief during `/setup`; the rest of the team joins when you need it._

## Install (pick one)
**Easiest: let Claude do it.** Make an empty folder, open it in Claude Code (desktop app: Code tab → choose folder; or run `claude` inside it) and paste:
```
Install my AI office in this folder from https://github.com/elronnaranja/O2San-Base-Install (copy every file into this folder, not a subfolder), then run /setup.
```

**With a terminal:**
```bash
git clone https://github.com/elronnaranja/O2San-Base-Install my-ai-office
```
Then open the `my-ai-office` folder in Claude Code and type `/setup`.

**Without git:** on the GitHub page press **Code → Download ZIP**, unzip it, open the folder in Claude Code and type `/setup`.

`/setup` takes about 5 minutes: you name your office and your Chief, and the Chief saves who you are, your rules and your first project. It also moves the brain (your notes) out of the office into its own `My AI Brain` folder next to it and leaves a link behind. Open that `My AI Brain` folder in Obsidian ("Open folder as vault"). Office and notes stay separate: you can reinstall the office without touching your notes. Back `My AI Brain` up on its own (Obsidian Sync or a private git repo). Best place for both: one `Claude` folder in your home folder with `My AI Office`, `My AI Brain` and `Projects/` inside (see the article). Set up before this change? Say "Move my brain out". Then ask for anything in plain words. The Chief plans it, does it, checks it, and asks before anything is sent, posted or paid.

## See your office (optional)
The 3D office view is optional. Don't want it? Delete the `office/` folder: setup, new agents and everything else keep working, they just skip the office.

Double-click `office/index.html`. It opens in your browser: one room, the Brain in the middle, your Chief at a desk. Drag to turn, scroll to zoom, click anyone. Now and then someone walks to the Brain to save their work.

**Spawn a new agent:** press **+ Spawn agent**. A see-through new hire appears at a random free desk with a random name and look (press 🎲 for another). Type its one job, press **Copy**, and paste the command into Claude Code. The Chief writes its brief and brain room and gives it that desk. Claude Code asks before writing the agent's file into `.claude/agents/`: say yes. Reload the page to see it.

**Make it yours:** click anyone and press the pencil to customize them (hair, headgear, glasses, facial hair, accessory, complexion, colors), or drag them to the couch, the pantry, someone else's chair (they swap desks), back to their own chair, or any spot on the floor. Their desk stays theirs while they're away. Changes show at once and stay in that browser; the page gives you a `/office …` command to paste into Claude Code so they're saved in the office for good.

It starts with one table, the Chief's. Every new agent brings its own, up to 9. Full? Say "upgrade the office". The room is yours to redesign: more desks, a second room, your colors.

## Grow it
- **`/teach <what to change>`**: corrected the Chief? Save it so it sticks. For an agent: `/teach writer: shorter intros`.
- **`/new-agent`** (or the Spawn button): when one kind of work keeps coming back, add one team member for it. One agent, one job.
- **`/tidy`**: every few weeks, or when the Chief suggests it, tidy the rules: duplicates merged, clashes settled, each rule in one place.
- **Keep it small.** Most offices need 3 to 7 agents, short rules and a short index. Say "Merge agents" when two start doing the same job. (I learned this the hard way: see the article.)
- **One task, one session.** Start a fresh chat for each new task; the brain remembers.

## What's inside
```
CLAUDE.md                  Chief of Staff instructions for Claude Code
AGENTS.md                  same, for ChatGPT Codex and other tools
office/index.html          your 3D office, optional (team list inside; /new-agent adds to it; delete office/ if you don't want it)
.claude/agents/            the team (starts with chief-of-staff.md)
.claude/commands/          /setup, /teach, /new-agent, /office, /tidy
.claude/hooks/guard.py     the guard: blocks key files, asks before deleting or sending
.claude/playbooks/         quick commands ("Status", "What needs me?", "Move my brain out") + brain-outside.md
.claude/skills/            skills you add later
tools/                     API scripts you add later (keys in .env)
brain/                     the memory; /setup moves it to its own folder next to the office (open THAT in Obsidian) and leaves a link here
  README.md                how the memory works + map of every folder
  00-Core/                 about-me.md: you, your office's name, your Chief's name
  01-Business/             your main work
  02-Brand/                your brand or second line of work (optional)
  03-AI-Office/            RULES.md (levels A-D, your rules) and decisions.md
  04-Personal/             personal notes (never secrets)
  05-Projects/             one note per bigger project
  06-Research/             what was looked up
  07-Daily-Logs/           one short note per day
  08-Inbox/                drop zone and proposals (archive/ instead of deleting)
  09-Templates/            state-page.md
  10-Office/               the office at work: board, approvals, state/, lessons/, reports/, one room per agent
```

## Add-ons (installed with the folder)
Claude Code offers these when you open the folder (say yes to trust the folder). If it says one is "enabled but isn't installed", run the command it shows, for example `claude plugin install superpowers@claude-plugins-official --scope project`. They're optional:
- **superpowers**: planning, testing and checking habits for building things.
- **claude-security**: scans code for security holes.
- **caveman**: short replies to save tokens. Off by default; type `/caveman` to turn it on.

## Safety defaults
Asks before anything sent, public or paid. No passwords or keys in files (use `.env`, never committed). Never deletes; archives instead. Plain language.

The most important of these aren't only written down: a small guard (`.claude/hooks/guard.py`, run by Claude Code before every action) blocks reading `.env` and stops to ask you before any deletion or anything sent, posted, paid or deleted through a connector. It needs Python, which most Macs have; if yours doesn't, Claude Code shows a hook error and the written rules still apply.

**Codex users:** open the folder in Codex; it reads `AGENTS.md`. Say "run setup" and it follows `.claude/commands/setup.md`.
# ai-agent
