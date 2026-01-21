# Publishing to ClawdHub

Your skill is ready: `obsidian-conversation-backup.skill` (7.4K)

## Steps to Publish on ClawdHub

### 1. Create GitHub Repository

```bash
cd /root/clawd/obsidian-conversation-backup

# Initialize git
git init
git add .
git commit -m "Initial release: Obsidian conversation backup skill"

# Create repo on GitHub (via web or gh CLI)
# Then push
git remote add origin https://github.com/YOUR-USERNAME/clawdbot-obsidian-backup.git
git branch -M main
git push -u origin main
```

### 2. Submit to ClawdHub

Go to: https://clawdhub.com/skills

**Submission form will ask for:**
- **Skill name**: `obsidian-conversation-backup`
- **GitHub URL**: `https://github.com/YOUR-USERNAME/clawdbot-obsidian-backup`
- **Description**: "Automatic conversation backup system for Obsidian with incremental snapshots and chat-style formatting"
- **Tags**: `backup`, `obsidian`, `archival`, `markdown`, `formatting`

### 3. What Gets Published

Your `SKILL.md` frontmatter already includes:
```yaml
name: obsidian-conversation-backup
description: Automatic conversation backup system...
```

ClawdHub will:
- Read your SKILL.md
- Display description and usage
- Allow users to install via: `clawdbot skills install YOUR-USERNAME/clawdbot-obsidian-backup`

## Alternative: Direct Distribution

Share the `.skill` file directly:

```bash
# Users can install from URL
clawdbot skills install https://your-site.com/obsidian-conversation-backup.skill

# Or from local file
clawdbot skills install ./obsidian-conversation-backup.skill
```

## What Your Skill Includes

- ✅ **SKILL.md**: Complete documentation with frontmatter
- ✅ **4 scripts**: All working backup tools
- ✅ **Format definitions**: JQ formatting script
- ✅ **Executable permissions**: Scripts are ready to run

## Testing Before Publishing

Have someone else test install:

```bash
# Extract and test
tar -xzf obsidian-conversation-backup.skill
cd obsidian-conversation-backup

# Configure vault path
vim scripts/monitor_and_save.sh  # Update VAULT_DIR

# Test run
./scripts/save_full_snapshot.sh test
```

## License (Recommended)

Add a LICENSE file before publishing:

```bash
# MIT License example
cat > LICENSE << 'EOF'
MIT License

Copyright (c) 2026 [Your Name]

Permission is hereby granted, free of charge...
EOF
```

## Version Updates

When updating the skill:

1. Update SKILL.md with changes
2. Re-package: `python3 /usr/lib/node_modules/clawdbot/skills/skill-creator/scripts/package_skill.py obsidian-conversation-backup .`
3. Tag release on GitHub: `git tag v1.1.0 && git push --tags`
4. Update ClawdHub entry

## Support

Users can report issues on your GitHub repo or via ClawdHub comments.

Good luck with your first Clawdbot skill! 🚀
