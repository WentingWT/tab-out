# Tab Out

**Keep tabs on your tabs.**

This is a personal modified version of [Tab Out](https://github.com/zarazhangrui/tab-out), originally created by [Zara Zhangrui](https://github.com/zarazhangrui).

The original project idea and core implementation are Zara's. This fork keeps that foundation and adds small new-tab workflow customizations: a bookmark bar, Google search, custom shortcuts, and a few local-only configuration hooks.

Tab Out is a Chrome extension that replaces your new tab page with a dashboard of everything you have open. Tabs are grouped by domain, with homepages (Gmail, X, LinkedIn, etc.) pulled into their own group. Close tabs with a satisfying swoosh + confetti.

No server. No account. No backend. Just a Chrome extension.

---

## Install with a coding agent

Send your coding agent (Claude Code, Codex, etc.) this repo and say **"install this"**:

```
https://github.com/WentingWT/tab-out
```

The agent will walk you through it. Takes about 1 minute.

---

## Features

- **See all your tabs at a glance** on a clean grid, grouped by domain
- **Homepages group** pulls Gmail inbox, X home, YouTube, LinkedIn, GitHub homepages into one card
- **Close tabs with style** with swoosh sound + confetti burst
- **Duplicate detection** flags when you have the same page open twice, with one-click cleanup
- **Click any tab to jump to it** across windows, no new tab opened
- **Save for later** bookmark tabs to a checklist before closing them
- **Bookmark bar** shows your Chrome bookmarks at the top of the new tab page
- **Google search** gives you a compact search box directly in the dashboard
- **Custom shortcuts** lets you add local new-tab shortcuts stored on your own machine
- **Localhost grouping** shows port numbers next to each tab so you can tell your vibe coding projects apart
- **Expandable groups** show the first 8 tabs with a clickable "+N more"
- **Local storage** saves tabs and shortcuts in Chrome extension storage
- **Pure Chrome extension** no server, no Node.js, no npm, no setup beyond loading the extension

---

## Manual Setup

**1. Clone the repo**

```bash
git clone https://github.com/WentingWT/tab-out.git
```

**2. Load the Chrome extension**

1. Open Chrome and go to `chrome://extensions`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Navigate to the `extension/` folder inside the cloned repo and select it

**3. Open a new tab**

You'll see Tab Out.

---

## How it works

```
You open a new tab
  -> Tab Out shows your open tabs grouped by domain
  -> Homepages (Gmail, X, etc.) get their own group at the top
  -> Click any tab title to jump to it
  -> Close groups you're done with (swoosh + confetti)
  -> Save tabs for later before closing them
```

Everything runs inside the Chrome extension. There is no external server or account. Saved tabs are stored in `chrome.storage.local`.

Custom shortcuts are also stored in `chrome.storage.local`. Optional personal rules can be placed in `extension/config.local.js`; that file is ignored by git so local-only settings stay local.

The page may request favicons and web fonts from the browser/Google-provided services so site icons and text render nicely.

---

## Tech stack

| What | How |
|------|-----|
| Extension | Chrome Manifest V3 |
| Storage | chrome.storage.local |
| Sound | Web Audio API (synthesized, no files) |
| Animations | CSS transitions + JS confetti particles |

---

## License

MIT

---

Original project built by [Zara](https://github.com/zarazhangrui). This fork is maintained by [WentingWT](https://github.com/WentingWT) and contains personal workflow customizations.
