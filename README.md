# 🎨 .themes-oh-my-posh

> Custom themes for [Oh My Posh](https://ohmyposh.dev/) — minimal, clean, and actually useful.

---

## ⚡ Quick Start

> **Requires:** Oh My Posh installed. If you haven't, [go here first](https://ohmyposh.dev/docs/installation/windows).

### 1. Pick a theme

Browse the [`themes/`](./themes/) folder and find one you like.

### 2. Get the raw link

1. Open the `.json` file you want.
2. Click **Raw** (top-right of the file preview on GitHub).
3. Copy the URL from your browser — it'll look like this:

```
https://raw.githubusercontent.com/<your-user>/.themes-oh-my-posh/main/themes/minimalist_r1.json
```

### 3. Apply it

**PowerShell (Windows):**
```powershell
oh-my-posh init pwsh --config "https://raw.githubusercontent.com/<your-user>/.themes-oh-my-posh/main/themes/minimalist_r1.json" | Invoke-Expression
```

**Bash / Zsh (Linux/macOS):**
```bash
eval "$(oh-my-posh init bash --config 'https://raw.githubusercontent.com/<your-user>/.themes-oh-my-posh/main/themes/minimalist_r1.json')"
```

**Fish:**
```fish
oh-my-posh init fish --config 'https://raw.githubusercontent.com/<your-user>/.themes-oh-my-posh/main/themes/minimalist_r1.json' | source
```

### 4. Make it permanent

Add the line above to your shell profile:

| Shell | Profile file |
|-------|-------------|
| PowerShell | `$PROFILE` |
| Bash | `~/.bashrc` |
| Zsh | `~/.zshrc` |
| Fish | `~/.config/fish/config.fish` |

---

## 🗂️ Themes

### `minimalist_r1` — The OG
> Clean, single-line, no noise.

**What it shows:**
- 🐚 Shell name (diamond style, dark purple `#381438`)
- 🕐 Current time `HH:MM`
- 🐍 Python venv (only when active)
- 📁 Current folder name (blue)
- 🌿 Git branch (red)

**Best for:** anyone who wants to know where they are and what branch they're on. Nothing more.

---

### `minimal_clean` — Two-line, zero clutter
> Folder + git status on line 1. Clean `❯` prompt on line 2.

**What it shows:**
- 📁 Current folder (blue)
- 🌿 Git branch — grey normally, orange if there are uncommitted changes, with `*` indicator
- 🐍 Python venv (only when active, purple)
- ✓ / ✗ Last exit status — green if OK, red if error

**Best for:** developers who want feedback on the last command without giving up screen space. The two-line layout keeps the actual typing area completely clean.

---

### `tech_dark` — Cyberpunk terminal
> Full powerline. Neon on black. Built for dark terminals.

**What it shows:**
- 🖥️ OS icon (neon green `#00FF9C`, black background)
- 👤 Username (cyan `#4FC3F7`)
- 📂 Path abbreviated with `…` — max 4 levels deep (bright cyan `#00D9FF`)
- 🌿 Git branch + added/deleted count — green normally, orange if uncommitted, red if diverged, with ahead/behind arrows
- ⏱️ Command execution time (only shows if the last command took over 2 seconds, in purple)
- ✓ / ✗ Exit code — neon green or red
- Right side: language versions (Python 🐍, Node 🟢, .NET 🔷) only when detected in the current folder
- 🕐 Time `HH:MM:SS` dimmed on the right

**Prompt:** `❯❯` in neon green on a clean second line.

**Best for:** dark terminals (VSCode dark, Windows Terminal dark themes, iTerm2 with dark backgrounds). The neon palette pops on `#0D0D0D`–`#1A1A2E` backgrounds.

---

### `default` (schema/schema.json) — Full powerline
> The full experience: OS icon, user, path, git details, exit code.

**What it shows:**
- 🖥️ OS icon
- 👤 `user@hostname`
- 📂 Current path (up to 3 folders deep)
- 🌿 Git branch + file change counts — color shifts when staging/working/ahead
- ✓ / ✗ Exit code in its own diamond

**Best for:** a primary machine where you want full context at a glance.

---

## 🔧 Customization Tips

**Change a color:**  
Every segment has a `"foreground"` and/or `"background"` field. Use any hex color like `"#FF6347"`.

**Change the path style:**  
In the `path` segment, the `"style"` property under `properties` accepts:
- `"folder"` — just the current folder name
- `"full"` — full absolute path
- `"agnoster"` — abbreviated with `…`
- `"mixed"` — short path + folder

**Add a language version** (e.g., Node.js):
```json
{
  "type": "node",
  "style": "plain",
  "foreground": "#68A063",
  "template": " {{ .Full }}",
  "properties": {
    "display_mode": "files",
    "fetch_version": true
  }
}
```

**Validate locally:**
```bash
oh-my-posh debug --config ./themes/minimal_clean.json
```

---

## 📦 Recommended Fonts

Oh My Posh uses Nerd Font icons. These themes were built with:

- [**MesloLGS NF**](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k) — clean, widely compatible
- [**JetBrainsMono Nerd Font**](https://www.nerdfonts.com/font-downloads) — great for coding terminals
- [**CaskaydiaCove Nerd Font**](https://www.nerdfonts.com/font-downloads) — the Cascadia Code with icons (official Microsoft)

Install via Oh My Posh directly:
```powershell
oh-my-posh font install meslo
```

---

## 🤝 Contributing

Fork, modify, open a PR. The only rule: keep themes focused and named descriptively.

---

<sub>Built with ❤️ and too much time staring at terminals.</sub>
