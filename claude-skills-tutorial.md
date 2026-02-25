# Claude Skills on claude.ai

## What it is

A Skill is a reusable instruction package you upload once. Claude loads it automatically whenever your request matches. No more pasting the same long prompt every time.

**Requires:** Pro, Max, Team, or Enterprise plan. Code execution must be enabled in **Settings > Customize**.

This tutorial is designed for Claude.ai browser interface, to work more advancely with Claude Skills in Claude Code. [Complete this!](https://anthropic.skilljar.com/introduction-to-agent-skills)

---

## Enable Skills

1. Go to **claude.ai** and click your profile icon, bottom left.
2. Select **Settings**, then **Customize**.
3. Scroll to the **Skills** section and toggle it on.

---

## What a Skill looks like

A Skill is a ZIP file containing a folder. Inside that folder, at minimum, is one file: `SKILL.md`.

That file has two parts. First, a metadata block that tells Claude when to load the skill:

```
---
name: jake-resume-latex
description: Generate a LaTeX resume using Jake's Overleaf template when
             the user asks to convert or update their resume.
---
```

Second, the instructions body: rules for how Claude should behave, what to output, and what to avoid.

Claude reads `name` and `description` first. If your request matches, it loads the full instructions. If not, it ignores the skill entirely.

---

## Upload a Skill

1. Create a folder on your computer. Name it after your skill, e.g. `jake-resume-skill`.
2. Inside it, create `SKILL.md` with your metadata block and instructions.
3. Right-click the folder and compress it to `jake-resume-skill.zip`.
4. In **Settings > Customize > Skills**, click **Upload skill**.
5. Select your ZIP and confirm. The skill appears in your list.

> Common mistake: zipping the contents instead of the folder. The ZIP must contain the folder, not loose files.

---

## Use it: I will give you a walkthrough with the LaTeX Resume Skill

Download my jake-resume-skill.zip in this repo. Please read what is inside too before downloading (for the sake of best pratice)\n

This skill generates a LaTeX resume in Jake's Overleaf template from a PDF or pasted text. [Why LaTeX you may ask?](https://www.reddit.com/r/LaTeX/comments/1noexjg/should_i_use_latex_for_making_a_resume/)

### Trigger it

1. Start a new chat on **claude.ai**.
2. Click the paperclip icon and upload your resume PDF.
3. Type: `Use the jake-resume-latex skill to generate my resume.`
4. Press **Enter**.

Claude reads your PDF, identifies all four sections (Technical Skills, Experience, Projects, Education), and replies with a brief summary followed by a single `latex` code block.

### What Claude returns

A short summary of decisions made:

```
Found 4 sections: Technical Skills, Experience (2 roles), Projects (2), Education.
Trimmed the Zustand workflow bullet from SIY to stay on one page.
Certifications section excluded — add manually if needed.
```

Then the full LaTeX source:

```latex
\documentclass[letterpaper,11pt]{article}
% ... preamble ...

\begin{document}

\begin{center}
    \textbf{\Huge \scshape Thai Tran} \\ \vspace{1pt}
    \small 514-000-0804 $|$
    \href{mailto:minh.thai.tran@mail.mcgill.ca}{\underline{minh.thai.tran@mail.mcgill.ca}} $|$
    \href{https://linkedin.com/in/thai-tran-minh}{\underline{linkedin.com/in/thai-tran-minh}} $|$
    \href{https://github.com/thaimtl}{\underline{github.com/thaimtl}}
\end{center}

% Technical Skills, Experience, Projects, Education follow...

\end{document}
```

### Paste into Overleaf

5. Copy everything inside the code block.
6. Open **overleaf.com** and create a new blank project.
7. Paste the LaTeX into the editor, replacing all existing content.
8. Click **Compile**. Your resume renders as a PDF on the right.

---

## Manage your Skills

- **Toggle** a skill on or off anytime in **Settings > Customize > Skills** without deleting it.
- **Update** a skill by editing `SKILL.md`, re-zipping the folder, deleting the old skill, and uploading the new ZIP.
- **Add more** skills for other tasks. Claude picks the right one based on context.
