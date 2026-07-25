# Codex User Message Contrast Proposal

Long Codex conversations should preserve a clear visual distinction between a user's prompts and the assistant's inline output. The proposed treatment gives user messages a subtle, theme-aware surface while leaving assistant prose unframed and assistant output neutral.

## The Proposal

- Introduce one semantic `user-message-surface` treatment across Codex conversations, tasks, threads, and sessions.
- Derive its subtle fill from the active theme accent, with a standard product accent as the fallback.
- Keep assistant prose unframed and assistant inline output on a neutral surface.
- Treat the tint as sender identity, not as success, warning, or other status meaning.
- Preserve text contrast in dark, light, custom, and high-contrast themes.
- Do not add sender labels, per-message color controls, or backend behavior.

The distinction is deliberately modest at rest but much easier to scan when a conversation contains sparse user prompts between long assistant responses.

## Public Package

- [Interactive prototype](https://h4xofficial.github.io/codex-user-message-contrast-proposal/)
- [One-page UX specification](user-message-contrast-spec.md)
- [Proposed `openai/codex` issue](github-issue-draft.md)
- `user-message-current.png`: current neutral user-message treatment
- `user-message-proposed.png`: proposed theme-aware user-message surface
- `user-message-scroll.png`: proposed treatment during a long-history scroll

Prototype controls:

- **Current** shows the observed neutral treatment.
- **Soft theme tint** shows the proposed semantic user surface.
- **Play scroll demo** runs a one-shot scan through long-form assistant output.

The scroll motion demonstrates the scanning problem; it is not a proposed product animation.

## Evidence Boundary

This proposal is based on a supplied Windows screenshot where a user message and assistant inline output use very similar neutral surfaces. It does not claim that every Codex theme or conversation surface currently uses identical styling.

The mockup uses invented content to demonstrate the issue in a realistic long-form history. The proposed implementation depends only on frontend semantic styling and existing theme tokens.

## Privacy

The supplied screenshot is private reference evidence and is not included. Public assets contain no account name, project name, chat title, payment details, or other personal data.

## Status

Published for public review:

- Repository: [`H4XOFFICIAL/codex-user-message-contrast-proposal`](https://github.com/H4XOFFICIAL/codex-user-message-contrast-proposal)
- Live prototype: [GitHub Pages](https://h4xofficial.github.io/codex-user-message-contrast-proposal/)
- Upstream proposal: [`openai/codex#35369`](https://github.com/openai/codex/issues/35369)
