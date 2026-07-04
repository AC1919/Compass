# Editing Compass Content (`data.json`) on GitHub

This guide is for team members with **no coding experience**. It explains how to edit the text, links, and resources shown in the Compass tool by editing the `data.json` file directly in GitHub's web browser — no software to install.

---

## 1. Find the file on GitHub

1. Go to the repository on GitHub (your project maintainer will give you the link).
2. Click on the file called **`data.json`** in the file list.
3. On the file page, click the **pencil icon (✏️ "Edit this file")** near the top right. This opens GitHub's built-in code editor.

> 💡 If you don't see a pencil icon, you may not have edit permission yet — ask your admin to add you as a collaborator.

---

## 2. Understand the structure (don't panic — it's just nested boxes)

`data.json` is organized like folders inside folders:

```
app                → overall app name, tagline, footer text
stages             → the 3 main sections (Self, Jobs, Explore)
  └── topics       → the pages inside each section
        └── resources → the clickable cards (name, description, link)
        └── reflects  → the reflection questions
        └── myths     → the "mythbusting" chips
```

Everything is written as `"key": "value"` pairs, separated by commas, and grouped using `{ }` and `[ ]`. You will mostly be editing the **text inside the quotation marks** — you should not need to touch the curly braces `{}`, square brackets `[]`, or commas.

---

## 3. How to edit existing text

Find the line you want to change and edit only what's **inside the quotation marks**.

**Example — changing a resource description:**

Before:
```json
{ "icon": "🎯", "name": "Prospects Job Match", "desc": "Answer questions to match your personality to real job roles", "url": "https://www.prospects.ac.uk/planner" }
```

After (only the `desc` text changed):
```json
{ "icon": "🎯", "name": "Prospects Job Match", "desc": "Take this quiz to see roles that match your personality", "url": "https://www.prospects.ac.uk/planner" }
```

✅ Keep the quotation marks `" "` exactly where they are.
✅ Keep the comma at the end of the line, if there was one before.
🚫 Don't delete the `{ }` around each item or the `[ ]` around each list.

---

## 4. How to update a link (URL)

Find the `"url"` field for the resource you want to update, and replace only the web address between the quotes.

Before:
```json
"url": "#"
```

After:
```json
"url": "https://sheffield.ac.uk/careers/support/services/appointments"
```

📌 **Rules for links:**
- Always start with `https://`
- Never remove the quotation marks around the link
- If a resource has no real link yet, it's set to `"#"` (a placeholder) — replace `#` with the real address when you have it
- For an email link, use the format: `"mailto:careers@sheffield.ac.uk"`

---

## 5. How to add a brand-new resource card

Copy an existing resource block, paste it as a new line inside the same `"resources": [ ... ]` list, and edit the text inside it. Make sure there's a comma between each item in the list (but **not** after the very last one).

```json
"resources": [
  { "icon": "🎯", "name": "Example One", "desc": "First card", "url": "https://example.com" },
  { "icon": "📊", "name": "Example Two", "desc": "Second card", "url": "https://example.com" }
]
```

Notice: every item has a comma after it **except the last one** in the list.

---

## 6. How to add a new reflection question or myth

**Reflection question** — add a new line inside `"reflects": [ ]`, in quotes, with a comma after it (except the last one):
```json
"reflects": [
  "What matters most to you in a working life?",
  "When have you felt most like yourself?"
]
```

**Myth** — add a new `{ }` block inside `"myths": [ ]`:
```json
{
  "chip": "\"Short label shown on the button\"",
  "bust": "The explanation shown when someone taps the myth chip."
}
```

⚠️ Notice the `\"` (backslash + quote) used *inside* the chip text when you want to show quotation marks on screen — this is required so GitHub doesn't think the quote marks are ending the text early.

---

## 7. Save your changes

1. Scroll to the bottom of the GitHub editor page.
2. You'll see a box titled **"Commit changes"**.
3. Write a short, clear message describing what you changed, e.g. *"Updated appointments link and fixed typo in values section"*.
4. Choose **"Commit directly to the main branch"** (or, if your team uses a review process, choose "Create a new branch and start a pull request").
5. Click the green **Commit changes** button.

Your edit is now live (or awaiting review, depending on the option chosen).

---

## 8. Quick checklist before you save

- [ ] Every piece of text is still wrapped in `" "`
- [ ] Every `{` has a matching `}`, and every `[` has a matching `]`
- [ ] Commas appear **between** items, but not after the last item in a list
- [ ] Links start with `https://` (or `mailto:` for emails)
- [ ] I only edited text — I didn't remove or rename any of the field labels (`"name"`, `"desc"`, `"url"`, etc.)

---


