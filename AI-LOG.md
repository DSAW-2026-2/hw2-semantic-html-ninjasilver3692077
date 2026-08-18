# AI Log — HW02: Semantic HTML (PlayReal)

## Which parts were AI-generated

AI (Claude) was used to help draft the full semantic HTML structure of `index.html`, including:

- The overall page skeleton (`header`, `nav`, `main`, `section`, `article`, `footer`).
- The written content for the Project Overview, Problem, Web App Justification, Target Users, Main User Flow, and User Stories sections, based on the PlayReal project description.
- The Interest Form markup (`<form>`, `<input>`, `<label>` pairs, `<button>`).
- The Team Roles and AI Log sections themselves.
- The `<figure>` / `<figcaption>` markup used to present the Figma wireframe image.

## What I had to fix and why

- **Removed all CSS and JavaScript.** The first draft focused on content and structure; I manually verified there was no `<style>`, `style="..."`, `<link rel="stylesheet">`, `<script>`, or `on*` event attribute anywhere, since HW02 evaluates structure only.
- **Enforced a single `<h1>` and a clean heading hierarchy.** I checked that only one `<h1>` exists (the project title), that every section uses `<h2>`, and that `<h3>` is only used inside `<article>` elements nested under their corresponding `<h2>` — with no skipped levels.
- **Connected every form label to its input.** I verified that each `<label for="...">` matches exactly the `id` of its corresponding `<input>` (`student-name`, `student-email`, `group-name`, `invite-code`, `account-password`).
- **Added a descriptive `alt` attribute to the wireframe image**, describing what the image actually shows (the PlayReal Home wireframe with the active challenge, progress, evidence feed, ranking, and annotations) instead of leaving it empty or generic.
- **Shortened the image `alt` text after running WAVE.** The first WAVE scan on the deployed page (0 errors, 1 alert) flagged **"Long alternative text"** on the wireframe image, since the original `alt` was ~160 characters long. I fixed this by shortening the `alt` to a concise description and relying on the existing `<figcaption>` to carry the fuller description. Re-running WAVE after the fix showed 0 errors and 0 alerts.

## Why these changes were made

These changes were made because HW02 specifically evaluates:
- Correct, meaningful use of semantic HTML5 elements (not `<div>` soup).
- A logical, unbroken heading hierarchy.
- Proper accessibility wiring between form labels and inputs.
- Descriptive, non-empty `alt` text on all images.
- A completely unstyled, script-free HTML skeleton.

Following the WAVE feedback loop (scan → identify flagged issue → fix → re-scan) also matches the Layer 2 requirement of the assignment: run the page through WAVE and fix at least the issues it flags, documenting the before/after result.