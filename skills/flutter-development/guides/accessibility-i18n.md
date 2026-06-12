# Flutter Accessibility and i18n Guide

Use this guide when Flutter work touches UI, forms, navigation, text, localization, dynamic type, screen readers, or user-facing content.

## Accessibility Rules

- Provide semantic labels for icon-only controls when meaning is not obvious.
- Preserve meaningful button, link, and form field roles.
- Keep tappable targets large enough for touch interaction.
- Support keyboard/focus behavior when relevant.
- Avoid color-only meaning.
- Maintain sufficient contrast according to product standards.
- Respect text scaling where possible.
- Avoid clipping or overlapping text at larger font sizes.
- Announce important state changes when appropriate.

## Flutter Semantics

Use Flutter semantics tools when needed:

- `Semantics`
- `ExcludeSemantics`
- `MergeSemantics`
- `Tooltip`
- `semanticLabel` on images/icons where appropriate

Do not over-label decorative elements.

## Forms

- Labels must remain visible or programmatically available.
- Error messages should be specific and accessible.
- Validation should not rely only on color.
- Focus should move predictably after submit or error.

## Localization Rules

- Do not hardcode user-facing strings when the repo uses localization.
- Use repository localization pattern such as ARB, generated localization, or custom string service.
- Keep interpolation safe and translatable.
- Avoid concatenating translated string fragments.
- Support pluralization and gender/context where needed.

## RTL and Layout

- Use directional widgets and padding where relevant.
- Avoid assuming left-to-right layout in icons, alignment, and animations.
- Test critical screens with longer strings when possible.

## Testing

Common checks:

```bash
flutter analyze
flutter test
dart format .
```

Recommended validation:

- Widget tests for key semantics where practical.
- Manual check with larger text size for UI-heavy changes.
- Locale/RTL smoke test when relevant.

## Output Format

```text
Accessibility/i18n review: PASS|RISK|BLOCKED
Semantics impact: {summary}
Localization impact: {summary}
Text scaling/RTL impact: {summary}
Tests/checks run: {list}
Remaining risks: {list}
```

## Stop Conditions

Stop or report blocker when:

- User-facing strings cannot follow repository localization pattern.
- UI text overflows or overlaps at expected text sizes.
- Required accessibility behavior cannot be validated.
