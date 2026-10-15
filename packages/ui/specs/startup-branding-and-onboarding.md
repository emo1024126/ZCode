# Startup branding and onboarding boundary

## Behavior

- The Electron pre-render startup shell uses the Codex PNG asset instead of an inline Z SVG.
- The React startup loading and occupation-onboarding visual surfaces use the bundled Codex image while preserving their layout.
- Occupation onboarding remains manually openable from Settings, but is not an automatic startup gate.
- The new-task draft empty state keeps its greeting and input layout but has no decorative Z background.
- Internal ZCode protocol names, CSS data attributes, store symbols, and persistent paths remain unchanged.

## Acceptance

- `packages/desktop/src/renderer/index.html` references `codex-logo.png` and contains no inline Z paths.
- `RootStartupLoading` and `OccupationOnboardingVisual` render the Codex image.
- First launch does not block on `OccupationOnboarding`; an explicit Settings request still opens it.
- `ConversationDraftEmptyState` has no `Z.svg` import or decorative Z layer.
