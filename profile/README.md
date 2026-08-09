## Readout

**The document format agents hand back.** Write a fenced block in ordinary
markdown; get a routed diagram, a real chart, or a whole notebook page - as one
self-contained interactive HTML file. No libraries, no coordinates in the source,
no Mermaid.

[![A Readout document: KPI tiles, a table, prose and two routed diagrams in one page](https://raw.githubusercontent.com/readoutlang/readoutlang/main/examples/runbook.doc.dark.png)](https://github.com/readoutlang/readoutlang)

*One markdown file in, one page out. The prose, the tiles, the table and both
diagrams above are the same source - and no line of it mentions a colour or a
coordinate.*

### It goes where your documents already are

|  | |
|---|---|
| **In your markdown** | A ` ```readout ` fence inside an existing `.md` renders with it. Docs, runbooks, ADRs, READMEs - the diagram lives next to the sentence that needed it. |
| **In an AI chat** | Live in the [Playcode](https://playcode.io) agent: the model writes a fence, the reader gets a diagram it can pan, zoom and open full screen - not a picture of one. |
| **In your editor** | A Zed extension highlights the fence as you type it. |
| **On a canvas** | And for the big standalone maps - architecture, data models, 80-edge graphs - the same source renders as an infinite pan/zoom board. |

### The bit that makes it work

You author **structure and meaning**. The renderer owns everything else:
orthogonal arrow routing with obstacle avoidance, port spreading, label
placement, theming for light and dark, reflow, and the axis of every chart.

```readout
section: Lead capture

row:
  visitor[green]: Visitor | submits the form
  api[teal]:      API | validates
  queue[purple]:  Queue | sends the alert

edges:
  visitor -> api : POST /leads
  api -> queue : enqueue
```

That is the whole source for a routed three-step flow. A colour is a semantic
role, never a hex; an arrow is a relationship, never a path. Which is also why
`readout diagram --verify` can prove a rendered page in headless Chromium: every
edge drawn, no arrow through a card, no label covering content.

### Start here

- **[readoutlang](https://github.com/readoutlang/readoutlang)** - the language, the renderer, the CLI, and the OKF docs linter it grew out of
- **[npm i -D readoutlang](https://www.npmjs.com/package/readoutlang)**
- **[Design rules](https://github.com/readoutlang/readoutlang/blob/main/BEST-PRACTICES.md)** - what the renderer encodes, and which knob to reach for when a diagram reads badly
