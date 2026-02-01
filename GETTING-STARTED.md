# Getting Started Guide for Lukasz

Welcome! This guide will help you set up everything you need to manage your Pod Reglami website and get help from Claude (AI assistant) whenever you need it.

---

## What You're Receiving

You'll get a folder containing:

```
theretrostay/
├── index.html              ← Your website (all code in one file)
├── images/                 ← All your property photos
├── MARKETING-STRATEGY.md   ← Complete marketing guide (READ THIS!)
├── CLAUDE.md              ← Instructions for Claude AI about your project
├── GETTING-STARTED.md     ← This file
└── .claude/               ← Claude's settings (don't edit)
```

---

## Part 1: Quick Start (No Coding Required)

### Just Want to Read the Marketing Guide?

1. Open the `MARKETING-STRATEGY.md` file
2. You can open it with:
   - **Any text editor** (Notepad, TextEdit)
   - **VS Code** (recommended - free, shows formatting nicely)
   - **Online:** Upload to [markdownlivepreview.com](https://markdownlivepreview.com/) to see it formatted

That's it! The marketing guide is self-contained and ready to follow.

---

## Part 2: Setting Up Claude Code (AI Assistant)

Claude Code is an AI assistant that can help you:
- Update your website
- Answer questions about your marketing strategy
- Write new listing descriptions
- Translate content
- Troubleshoot issues

### Step 1: Install Node.js

Claude Code requires Node.js (a free program).

**On Mac:**
1. Open Terminal (press `Cmd + Space`, type "Terminal", press Enter)
2. Install Homebrew (if you don't have it):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
3. Install Node.js:
   ```bash
   brew install node
   ```

**On Windows:**
1. Go to [nodejs.org](https://nodejs.org/)
2. Download the "LTS" version (green button)
3. Run the installer, click Next through everything
4. Restart your computer

**Verify it worked:**
Open Terminal (Mac) or Command Prompt (Windows) and type:
```bash
node --version
```
You should see something like `v20.x.x`

### Step 2: Install Claude Code

In Terminal or Command Prompt, run:

```bash
npm install -g @anthropic-ai/claude-code
```

Wait for it to finish (may take 1-2 minutes).

### Step 3: Get Your API Key

1. Go to [console.anthropic.com](https://console.anthropic.com/)
2. Create an account (or sign in)
3. Go to "API Keys"
4. Click "Create Key"
5. Copy the key (starts with `sk-ant-...`)
6. **Save it somewhere safe!** You'll need it once.

### Step 4: Set Up Your API Key

**On Mac:**
```bash
export ANTHROPIC_API_KEY="sk-ant-your-key-here"
```

**On Windows (Command Prompt):**
```bash
set ANTHROPIC_API_KEY=sk-ant-your-key-here
```

**To make it permanent (recommended):**

*Mac:* Add the export line to your `~/.zshrc` or `~/.bash_profile`

*Windows:*
1. Search "Environment Variables" in Start menu
2. Click "Environment Variables"
3. Under User Variables, click "New"
4. Name: `ANTHROPIC_API_KEY`
5. Value: your key

### Step 5: Navigate to Your Project

1. Put the `theretrostay` folder somewhere on your computer (e.g., Desktop or Documents)

2. In Terminal/Command Prompt, navigate to it:

**Mac:**
```bash
cd ~/Desktop/theretrostay
```

**Windows:**
```bash
cd C:\Users\YourName\Desktop\theretrostay
```

### Step 6: Start Claude Code

Run:
```bash
claude
```

You should see Claude start up and greet you!

---

## Part 3: Using Claude Code

### Basic Commands

Once Claude is running, just type naturally:

**Examples of things you can ask:**

```
Show me the marketing strategy summary
```

```
Help me write an Instagram post about skiing
```

```
Translate this text to Polish: "Welcome to our mountain retreat"
```

```
Update the website price from 500 PLN to 550 PLN
```

```
What should I do first to get more bookings?
```

### Useful Built-in Commands

| Command | What It Does |
|---------|--------------|
| `/help` | Show help menu |
| `/clear` | Clear conversation history |
| `/cost` | Show API usage cost |
| `Ctrl+C` | Exit Claude |

### Tips for Best Results

1. **Be specific:** Instead of "help with marketing", say "write me 3 Instagram captions about the thermal baths near my property"

2. **Reference the files:** You can say "look at my marketing strategy" and Claude will read the file

3. **Ask follow-ups:** If you don't understand something, just ask "explain that simpler"

4. **Request changes:** "Make that shorter" or "make it more formal" works great

---

## Part 4: Making Website Changes

### Simple Text Changes

Ask Claude:
```
Change the price on the website from 500 PLN to 550 PLN
```

Claude will edit the `index.html` file for you.

### View Your Changes Locally

1. Find `index.html` in your folder
2. Double-click it — it opens in your browser
3. See your changes!

### Put Changes Online (GitHub Pages)

Your website is hosted on GitHub. To update the live site:

**Option A: Ask Claude**
```
Commit my changes and push to GitHub
```

**Option B: Manual (if you know git)**
```bash
git add .
git commit -m "Updated pricing"
git push
```

The live site updates automatically in 1-2 minutes.

---

## Part 5: Common Tasks

### "I want to add a new photo"

1. Put the photo in the `images/` folder
2. Ask Claude: "Add the new photo mountain-view.jpg to the gallery"

### "I want to change the website text"

Ask Claude:
```
Change the hero description to: "Your perfect mountain escape awaits"
```

### "I need help with my Airbnb listing"

Ask Claude:
```
Write me a short Airbnb description (500 characters) highlighting
that we're close to ski slopes and pet-friendly
```

### "I want to translate something"

```
Translate this review response to Polish: "Thank you for staying
with us! We hope to see you again."
```

### "I forgot what to do next"

```
What are my highest priority marketing tasks right now?
```

---

## Part 6: Troubleshooting

### "Command not found: claude"

Node.js or Claude Code isn't installed properly. Try:
```bash
npm install -g @anthropic-ai/claude-code
```

### "API key not found" or "Unauthorized"

Your API key isn't set. Run:
```bash
export ANTHROPIC_API_KEY="your-key-here"
```

### "I messed up the website"

Don't worry! Ask Claude:
```
Undo the last change to index.html
```

Or if really broken:
```
Reset index.html to the last working version from git
```

### "The live website isn't updating"

1. Make sure changes are committed and pushed
2. Wait 2-3 minutes (GitHub Pages can be slow)
3. Hard refresh your browser: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)

### "I don't understand the marketing guide"

Ask Claude!
```
Explain the Airbnb setup section in simpler terms
```

```
What does "occupancy rate" mean?
```

---

## Part 7: Cost Information

### Claude Code API Costs

Claude Code uses the Anthropic API, which has usage-based pricing:

- **Claude Sonnet:** ~$3 per million input tokens, ~$15 per million output tokens
- **Typical session:** $0.05 - $0.50 depending on how much you ask

**To check your spending:**
- Type `/cost` in Claude
- Or visit [console.anthropic.com](https://console.anthropic.com/) → Usage

**Tips to save money:**
- Be concise in your questions
- Don't repeat the same question multiple times
- Use `/clear` to start fresh if conversation gets long

### Free Alternatives

If you don't want to use Claude Code:
- [claude.ai](https://claude.ai) — Free tier available (just copy/paste content)
- [ChatGPT](https://chat.openai.com) — Alternative AI, free tier available

---

## Quick Reference Card

Print this out!

```
┌─────────────────────────────────────────────────────────┐
│                   POD REGLAMI QUICK REFERENCE           │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  START CLAUDE:                                          │
│  1. Open Terminal                                       │
│  2. cd ~/path/to/theretrostay                          │
│  3. claude                                              │
│                                                         │
│  COMMON ASKS:                                           │
│  • "What should I do next for marketing?"              │
│  • "Write an Instagram post about [topic]"             │
│  • "Update the website [what you want changed]"        │
│  • "Translate this to Polish: [text]"                  │
│  • "Help me respond to this review: [review]"          │
│                                                         │
│  COMMANDS:                                              │
│  • /help     → Get help                                │
│  • /clear    → Clear conversation                      │
│  • /cost     → Check API spending                      │
│  • Ctrl+C    → Exit Claude                             │
│                                                         │
│  WEBSITE:                                               │
│  • Live: andreasnyberg82.github.io/theretrostay        │
│  • Edit: Ask Claude to change index.html               │
│  • Publish: "commit and push to GitHub"                │
│                                                         │
│  FILES:                                                 │
│  • MARKETING-STRATEGY.md → Full marketing guide        │
│  • index.html → Website code                           │
│  • images/ → Photos                                    │
│                                                         │
│  HELP: Just ask Claude anything!                       │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## Contact & Support

**Website issues?** Ask Claude or check the GitHub repository.

**Marketing questions?** Read `MARKETING-STRATEGY.md` or ask Claude to explain.

**Anthropic/Claude Code issues?** Visit [docs.anthropic.com](https://docs.anthropic.com)

---

*Good luck with Pod Reglami! You've got a beautiful property — now let's fill it with happy guests!* 🏔️
