<div align="center">

<img src="client/src/assets/manor-rosewood.jpg" alt="The Last Testament — Rosewood Manor, Case File 001" width="100%" />

# THE LAST TESTAMENT

### *An inheritance. A murder. Six files to uncover the truth.*

**ROSEWOOD MANOR · CASE FILE 001**

[About](#about) · [How It Plays](#how-it-plays) · [Features](#features) · [Tech Stack](#tech-stack) · [Setup](#setup) · [Quality Checks](#quality-checks)

</div>

---

## EVERY FAMILY HAS SECRETS

## About

**The Last Testament** is a scenario-driven Python learning game wrapped in a gothic murder mystery.

You play the detective. Your task is to solve a six-part case at Rosewood Manor by examining clues, following timelines, questioning alibis, and narrowing down the suspects. Each case file teaches an underlying Python idea through short, interactive slides and multiple-choice questions. When a file closes, the Python behind the investigation is revealed and explained line by line in plain language.

The experience is designed for beginners, including learners with no prior coding background.

- No login or account required.
- No external database.
- No external AI service or API key.
- Learning logic is deterministic and runs locally.

## How It Plays

The investigation unfolds across six connected case files:

1. **The Case Opens** — enter Rosewood Manor and discover the crime.
2. **The Notes** — examine the first pieces of evidence.
3. **The Timeline** — arrange events and understand when they happened.
4. **The Alibis** — compare each suspect's account with the evidence.
5. **Narrowing It Down** — connect the clues and eliminate possibilities.
6. **The Reveal** — identify the culprit and close the case.

### The gameplay loop

- **Onboarding:** three short screens introduce the experience, then the case begins.
- **Case files:** each file contains short slides and one question at a time.
- **No typing:** every interaction is multiple choice, with instant feedback and a retry after an incorrect answer.
- **Fair answer placement:** correct options are shuffled across A–D.
- **Plain language:** explanations are written for a first-year student. Concept names remain hidden until the relevant file is complete.
- **Code reveal:** after a file closes, its Python code appears with a plain-language comment on every line.
- **Suspect Board:** five initially unnamed slots reveal suspects as the story introduces them. Their rankings change as clues arrive; cleared suspects move to a Cleared drawer, and the final culprit reaches 100/100.
- **Ledger:** a case notebook records the concepts learned after each completed file.

## Features

- **Six-part chained case:** the new Advanced tier links scenarios through `storyId`, `order`, and `nextScenarioId`, replacing the previous standalone scenarios.
- **Slide-based learning:** short, visual, multiple-choice interactions instead of long blocks of text.
- **Light and dark themes:** a haunted-mansion dark theme with lightning effects and a daylight counterpart.
- **Onboarding and navigation:** guided introduction, sidebar case navigation, and visible progress.
- **Local progress:** progress and theme preferences are saved in browser `localStorage`.
- **Dynamic Suspect Board:** board state is driven by hand-authored clue events and a pure `computeBoard` function.
- **Case bible:** one source of truth for the victim, suspects, witnesses, clues, times, and rooms, validated by an audit script.
- **Concept-driven code generation:** each case file generates Python code that matches the idea taught in that file.
- **Visual storytelling:** supplied manor and suspect photos are used throughout the experience.

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React + Vite |
| Backend | Node.js + Express |
| Storage | Local JSON-file storage |
| Browser persistence | `localStorage` |
| Database | None |
| Authentication | None |
| External AI | None |

## Setup

### Requirements

- Node.js 18 or later
- npm

### Installation

```bash
npm run installAll
cp server/.env.example server/.env
npm run seed
npm run dev
```

### Local development URLs

| Service | URL |
|---|---|
| Frontend | [http://localhost:5173](http://localhost:5173) |
| API | [http://localhost:5000/api](http://localhost:5000/api) |

## Quality Checks

The project includes scripts for checking content, presentation, story consistency, and application behaviour.

Run `npm run` inside the `client/` and `server/` directories to see the scripts available in each package.

The checks include:

| Script | Purpose |
|---|---|
| `audit:text` | Checks text length, plain-language wording, and banned terms |
| `audit:colors` | Checks colour usage |
| `audit:answers` | Checks the spread of correct answer positions |
| `audit:story` | Checks story and case consistency |
| `audit:type` | Checks type-related constraints |
| `smoke` | Runs smoke checks |

Run each script from the package where it is defined.

## Project Structure

```text
.
├── client/
│   └── React application
│       ├── Slides and case-file flow
│       ├── Suspect Board
│       ├── Ledger
│       └── Themes
│
└── server/
    ├── Express API
    └── src/
        ├── data/
        │   └── JSON storage and case data
        └── services/
            └── learningEngine.js
                └── Concept-driven Python code generation
```

## Design Principles

- **Story first:** learners experience a mystery rather than a conventional lesson.
- **Learn by reasoning:** each question asks the player to apply an idea before seeing its formal name.
- **Explain the code:** generated Python is paired with plain-language comments.
- **Keep it accessible:** no coding background, typing, login, or external service is required.
- **Make progress visible:** completed files, the Suspect Board, and the Ledger make the investigation feel continuous.

## Notes & Limitations

- Progress and theme preferences are stored in the browser's `localStorage`; they do not sync across devices or browsers.
- The server uses local JSON-file storage rather than a database.
- All learning logic is deterministic and local. The application does not make external AI calls.
- The project requires Node.js 18 or later.

---

<div align="center">

### Dive into the mystery. Learn Python. Solve the case.

*THE LAST TESTAMENT · ROSEWOOD MANOR · CASE FILE 001*

</div>
