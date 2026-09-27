# StepUp 🚀

A minimal, beautiful roadmap tracker inspired by Duolingo — built for people who want to break down one big task into a sequence of achievable levels and rewards.

No XP. No streaks. No distractions. Just you and your roadmap.

---

## ✨ Features

### 🎯 One Big Task, One Clear Goal
- Set a single big task (e.g., *"Complete SST Syllabus"*)
- Rename it anytime via inline edit — click the pencil icon
- The name syncs across the sidebar and the floating progress bar

### 🗺️ Duolingo-Style Zigzag Roadmap
- Levels and rewards displayed as large, tappable circular nodes
- Precise SVG connectors curve smoothly between each node
- Alternating left-right zigzag layout for a natural, game-like path
- Completed nodes glow blue (tasks) or gold (rewards) with a green checkmark badge

### 📦 Two Node Types
- **📘 Task** — a level or chapter to complete (blue theme)
- **🎁 Reward** — something to look forward to (gold theme)
- Mix and match freely to build your own pace

### ✏️ Full Inline Editing — No Prompts
- **Big Task name:** Click the pencil icon, edit inline, save or cancel
- **Level names:** Click any name (in sidebar *or* on the roadmap) to edit it in place
- **Icons:** Click any icon tile to open the emoji picker modal
  - Choose from a curated default set
  - Add your own custom emojis anytime

### 🔀 Drag-to-Reorder Sequence
- Drag the grip handle (⠿) on any item in the sidebar list
- Reorder tasks and rewards to change the roadmap order instantly
- The roadmap redraws itself to match

### 📊 Floating Glass Progress Bar
- Compact, glassmorphic bar with `backdrop-blur`
- Circular progress ring + horizontal progress bar
- Live counts of completed items, tasks, and rewards
- Big task shown as a compact chip — doesn't hog vertical space

### 🎉 Delightful Feedback
- Confetti burst when completing a node
- Toast notifications for every action
- Smooth spring animations on node clicks
- Animated dashed connectors flowing along the path

### 💾 Local Persistence
- Everything auto-saves to `localStorage`
- Custom emojis persist across sessions
- No backend, no login, no tracking

---

## 🚀 Getting Started

1. **Download** `index.html`
2. **Open** it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Start building your roadmap!

That's it. No build step, no dependencies, no server required.

---

## 🎮 How to Use

| Action | How |
|--------|-----|
| **Rename big task** | Click the ✏️ pencil icon next to the big task name |
| **Add a level** | Click **"Add Level"** at the bottom of the sidebar to expand the form |
| **Choose task or reward** | Toggle between **📘 Task** and **🎁 Reward** buttons |
| **Pick an icon** | Click any emoji tile, or hit **"+ Custom"** to add your own |
| **Complete a node** | Click any circular node on the roadmap |
| **Rename a level** | Click the name in the sidebar list *or* below the node |
| **Change a level's icon** | Click the icon tile in the sidebar |
| **Reorder levels** | Drag the grip handle (⠿) on the left of any sidebar item |
| **Delete a level** | Hover a sidebar item → click the 🗑️ trash icon |
| **Reset progress** | Clear browser localStorage (key: `stepup_roadmap_v4`) |

---

## 🎨 Design System

A **dark, blue-themed** palette with soft, rounded corners throughout.

| Token | Value | Usage |
|-------|-------|-------|
| `--bg-app` | `#0A1428` | Main background |
| `--bg-sidebar` | `#0F1D36` | Sidebar surface |
| `--bg-card` | `#16294A` | Cards, inputs, nodes |
| `--blue-500` | `#3D7EDB` | Primary blue |
| `--gold-500` | `#F1C232` | Reward accent |
| `--green-500` | `#3FB950` | Completion green |

- **Font:** [Nunito](https://fonts.google.com/specimen/Nunito) (400–900 weights)
- **Icons:** [Font Awesome 6](https://fontawesome.com/)
- **Sidebar:** squared corners (no radius) — a deliberate design choice
- **Everything else:** generously rounded (12px → 32px → full pills)

---

## 🧩 Tech Stack

| Layer | Tech |
|-------|------|
| **Markup** | Single HTML file |
| **Styling** | Pure CSS (custom properties, flexbox, grid) |
| **Logic** | Vanilla JavaScript (IIFE, no framework) |
| **Persistence** | `localStorage` |
| **Connectors** | Inline SVG paths with cubic Bézier curves |

Zero dependencies. Zero build tools. Zero config.

---

## 📁 File Structure

```
index.html    ← the entire app
README.md     ← you are here
```

Everything lives in one file for maximum portability.

---

## 🧠 Data Model

```js
{
  bigTask: "Complete SST Syllabus",
  nodes: [
    { id, type: "task" | "reward", label, symbol, completed },
    ...
  ],
  customEmojis: ["🦊", "🍕", ...]
}
```

Stored in `localStorage` under the key `stepup_roadmap_v4`.

---

## 🌈 Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Enter` | Save inline edit / Add level / Confirm modal |
| `Esc` | Cancel inline edit |
| `Enter` (in custom emoji) | Add custom emoji |

---

## 🛠️ Customization Tips

**Change the theme colors** — edit the CSS variables at the top of `<style>`:

```css
:root {
  --blue-500: #3D7EDB;   /* primary accent */
  --gold-500: #F1C232;   /* reward accent */
  --green-500: #3FB950;  /* completion */
  /* ... */
}
```

**Add more default emojis** — find this array in the JS:

```js
const DEFAULT_EMOJIS = ['📖','✏️','📘','🎯','🎁','🏆', ...];
```

**Change the storage key** — to avoid conflicts with old data:

```js
const STORAGE_KEY = 'stepup_roadmap_v4';
```

---

## 📱 Responsive

- **Desktop:** Two-column layout (sidebar + roadmap)
- **Mobile (< 900px):** Sidebar stacks on top, roadmap fills the rest
- Node size, offsets, and spacing auto-adjust

---

## 🐛 Troubleshooting

**My data disappeared**
- Check that you're using the same browser/profile
- `localStorage` is per-origin — clearing site data wipes the roadmap

**Emoji not showing correctly**
- Make sure your OS/browser supports the emoji
- Custom emojis are stored as raw strings; multi-codepoint emojis work fine

**Connectors look misaligned**
- Try resizing the window — the SVG paths redraw on `resize`
- If it persists, hard refresh (`Ctrl+Shift+R`)

---

## 🎯 Philosophy

> *Big goals don't fail from lack of ambition. They fail from lack of structure.*

StepUp gives you **one canvas for one goal**. Not a productivity suite. Not a habit tracker. Just a clear, delightful path from *"I don't know where to start"* to *"I did it."*

---

## 📜 License

Free to use, modify, and share. Attribution appreciated but not required.

---

**Built with 💙 for people who finish what they start.**
