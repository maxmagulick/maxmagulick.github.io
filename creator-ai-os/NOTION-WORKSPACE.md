# Creator AI OS — Notion Workspace Design

**Goal:** Help users create a week of content in 90 minutes.

A minimal Notion workspace. One home, a handful of databases, no clutter. Every part below lists its **Purpose, Layout, Databases, Properties, Templates, and User workflow.**

---

## Workspace map

```
🏠 Dashboard (Home)
├── 🏃 Weekly Sprint Dashboard
├── 📝 Content Pipeline        (database)
├── 🔍 Research Hub            (database)
├── 💬 Prompt Library          (database)
├── 📋 Swipe File              (database)
├── ♻️ Repurposing Tracker     (database)
└── 🗓️ Publishing Calendar     (view of Content Pipeline)
```

**Shared databases (built once, reused everywhere):**
- `Content Pipeline` — every piece of content.
- `Research Hub` — ideas, notes, sources.
- `Prompt Library` — copy-paste prompts.
- `Swipe File` — examples and templates.
- `Repurposing Tracker` — one idea → many formats.

The Publishing Calendar is just a calendar **view** of Content Pipeline (no extra database).

---

## 1. Dashboard (Home)

**Purpose**
The single front door. Tells the user where to go and gets them into a sprint fast. No content lives here — only links and status.

**Layout**
- Top: one-line promise — *"A week of content in 90 minutes."*
- Big button row: **Start Sprint** · **Content Pipeline** · **Publishing Calendar**.
- Left column: quick links to all sections.
- Right column: 3 small linked views — *Posting This Week*, *Drafts in Progress*, *Top Ideas*.
- Bottom: "New here? Start your first sprint" callout.

**Databases**
None of its own. Shows linked views of `Content Pipeline` and `Research Hub`.

**Properties**
N/A (uses linked database properties).

**Templates**
None. It's a static landing page.

**User workflow**
1. Open Dashboard.
2. Glance at "Posting This Week."
3. Click **Start Sprint** to begin the 90-minute run.

---

## 2. Weekly Sprint Dashboard

**Purpose**
The 90-minute control room. One page that walks the user through the whole week in 5 timed steps.

