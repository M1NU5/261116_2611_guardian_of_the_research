# 🛡️ Guardian of the Research (GotR)

### Your research. Your realm. Your quest.

**Guardian of the Research (GotR)** is a gamified research environment concept built around an **Obsidian vault**. Its goal is to make the journey from reading an academic paper to developing connected, reusable research knowledge more structured, navigable and engaging.

Imagine research projects as **worlds**, goals as **quests**, work packages as **missions**, and individual tasks as **objectives**. The **Codex** is the growing body of literature notes, concepts and insights that supports those quests.

> **Project status:** Starter Edition in development. The workflow below describes the intended approach; it does not imply that all templates, integrations, dashboards or automation are already included. Check the repository and Releases page for what is actually available.

## 📚 From a paper to a connected research knowledge base

GotR's intended research pipeline connects **Zotero**, **structured literature extraction**, **Obsidian**, and the **Zettelkasten method**:

```text
Discover and collect academic literature
                ↓
Read, annotate and colour-highlight in Zotero
                ↓
Extract evidence using the 11-part literature skeleton
                ↓
Import/create a structured literature note in Obsidian
                ↓
Write atomic, linked Zettelkasten notes in your own words
                ↓
Connect concepts, papers and questions with [[wikilinks]]
                ↓
Explore relationships using Obsidian Graph View and backlinks
                ↓
Synthesize evidence into arguments, research questions and outputs
```

### 1. Read and mark up the source in Zotero

