# Claude Skills - Personal

Personal Claude Code skills that sync across my machines.

## Setup (new machine)

```bash
# Clone the repo
mkdir -p ~/claude-skills
cd ~/claude-skills
git clone git@github.com:austinjamesrose/claude-skills-personal.git

# Symlink to it
rm -rf ~/.claude/skills
ln -s ~/claude-skills/claude-skills-personal ~/.claude/skills
```

## Skills in this repo

| Skill | Description | Shared? |
|-------|-------------|---------|
| session-summary | End-of-session logging to Obsidian | Yes (also in work repo) |

## Workflow

### After editing a skill

```bash
cd ~/claude-skills/claude-skills-personal
git add . && git commit -m "Update skill-name" && git push
```

### Syncing shared skills

`session-summary` exists in both this repo and `claude-skills-work`. When you update it:

1. Make the change in whichever repo you're using
2. Copy the updated `SKILL.md` to the other repo
3. Commit and push both

```bash
# Example: updated session-summary in personal repo, now sync to work
cp ~/claude-skills/claude-skills-personal/session-summary/SKILL.md \
   ~/claude-skills/claude-skills-work/session-summary/SKILL.md

cd ~/claude-skills/claude-skills-work
git add . && git commit -m "Sync session-summary from personal" && git push
```

### Pulling updates on another machine

```bash
cd ~/claude-skills/claude-skills-personal
git pull
```
