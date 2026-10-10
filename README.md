# FORMALQ — Interactive Demo (macOS)

This bundle contains what has been built so far:

- `index.html` — the interactive FORMALQ black-glass dashboard demo (single file, no dependencies, works offline)
- `FORMALQ-build-prompt.md` — the full project specification for the complete Next.js + Supabase app (NOT yet built)

## Run it on your MacBook

Option 1 (simplest): double-click `index.html`, or in Terminal:

    cd formalq-demo
    open index.html

Option 2 (local server, works the same):

    cd formalq-demo
    python3 -m http.server 8000

Then open http://localhost:8000 in your browser.

## What the demo does

- Navigation: Overview, My Forms, Create with AI, Analytics, Settings, Sign out
- Create forms, edit questions (add, copy, delete, reorder, change type, set options)
- Generate questions from a topic, then answer them and submit a response
- Publish/unpublish, duplicate, archive, delete, copy link, preview
- Analytics for your submitted answers, CSV export (shown as copyable text)

## Important limits

- Demo only: data lives in memory and resets on refresh.
- No database, no login system, and no AI is called. "Generate" builds template questions locally.
- Links like formalq.example are placeholders.
- The full app (Next.js, Supabase, real AI, auth, RLS) described in FORMALQ-build-prompt.md has not been built.
