# Published GitHub Issue

**Title:** Codex Desktop: distinguish user messages from AI inline output with a theme-aware surface

**Published:** [`openai/codex#35369`](https://github.com/openai/codex/issues/35369)

## Summary

Give user-authored messages a subtle, theme-aware surface so they remain easy to locate in long Codex conversation histories. Keep assistant prose unframed and assistant inline output neutral.

## Problem

In the observed Windows conversation, a user message and assistant inline output use very similar neutral backgrounds. Right alignment is sufficient when reading one turn at a time, but it is a weak scanning cue when sparse user prompts are separated by long assistant responses. The user's own messages can blend into inline output blocks during a long scroll.

## Proposed UX

- Introduce one semantic `user-message-surface` treatment across Codex conversations, tasks, threads, and sessions.
- Derive a soft fill and compatible border from the active theme accent.
- Use the standard product accent as the fallback when no custom accent is selected.
- Keep assistant prose unframed on the conversation background.
- Keep assistant code, logs, tool output, and other inline output on a neutral surface.
- Treat the tint as sender identity, not as success, warning, error, approval, or another status.
- Preserve alignment and shape as non-color cues.
- Do not add sender labels, per-message color settings, or new backend behavior.

## Acceptance Criteria

- User messages and assistant inline output are visibly distinct at a glance.
- Sparse user prompts remain easy to find while scanning long assistant responses.
- The user surface adapts to dark, light, custom, and high-contrast themes.
- Text contrast remains readable and the treatment does not become a strong theme-colored block.
- Assistant prose remains unframed and assistant output remains neutral.
- Narrow desktop windows do not introduce overlap or horizontal overflow.

## Evidence Boundary

This request is based on a supplied Windows screenshot where a user message and assistant inline output use similar neutral surfaces. It does not claim that every Codex theme or conversation surface currently uses identical styling.

The original screenshot is not included because it contains private account and workspace information. The public prototype uses generic, invented content.

## Prototype

- Interactive prototype: https://h4xofficial.github.io/codex-user-message-contrast-proposal/
- One-page specification: https://github.com/H4XOFFICIAL/codex-user-message-contrast-proposal/blob/main/user-message-contrast-spec.md
- Current treatment: https://h4xofficial.github.io/codex-user-message-contrast-proposal/user-message-current.png
- Proposed treatment: https://h4xofficial.github.io/codex-user-message-contrast-proposal/user-message-proposed.png
- Long-history scan: https://h4xofficial.github.io/codex-user-message-contrast-proposal/user-message-scroll.png

The prototype's scroll animation demonstrates the scanning problem and is not a proposed product animation.
