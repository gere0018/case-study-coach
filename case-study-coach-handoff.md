# Case Study Coach: handoff

## What this is
An interactive prototype that helps an early-career product designer (Sam) write an honest case study. One file: `case-study-coach.html` (self-contained, no build step).

Flow: Start (paste notes, Figma link, or from scratch) → Interview (one question at a time, live preview, progress and open gaps) → Hiring-manager check (top 3 gaps, each linked to the fixing question) → Final case study (edit, copy, download .md).

Honesty rules built in: the coach never invents metrics, outcomes, decisions or quotes. Quotes pulled from notes must exist in the notes, and any number in a generated preview must already appear in what Sam wrote, or the page falls back to Sam's own words.

## Republish from another Claude account
1. Open a new chat in the other account (a Project is optional).
2. Attach `case-study-coach.html`.
3. Paste this prompt:

> Publish the attached HTML file as an artifact exactly as it is. Don't rewrite or restyle it. Declare the runtime capabilities `sample` (so the page can ask Claude) and `downloads` (so "Download .md" works). Title it "Case Study Coach". Then give me the link.

4. Open the link, run the coaching once (the viewer is asked to allow Claude), and check that the notes example reads correctly.

Notes:
- The coaching, previews and review run on the viewer's own Claude account and usage. Outside Claude the page falls back to basic checks, and reading notes is unavailable.
- An artifact link can't be opened from a different organization's account. Always move the HTML file, not the link.
- Progress is saved per browser. Use "Start over" between test participants.

## Hosting it outside Claude (optional)
The HTML works on any static host, but the live Claude calls won't. You'd need a small server that holds an Anthropic API key and answers three requests (answer coaching, notes reading, hiring-manager review), plus a consent line about where notes go. Add rate limits, because you pay for each tester's usage.

## Design system
Dark turquoise system from the workshop Figma file. Local variable collection: "Case Study Coach · Tokens".

| Token | Value |
|---|---|
| bg | #0A0D14 |
| rail | #0D1119 |
| raised | #232A36 |
| sunken | #141A24 |
| ink | #F7F9FC |
| muted | #9BA5B4 |
| line / line-strong / field | #363E4C / #5B6577 / #7C8799 |
| accent / on-accent | #00E5FF / #0A0D14 |
| amber / amber-ink / amber-line | #FFC44D / #FFD98A / #C99A3B |
| violet / violet-ink | #8F80DA / #DAD3FF |
| red | #FF9DA8 |
| frame | #A2EBF4 |

Type: Fraunces SemiBold for headlines, Nunito for body. Radii: 18 for cards, fully round for buttons and pills. All text and control pairings checked against WCAG 2.1 AA.

## Figma references (personal file `NXBqMrgDHdZX3m9YKbsozR`)
- Interview first wireframe: https://www.figma.com/design/NXBqMrgDHdZX3m9YKbsozR/AI-Native-Product-Design--Nehmat-?node-id=4037-302
- Structure first wireframe: https://www.figma.com/design/NXBqMrgDHdZX3m9YKbsozR/AI-Native-Product-Design--Nehmat-?node-id=4037-155
- Feedback first wireframe: https://www.figma.com/design/NXBqMrgDHdZX3m9YKbsozR/AI-Native-Product-Design--Nehmat-?node-id=4037-3
- 12 hi-fi screens and design tokens: https://www.figma.com/design/NXBqMrgDHdZX3m9YKbsozR/AI-Native-Product-Design--Nehmat-?node-id=4068-21

## The 12 screens
01 Start · empty · 02 Start · paste notes · 03 Notes too thin · 04 Notes readout · 05 Interview · question · 06 Needs evidence · 07 Your part is unclear · 08 Notes disagree · 09 No outcome data · 10 Hiring-manager check · 11 Final case study · 12 Save and return

## Assumptions
1. Progress is saved in the browser, on one device, for one case study at a time.
2. The nine questions and their prompts are a draft and haven't been tested.
3. Completeness gives half credit to thin or unsupported answers and full credit to an honest "no data" answer. It is a coaching signal, not a score.
4. The case study is written in first person.
5. Testers use their own real project.
6. Reading a Figma link is simulated with sample content (a transit ticketing redesign). Links containing "private" show the can't-open state.
7. Dark only, per the design system.

## What to test first
1. Do testers start from nothing, notes, or an old draft, and does answering nine questions feel like help or like a slow form?
2. Do testers trust the evidence flags and the "I don't have this data" path, or skip them?
3. Would they submit the finished case study to a real application, and what would they change first?
