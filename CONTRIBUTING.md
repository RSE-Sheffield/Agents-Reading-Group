# Contributing to Agents-Reading-Group

## Repo purpose and structure

This repo supports the RSE Agentic Reading Group — a fortnightly session where we read papers, demo tools, and run exercises related to AI agents. The repo has two main areas:

```
sessions/   — planned session content (agenda, background reading, activities)
ideas/      — lightweight proposals for future topics
```

## Adding a session plan

Session files live in `sessions/` and follow this naming convention:

```
sessions/YYYY-MM-DD-short-slug.md
```

Use the session date, not the date you created the file.

### Required sections

Every session file should include:

| Section | Content |
|---------|---------|
| **Overview** | 2–4 sentences on the topic and why it matters now |
| **Background reading** | Ordered list of links to read before the session |
| **Timed agenda** | Table with time blocks, activity, and who leads |
| **Practical activity** | Hands-on exercise for the group (≥15 min) |
| **Discussion prompts** | 4–6 questions to structure the final segment |

See [`sessions/2026-03-31-nemoclaw-openshell.md`](sessions/2026-03-31-nemoclaw-openshell.md) for a complete example.

Once your file is ready, update the Schedule table in `README.md` and open a PR.

## Submitting an idea

The quickest way is to [open a session idea issue](https://github.com/RSE-Sheffield/Agents-Reading-Group/issues/new?template=session-idea.yml) — the form mirrors the idea template. Alternatively, add an idea file via a PR.

Idea files live in `ideas/` and use a simple slug with no date prefix:

```
ideas/short-slug.md
```

1. Copy the template from [`ideas/README.md`](ideas/README.md).
2. Create a new file: `ideas/short-slug.md` (e.g. `ideas/multi-agent-evals.md`).
3. Fill in the title, proposed by, suggested format, why it's interesting, and any relevant links.
4. Open a PR — ideas don't need to be complete or even have a date in mind.

When an idea is ready to become a session, create a file under `sessions/` (following the session naming convention) and open a new PR. You can delete the idea file in the same PR or leave it for reference.

## Previewing Marp slides locally

Some sessions include a `slides.md` file written for [Marp](https://marp.app/). No local install is required — `npx` fetches the CLI on demand. Commands below run from the repo root.

Decks at `sessions/*/slides.md` are built and published to GitHub Pages automatically when changes merge to `main` (see `.github/workflows/slides.yml`), at `https://<owner>.github.io/Agents-Reading-Group/sessions/<session-dir>/`.

Sessions that ship a `slides.css` use a custom theme (e.g. `theme: uos` in the front matter). Pass it with `--theme-set` in every command, otherwise Marp silently falls back to its default theme. Put `--theme-set` **after** the input path: it accepts multiple files, so anything following it is read as another theme.

### Live preview (hot reload)

Point `-s`/`--server` at the **session directory**, not the `slides.md` file itself:

```
npx @marp-team/marp-cli@latest -s sessions/YYYY-MM-DD-short-slug/ --theme-set sessions/YYYY-MM-DD-short-slug/slides.css
```

Then open http://localhost:8080/slides.md — the page reloads whenever you save `slides.md` or `slides.css`.

- Pointing `-s` at the file gives a `"...slides.md" is not directory` error.
- To change the port, set the `PORT` environment variable (e.g. `PORT=8081 npx ...`). `-p` means `--preview`, not port.
- Only one Marp server can run at a time: the live-reload socket uses a fixed port, so a second server fails with `EADDRINUSE`.

### Watch mode

To rebuild `slides.html` automatically on save instead of running a server:

```
npx @marp-team/marp-cli@latest -w sessions/YYYY-MM-DD-short-slug/slides.md --theme-set sessions/YYYY-MM-DD-short-slug/slides.css
```

### Export

To export static HTML or PDF next to the slides (PDF export needs Chrome, Chromium or Edge installed):

```
npx @marp-team/marp-cli@latest sessions/YYYY-MM-DD-short-slug/slides.md --theme-set sessions/YYYY-MM-DD-short-slug/slides.css -o sessions/YYYY-MM-DD-short-slug/slides.pdf
```

### VS Code

With the [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) extension, register the theme in your workspace settings so the built-in Markdown preview (Ctrl+Shift+V) live-updates with it:

```json
"markdown.marp.themes": ["./sessions/YYYY-MM-DD-short-slug/slides.css"]
```

## Branch and PR conventions

- Branch names: `add-<slug>` for new sessions/ideas, `fix-<slug>` for corrections.
- Commit message style: `feat:`, `fix:`, `docs:` prefix (e.g. `feat: add session plan for tool-use evals`).
- PR description: briefly explain what the session/idea covers and why you think it would suit the group.
- One session or idea per PR keeps reviews focused.
