# All Izz Connected

Slide deck for the guest lecture "All Izz Connected: Advanced Graph Algorithms". 39 slides, about 76 minutes.

It's plain HTML, CSS and JavaScript, with no build step and no dependencies. Fonts are bundled in `fonts/` and every image is embedded inside `index.html`, so the deck works fully offline.

## Run it

- **Quickest:** double-click `index.html` to open it in Chrome or Edge.
- **While editing in VS Code:** install the *Live Server* extension, right-click `index.html`, and choose **Open with Live Server**. The page reloads every time you save.

## Presenting

| Key | Action |
|---|---|
| → / Space / click | Next slide or next reveal |
| ← | Back |
| N | Speaker notes |
| O | All slides (jump anywhere) |
| B | Blackout screen |
| F | Fullscreen |

To open a specific slide, add `#s12` to the end of the URL (that example opens slide 12).

## The running order

| Slides | Section |
|---|---|
| 1–7 | Opening: Kitne Nodes The, Graphs are everywhere, title, who am I, let's connect, before breakfast, agenda |
| 8–19 | Reel 1 · 2 States: cyclic/acyclic, graph types, storing a graph (matrix vs list), BFS vs DFS + demos |
| 20 | Interval: ask me anything (not graphs) |
| 21–26 | Reel 2 · Chennai Express: Dijkstra (pronunciation, story, race, idea + TypeScript code, step-by-step demo), A* teaser |
| 27–30 | Reel 3 · 12th Fail: intro, Tarik pe tarik, topological sort line-up animation, Kahn's algorithm demo |
| 31–34 | Reel 4 · Fan: intro, Rahul meme, PageRank explainer animation, live demo |
| 35–37 | Reel 5 · Robot: graphs in AI intro, AI agent workflow, graph neural networks |
| 38–39 | Climax: end credits, Mogambo Q&A |

## Where things live in `index.html`

| What | Where |
|---|---|
| Colours, fonts, type sizes | `:root { ... }` at the top of the main `<style>` |
| Slides | One `<section class="slide">` per slide, in order. `data-title` is the name shown in the overview (O); `data-reel` is the label in the bottom bar; `data-reelstart` marks the first slide of a reel. |
| Speaker notes | `<aside class="notes">` inside each slide |
| Click-to-reveal lines | Any element with `class="frag"` |
| Time-complexity badges | `<p class="cx">` blocks |
| Meme / photo images | `<img src="data:image/jpeg;base64,...">` inside `<figure>` tags (embedded, so they're long lines) |
| Interactive demos and animations | In the main `<script>`: `hopRace` (BFS vs Dijkstra race), `demoTree` / `demoTrav` (BFS/DFS), `demoDij` (Dijkstra step-by-step), `demoRace` (Dijkstra vs A*), `topoAnim` (topological sort line-up), `demoKahn`, `prVideo` (PageRank explainer), `demoPR` (PageRank live), `agentFlow` (AI agent), `gnnDemo` (GNN), `pictures` (static diagrams), `stars` (title-slide background) |
| Spinning reel countdown | `.mini-leader` in the CSS. Add `keep-spinning` to a slide's class to keep it spinning while that slide is shown. |

## Swapping an image for a file

Images are embedded as base64 so the deck is a single file. To use a file instead, put it in an `images/` folder next to `index.html` and change the `src`, e.g. `<img src="images/gabbar.jpg">`.

## Adding a slide

Copy an existing `<section class="slide" ...>` block, paste it where the slide should go, and edit it. Slide numbers, the overview and the progress bar update automatically.