Use [Zotero](https://www.zotero.org/) to collect bibliographic metadata and PDFs, read each paper, highlight relevant passages and attach your own comments. Use consistent highlight colours or tags to indicate the extraction category of each passage. Preserve source metadata and page references so you can trace claims back to the original paper.

### 2. Extract evidence using the 11-part literature skeleton

The skeleton provides a consistent way to compare papers. A paper will not necessarily contain evidence for every category; leave unsupported fields empty rather than inventing information.

| #   | Category                  | What to capture from each paper                                                                                                                                         |
| --- | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | **Problem**               | The research problem, knowledge gap, motivation, research questions or hypotheses, and why the issue matters.                                                           |
| 2   | **Constructs**            | Key concepts or variables, definitions, conceptual boundaries, relationships, and how constructs are distinguished from one another.                                    |
| 3   | **Theoretical Lens**      | Theories, models and conceptual frameworks used to explain the phenomenon; the role each theory plays in the argument.                                                  |
| 4   | **Mechanisms**            | Proposed causal or explanatory processes: *how* and *why* an intervention, context or condition may produce an outcome. Distinguish tested mechanisms from speculation. |
| 5   | **Intervention**          | The system, interface, game mechanic, treatment, policy or design change being introduced; its components and comparison condition, if any.                             |
| 6   | **Context**               | Setting, participants, population, tasks, technologies, organisation, domain and other circumstances affecting transferability.                                         |
| 7   | **Methods**               | Research design (e.g., experimental, observational, qualitative or mixed methods), sampling, procedure, data collection and analysis methods.                           |
| 8   | **Measures**              | Instruments, operational definitions, dependent and independent variables, scales, behavioural indicators, and evidence of validity or reliability.                     |
| 9   | **Results**               | Findings, direction and magnitude of effects where reported, statistical or qualitative evidence, and whether hypotheses were supported.                                |
| 10  | **Limitations & Quality** | Author-reported limitations, methodological weaknesses, threats to validity, bias, evidence quality and limits on generalisation.                                       |
| 11  | **Relevance**             | Why the source matters to your own research questions, which arguments it supports or challenges, how it relates to other sources, and what to investigate next.        |

**Recommended annotation practice:** Capture the relevant quote or paraphrase, its page number, your interpretation and the applicable skeleton category. Clearly separate the author's claims from your own analysis. The skeleton is an extraction aid, not a substitute for critical reading.

### 3. Turn Zotero annotations into Obsidian literature notes

Create **one literature note per paper**, ideally using a consistent template. Include the paper title, authors, year, citation key, DOI/URL, Zotero link, a concise key point, and the 11 extraction headings. Under each heading, record the evidence and your commentary, with page citations where possible.

Zotero-to-Obsidian importing can be supported by community tools or templates, but **automatic import and colour-preserving annotation conversion are not guaranteed** in this Starter Edition. Consult the vault's plugin instructions and verify the output against the source PDF.

Example structure:

```markdown
---
title: "Example Paper"
authors: ["Author, A."]
year: 2026
citation-key: "author2026example"
doi: ""
tags: [literature-note]
---

# Literature Note — Author (2026) Example Paper

## Key Point
A brief statement of the paper's central contribution.

## 1. Problem
## 2. Constructs
## 3. Theoretical Lens
## 4. Mechanisms
## 5. Intervention
## 6. Context
## 7. Methods
## 8. Measures
## 9. Results
## 10. Limitations & Quality
## 11. Relevance

## Connected Ideas
- [[Concept — Distributed Cognition]]
- [[Concept — Interaction Costs]]
```

### 4. Develop understanding with Zettelkasten

**Zettelkasten** is a method of building a network of small, connected notes rather than accumulating isolated summaries. In GotR, a **literature note** records what a source says; a **permanent or concept note** develops *one reusable idea in your own words* and links it to supporting or contrasting evidence.

For example, a literature note might describe a study's findings about context switching. A separate note titled `[[Concept — Context Reconstruction Cost]]` could explain your interpretation, cite several papers and connect to `[[Concept — Distributed Cognition]]` and `[[Concept — Attention Residue]]`.

Useful habits:

- Make each permanent note understandable on its own and focused on one idea.
- Explain **why** two notes are linked; don't add links merely because keywords match.
- Keep bibliographic evidence traceable to its source and page.
- Use index or *map-of-content* notes to navigate developing arguments.
- Revise and connect notes as understanding evolves, rather than treating notes as static archives.

### 5. Explore relationships with Graph View

Obsidian's **Graph View** visualises internal links between notes; **Local Graph** focuses on a selected note's neighbourhood. Use `[[wikilinks]]` to connect literature notes, permanent notes, theoretical constructs, research questions and synthesis notes. Backlinks help reveal where an idea is referenced.

The graph is a **navigation and sense-making aid**, not proof that two ideas are scientifically related. Meaningful links and explanatory notes are more important than the number of connections.

## 📊 Research planning dashboard and Kanban

Guardian of the Research also supports a planning workflow using an **Obsidian dashboard** and **Kanban boards**. These provide an operational view of research alongside the Zotero → literature notes → Zettelkasten → Graph View knowledge workflow. The exact dashboard layout, board names and automation depend on the vault files and installed plugins; verify them in your downloaded edition.

### Planning dashboard — your research command centre

1. Open the dashboard or home note supplied with the vault (look for a note labelled **Dashboard**, **Home** or **Start Here**).
2. Review your active research **Worlds** (projects), **Quests** (goals), **Missions** (work packages), deadlines and upcoming **Objectives** (tasks), where the dashboard provides these views.
3. Identify the most important next objective and open its linked note or Kanban card.
4. Link planning items to relevant literature notes, concept notes and research questions using Obsidian `[[wikilinks]]`.
5. Return to the dashboard at the start and end of each research session to plan work and record progress.

> If the dashboard is missing or a widget is blank, check the vault's supplied dashboard notes, any linked paths, and the required community plugins. Dashboard widgets are not native to every Obsidian installation.

### Kanban — move research work from idea to completion

1. Open a supplied Kanban board, if present. If none is included, install and enable the **Kanban** community plugin after reviewing its permissions, then create a board from the plugin's command or ribbon action.
2. Organise cards into columns such as **Backlog → To Do → In Progress → Review → Done**. These are suggested stages, not confirmed existing board columns.
3. Create a card for a concrete objective, such as *Extract mechanisms from Paper A*, rather than an entire research project.
4. Add a link to the relevant note, e.g. `[[Literature Note — Paper A]]`, and include a due date or priority if your board configuration supports it.
5. Drag the card between columns as the work progresses. Use **Review** for work needing verification, such as checking Zotero citations against the source PDF.
6. When complete, update the linked research note or quest so that progress is recorded in the knowledge base, not only on the board.

**Example:** World = *PhD Literature Review* → Quest = *Establish theoretical foundations* → Mission = *Review distributed cognition literature* → Objective/Kanban card = *Extract the 11 skeleton categories from a selected paper*. The completed extraction becomes a literature note, then informs linked Zettelkasten concept notes and your graph.

### Dashboard vs Kanban vs Graph View

| Tool | Main question | Best use |
|---|---|---|
| **Dashboard** | What should I focus on now? | Overview of projects, goals, deadlines and progress |
| **Kanban** | What stage is each task at? | Visual planning and execution of research objectives |
| **Graph View** | How are my ideas and sources connected? | Navigating links between evidence, concepts and questions |
| **Zettelkasten notes** | What do I understand and how does it connect? | Building reusable arguments in your own words |

## 🌍 The Research Realm

| Research activity | RPG concept |
|---|---|
| Research projects | Worlds |
| Research goals | Quests |
| Work packages | Missions |
| Individual tasks | Objectives |
| Unexpected work | Side quests |
| Milestones | Achievements |
| Research notes and sources | Codex |

## ⚔️ Starter Edition — Installation and getting started

The Starter Edition is intended to be used as an **Obsidian vault** on Windows, macOS or Linux.

### 1. Download and install Obsidian

1. Visit [obsidian.md/download](https://obsidian.md/download).
2. Download and install the version for your operating system.
3. Launch Obsidian. A local vault does not require a paid Obsidian Sync or Publish subscription.

### 2. Download Guardian of the Research

1. On this repository's main GitHub page, select **Code → Download ZIP**.
2. Extract the ZIP to a permanent folder such as `Documents/Guardian-of-the-Research`.
3. Locate the folder containing the vault's `.md` notes and, if supplied, its `.obsidian` configuration directory. **That folder is the vault root.**
4. If a ready-to-use vault ZIP is available under **Releases**, prefer it to the source-code ZIP.

> A ready-to-use vault release has not been confirmed by this README. If the repository contains no vault notes or configuration, the Starter Edition is not yet ready for installation.

### 3. Open the folder as an Obsidian vault

1. In Obsidian, select **Open folder as vault**, or open the vault switcher → **Manage vaults** → **Open folder as vault**.
2. Select the extracted **vault root folder**, not the ZIP file.
3. Review any trust or security prompt before opening an unfamiliar vault.
4. Check that the notes appear in the file explorer. If you see only a README, check whether you selected an outer extraction folder.

### 4. Enable core and community plugins

1. Open **Settings → Core plugins**. Enable features used by your vault, such as **Backlinks**, **Graph view**, **Templates** and **Canvas**, as appropriate. (Some features may already be enabled.)
2. Open **Settings → Community plugins**. Review the security implications before enabling community plugins.
3. Select **Browse**, then **Install** and **Enable** each *documented* dependency.
4. If `.obsidian/community-plugins.json` is included, treat it as a list of previously enabled plugin IDs, not evidence that plugins are installed, compatible or safe.
5. Follow any supplied plugin-specific configuration instructions, and restart Obsidian if required.
6. **Install and enable the Kanban community plugin** before attempting to open the training board. Confirm that it appears under your enabled community plugins.

**Dependency status:** The exact GotR community-plugin list, supported versions and settings have not yet been verified. They must be documented before a reproducible Starter Edition release. Zotero integration and automated annotation importing may require additional plugins and templates.

### 5. Start your guided training in Kanban

1. **Now that the Kanban plugin is enabled**, open `[[GotR-Onboarding-Kanban]]` in the vault. If the board is not supplied, download **GotR-Onboarding-Kanban.md** from the repository and place it in the vault.
2. Start with **Explore the Dashboard** and **Learn Kanban**; complete the checklists and move their cards to **Done**.
3. Follow the remaining cards in order to learn Zotero annotation, literature-note importing, editing the **Key Point**, Zettelkasten linking and Graph View.
4. Use the sections below as reference instructions while completing the guided cards. **Do not start the onboarding board before finishing Steps 1–4 above.**

### 6. Set up Zotero and your first literature note

1. Install [Zotero](https://www.zotero.org/) if you do not already have it.
2. Add an academic paper and its PDF, then read and highlight passages against the 11 skeleton categories.
3. In Obsidian, open the supplied literature-note template, if available; otherwise create a new note using the example above.
4. Transfer source metadata, annotations, page references and your comments into the corresponding headings. If an import plugin is configured, review its generated note for accuracy.
5. Write a short **Key Point** summarising the paper's main contribution.
6. Create at least one separate concept note in your own words and link it to the literature note.
7. Open **Graph View** and **Backlinks** to inspect the new connections.

### 7. Begin your first quest

1. Open a **Start Here**, **Home**, **Dashboard** or introductory note, if one is included.
2. Create your first research **World** (project) and **Quest** (goal).
3. Break it into a **Mission** (work package) and a concrete **Objective** (next task).
4. Link relevant literature and concept notes from the **Codex** to that quest.
5. Open your Kanban board (if supplied), create an objective card and move it through your workflow. Use the dashboard to review priorities and progress. If either feature is missing, follow the planning setup instructions above; game mechanics may still be planned features.

### 8. Use the dashboard and Kanban together

1. Start the day on the dashboard and select a priority Quest.
2. Open the corresponding Kanban board and choose the next Objective.
3. Work in Zotero and Obsidian, capturing evidence in the 11-category literature note.
4. Link emerging ideas in Zettelkasten notes and inspect Graph View.
5. Move the Kanban card to Review or Done, and return to the dashboard to plan the next session.

### 9. Updates and troubleshooting

- **Empty vault:** Confirm you selected the folder containing the `.md` files.
- **Missing dashboard or button:** Check documented plugin dependencies, linked note paths and whether that feature has actually shipped.
- **Onboarding board missing:** Confirm `GotR-Onboarding-Kanban.md` is included in your vault, and check that the internal link matches its filename.
- **Kanban board opens as plain Markdown:** Check whether the Kanban community plugin is installed and enabled, and whether the note was created as a Kanban board.
- **Missing Zotero highlights:** Check the import plugin/template configuration; otherwise transfer them manually.
- **No graph connections:** Add meaningful internal links such as `[[Concept — Distributed Cognition]]`.
- **No sync across devices:** Local vaults do not automatically sync; configure a separate sync solution if needed.
- **Updating GotR:** Back up your vault first. Review incoming files carefully to avoid overwriting your notes or `.obsidian` settings.
- **Reporting problems:** Open a GitHub Issue with your operating system, Obsidian version, relevant plugins and steps to reproduce.

## ☕ Support the Guardian's Quest

Guardian of the Research is intended to be accessible as a free starter project. If you find the idea useful and would like to support continued development, you can make a voluntary contribution.

### [☕ Fuel the Guardian's Quest](https://buy.stripe.com/6oU9ATbSx4PD2b83jl6wE00)

**Choose your own contribution amount.** Payments are processed through Stripe. Contributions are optional and do not purchase features, access or research participation. The Starter Edition is intended to remain free, with no strings attached.

## 🗺️ Roadmap

The roadmap is provisional. Items below are **planned**, not claims of implemented functionality.

### Phase 1 — Starter Realm: Obsidian foundation

- [x] Publish **Starter Edition v1.0.0.0** with a documented, downloadable vault.
- [x] Ship and document the 11-category literature-note template and Zotero annotation workflow.
- [ ] Provide reproducible community-plugin dependency and configuration instructions.
- [ ] Include starter Worlds, Quests, Missions, Objectives and Codex examples.
- [x] Package and document a working planning dashboard and sample Kanban board, including their plugin dependencies.
- [x] Include `Kanban.md` with guided quests covering dashboard, Kanban, Zotero import, the literature-note Key Point, Zettelkasten and Graph View.
- [ ] Provide sample Zettelkasten concept notes, maps of content and Graph View navigation.

### Phase 2 — Knowledge Weaving: connected research

- [ ] Improve Zotero → Obsidian import, preserving citations, page numbers, annotation categories and comments where supported.
- [ ] Build better navigation between papers, concepts, research questions and evidence.
- [ ] Enhance research progress dashboards and guided workflows, including links between Kanban cards, goals and literature notes.
- [ ] Explore game-informed feedback, achievements and persistent quest state.

### Phase 3 — Systematic Research: SLR application integration

- [ ] Integrate a **Systematic Literature Review (SLR) application** with GotR, initially through a documented import/export interface or API.
- [ ] Create and version review protocols, research questions, search concepts, eligibility criteria and search strategies.
- [ ] Connect supported academic search providers (subject to API access and licensing) and record search dates, queries and sources.
- [ ] Import bibliographic records, deduplicate studies and retain an auditable identification trail.
- [ ] Support title-and-abstract screening, inclusion/exclusion/uncertain decisions, reasons and reviewer oversight.
- [ ] Add full-text eligibility assessment and structured extraction using the 11-part skeleton.
- [ ] Track review progress and generate reproducible screening counts and PRISMA-compatible reporting data where supported.
- [ ] Export included studies, metadata and extracted evidence into Zotero and/or linked Obsidian literature notes.
- [ ] Link the SLR evidence base to Zettelkasten concept notes, research questions and synthesis maps.

**Integration principle:** Keep systematic-review decisions, source provenance and audit trails traceable. Automated or AI-assisted steps should remain reviewable rather than silently replacing researcher judgement.

### Phase 4 — The Research Multiverse: integrated experience

- [ ] Unify research planning, literature discovery, evidence extraction and synthesis in a coherent game-informed interface.
- [ ] Explore goal continuity, context preservation and feedback across research activities.
- [ ] Evaluate usability, cognitive workload and research workflow effectiveness before claiming performance benefits.

## 🤝 Contributing

Ideas, feedback, bug reports and contributions are welcome once the repository is available for collaboration. Use GitHub Issues to suggest improvements or discuss the project direction.

## 📄 Licence

A licence has not yet been specified. Review the repository's licence before assuming permission to reuse or redistribute its contents.

---

*Guard the knowledge. Weave the worlds. Complete the quest.*
