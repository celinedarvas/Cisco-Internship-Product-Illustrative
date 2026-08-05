# Celine Darvas &middot; Portfolio

Three internal tools I designed and built as an intern on a Skills Strategy team.

## What's in here

Each folder is a self-contained static site. No build step, no server, no dependencies. Open any `index.html` directly in a browser and it works.

| Folder | What it is |
|---|---|
| `cs-strategic-capabilities/` | Strategy website for the Customer Success function. Names the 5 capabilities the function is investing in, the 6 signature skills per capability, and the sub-orgs and role families behind each pick. |
| `3p-strategic-capabilities/` | Same design system applied to a second function with different content, pillars, sub-orgs, and priorities. |
| `capability-readiness-tool/` | Gap analysis tool that pulls the 30 signature skills, matches them against ~10,700 people across 43 roles, and ranks capabilities by (demand &times; gap). Includes a chat interface with deterministic answer templates. |

Each artifact carries a portfolio NDA notice at the top: numbers, names, and organisation labels have been changed, but structure, design system, and analytical model mirror the shipped deliverable.

## Tech stack

Vanilla HTML, CSS, and JavaScript. No frameworks. No build tooling. Everything runs as static files via GitHub Pages.

- **Design system**: shared token layer across all three artifacts (colors, spacing, type scale, motion timing). Copied into each artifact so each folder stays independent.
- **Data**: the readiness tool ships a synthetic dataset with the same schema as the production data (roles, skills, capabilities, headcount by region / management level / sub-org). Structure and ratios match the original.
- **Chat**: 12 structured answer templates, deterministic renders. No LLM in the loop. If the user's question doesn't match a template, the tool says so and offers the closest structured question it can answer.

## Local preview

```bash
cd portfolio-public
python3 -m http.server 8000
# open http://localhost:8000/
```

## About the NDA notice

Each site carries a small strip below the header that reads:

> **Portfolio version.** Every number, name, and organisation label in this build has been changed to comply with NDA. Structure, design system, and analytical model mirror the shipped deliverable.

The transformations that produced this portfolio version (name-swap dictionaries, headcount scaling, LOB relabelling) live in a separate local build layer that is not part of this repository.
