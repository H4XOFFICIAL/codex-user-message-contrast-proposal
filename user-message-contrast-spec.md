# Theme-Aware User Message Surface for Codex Desktop

## Objective

Make a user's own prompts easy to relocate while scanning long Codex conversation histories, without adding visual noise or confusing sender identity with status.

## User Problem

In the observed Windows conversation, user messages and assistant inline output use very similar neutral backgrounds. Right alignment helps when reading turn by turn, but becomes a weak cue during a long scroll through extended assistant responses. Sparse user prompts can disappear among neutral output blocks.

## Proposed Experience

### Semantic User Surface

- Apply one semantic `user-message-surface` treatment to user-authored messages across Codex conversations, tasks, threads, and sessions.
- Derive a soft fill and compatible border from the active theme accent.
- When no custom accent exists, use the standard product accent.
- Keep the user's message text on the normal foreground token with verified contrast.
- Use the same semantic treatment consistently wherever a user's conversational input is rendered.

### Preserve Assistant Hierarchy

- Keep assistant prose unframed on the conversation background.
- Keep assistant code, logs, tool output, and other inline output on a neutral surface.
- Do not apply the user tint to assistant content.
- Treat the tint only as a sender-identity cue; do not reuse success, warning, destructive, or approval colors.

### Interaction

- No new controls are required in the product.
- Existing custom-theme choices automatically affect the user surface through semantic tokens.
- The prototype's **Current**, **Soft theme tint**, and scroll controls exist only for review.
- The prototype scroll animation demonstrates scan behavior and is not part of the product proposal.

## Accessibility

- Maintain WCAG-readable text contrast in dark, light, custom, and high-contrast themes.
- Keep sender distinction understandable through alignment and layout as well as color.
- Preserve standard text selection, links, keyboard navigation, and focus behavior.
- Do not add motion to the product experience.
- In forced-colors mode, defer to system colors and retain a visible boundary.

## Acceptance Criteria

- A user prompt remains visually distinct from assistant inline output at a glance.
- Sparse user prompts are easy to locate while scanning a history containing long assistant responses.
- The semantic user surface adapts to the active theme without becoming a strong theme-colored block.
- Assistant prose remains unframed and assistant inline output remains neutral.
- Text and controls remain readable at desktop and narrow window widths without overlap.
- The treatment remains identifiable when color perception is limited because alignment and shape are preserved.
- Public proposal assets contain only generic, invented content.

## Scope

This is a focused frontend styling proposal. It does not add sender labels, per-message color settings, new conversation metadata, backend work, or a product scroll animation. Exact token names are illustrative and should map to the desktop client's existing design system.