**Layout**
- Header: this week's theme + a 90-minute timer reminder.
- The 5-step checklist (toggles open each step's prompt + link).
- Inline view: this week's items from `Content Pipeline` (board by Status).

**Databases**
Uses `Content Pipeline` (filtered to this week). Optional tiny `Sprints` log database.

**Properties (optional `Sprints` log)**
| Property | Type | Example |
|----------|------|---------|
| Week | Date | Jun 9 – Jun 15 |
| Theme | Text | "Beginner money tips" |
| Platforms | Multi-select | Instagram, LinkedIn |
| Done? | Checkbox | ✅ |
| Time taken | Number | 85 (min) |

**Templates**
- **Weekly Sprint** template (the core one):
```
Theme: __________   Platforms: __________

☐ Step 1 — Set the week                ~10 min
☐ Step 2 — Generate 10–15 ideas        ~15 min   → Research Hub + Idea Prompt
☐ Step 3 — Write the content           ~35 min   → Caption/Script Prompts
☐ Step 4 — Polish + format             ~20 min   → Voice Prompt
☐ Step 5 — Schedule into Calendar      ~10 min
```

**User workflow**
1. Click **+ New** → Weekly Sprint template.
2. Set theme + platforms.
3. Work top to bottom, ticking each step.
4. Finish when all 5 boxes are checked — a week is done.

---

## 3. Content Pipeline

**Purpose**
The backbone database. Every piece of content lives here from idea to posted. Most other views are just slices of this.

**Layout**
- Default view: **Board by Status** (Idea → Drafting → Ready → Posted).
- Secondary views: *This Week* (table), *By Platform*, *Ready to Post*.

**Databases**
`Content Pipeline` (the main database).

**Properties**
| Property | Type | Example |
|----------|------|---------|
| Title | Text | "5 myths about saving money" |
| Status | Select | Idea / Drafting / Ready / Posted |
| Platform | Multi-select | Instagram, LinkedIn, TikTok |
| Pillar | Select | Pillar 1 / 2 / 3 |
| Format | Select | Caption / Reel / Carousel / Thread |
| Hook | Text | The opening line |
| Content | Page/Text | The full caption or script |
| Post Date | Date | Mon, Jun 9 |
| Source Idea | Relation → Research Hub | Linked idea |

**Templates**
- **Caption Post** — Hook + body + CTA blocks pre-filled.
- **Short-Form Script** — Hook / 3 points / CTA structure.
- **Carousel** — Slide 1–5 outline.

**User workflow**
1. During a sprint, new ideas land here as **Status = Idea**.
2. Pick a template, write the content → **Drafting**.
3. Polish → **Ready** and set Post Date.
4. After posting → **Posted**.

---

## 4. Research Hub

**Purpose**
A holding tank for raw ideas, notes, and sources — so the user never starts a sprint from a blank page.

**Layout**
- Default view: **Gallery** of idea cards.
- Secondary: *Unused Ideas* (filter Used = unchecked), *By Pillar*.

**Databases**
`Research Hub`.

**Properties**
| Property | Type | Example |
|----------|------|---------|
| Idea | Text | "Why budgeting apps fail" |
| Pillar | Select | Pillar 1 / 2 / 3 |
| Type | Select | Idea / Note / Source / Question |
| Notes | Text | Quick context |
| Link | URL | Source article |
| Used? | Checkbox | ☐ |

**Templates**
- **Idea Capture** — one line + pillar tag.
- **AI Idea Batch** — paste a list of 10–15 AI-generated ideas at once.

**User workflow**
1. Step 2 of the sprint: run an Idea Prompt, paste results in via **AI Idea Batch**.
2. Pick the best ideas → convert to a `Content Pipeline` item.
3. Mark **Used?** so it doesn't repeat.

---

## 5. Prompt Library

**Purpose**
Copy-paste prompts for every sprint step. Removes "I don't know how to prompt."

**Layout**
- Default view: **Board by Category** (Idea / Hook / Caption / Script / Repurpose / Voice).
- Each prompt opens to show copy-paste text with `[BLANKS]`.

**Databases**
`Prompt Library`.

**Properties**
| Property | Type | Example |
|----------|------|---------|
| Name | Text | "10 hooks from one idea" |
| Category | Select | Idea / Hook / Caption / Script / Repurpose / Voice |
| Platform | Multi-select | All / Instagram / LinkedIn |
| Prompt | Text | The copy-paste text |
| When to use | Text | "Sprint Step 3" |

**Templates**
- **New Prompt** — Name, Category, Prompt body, When-to-use note.

**User workflow**
1. At each sprint step, open the matching category.
2. Copy the prompt, fill the `[BLANKS]`.
3. Paste into the AI tool, bring the output back into the workspace.

---

## 6. Swipe File Database

**Purpose**
A bank of proven examples and fill-in-the-blank templates for instant inspiration on stuck days.

**Layout**
- Default view: **Gallery** (visual cards).
- Filters: *By Format*, *Favorites*.

**Databases**
`Swipe File`.

**Properties**
| Property | Type | Example |
|----------|------|---------|
| Title | Text | "Listicle hook template" |
| Format | Select | Hook / Caption / Carousel / Script |
| Template | Text | "[Number] ways to [result] without [pain]" |
| Example | Text | A real filled-in version |
| Platform | Multi-select | Instagram, X |
| Favorite | Checkbox | ⭐ |

**Templates**
- **Swipe Entry** — Title, Format, Template, Example.

**User workflow**
1. Stuck during writing? Open Swipe File.
2. Grab a template, fill the blanks (or feed it to AI).
3. Save the result into `Content Pipeline`.

---

## 7. Repurposing Tracker

**Purpose**
Turn one piece of content into many. Ensures every idea is squeezed across platforms.

**Layout**
- Default view: **Board by Status** (To Repurpose → In Progress → Done).
- Secondary: *By Source* (grouped by original post).

**Databases**
`Repurposing Tracker`.

**Properties**
| Property | Type | Example |
|----------|------|---------|
| Original | Relation → Content Pipeline | "5 money myths" |
| New Format | Select | Reel / Thread / Carousel / Newsletter |
| Platform | Multi-select | TikTok, X |
| Status | Select | To Repurpose / In Progress / Done |
| Notes | Text | "Cut to top 3 points" |

**Templates**
- **Repurpose Set** — picks one Original, adds 3 New Format rows (Reel, Thread, Carousel).

**User workflow**
1. After a post is **Ready/Posted**, add it as an Original.
2. Spin up a Repurpose Set (3 formats).
3. As each is made, push it back to `Content Pipeline` and mark **Done**.

---

## 8. Publishing Calendar

**Purpose**
See the whole week at a glance and confirm every day is covered. The "is my week actually scheduled?" check.

**Layout**
- **Calendar view** of `Content Pipeline`, filtered to **Status = Ready or Posted**.
- Color-coded by Platform.
- Optional toggle for a **Board by Post Date** view.

**Databases**
No new database — a **view** of `Content Pipeline` on the `Post Date` property.

**Properties**
Uses `Content Pipeline` properties (Post Date drives placement; Platform drives color).

**Templates**
None (inherits Content Pipeline templates).

**User workflow**
1. Sprint Step 5: drag Ready items onto their Post Dates.
2. Scan the week — fill any empty days.
3. After posting, items flip to **Posted** automatically by status.

---

## How it all runs in 90 minutes

```
Dashboard → Start Sprint
   │
Weekly Sprint Dashboard (the 5 steps):
   1. Set week        → set Theme + Platforms
   2. Ideas (15m)     → Prompt Library → Research Hub
   3. Write (35m)     → Content Pipeline (templates + prompts)
   4. Polish (20m)    → Voice prompt + Swipe File
   5. Schedule (10m)  → Publishing Calendar
   │
Repurposing Tracker → stretch the best pieces further (optional)
```

**Minimal by design:** 5 databases, one home, one sprint page. The Publishing Calendar reuses the Content Pipeline, so nothing is duplicated and there's nothing extra to maintain.
