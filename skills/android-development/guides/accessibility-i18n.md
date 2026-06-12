# Android Accessibility and i18n Guide

Use this guide when Android work touches UI, forms, navigation, text, localization, font scaling, TalkBack, RTL, or user-facing content.

## Accessibility Rules

- Provide content descriptions for meaningful icon-only controls and images.
- Do not add content descriptions to decorative elements unless needed.
- Keep touch targets large enough for Android interaction standards.
- Support TalkBack focus order.
- Avoid color-only meaning.
- Maintain sufficient contrast according to product standards.
- Respect font scaling.
- Avoid clipping or overlapping text at larger font sizes.
- Announce important state changes when appropriate.

## Compose Accessibility

Use Compose semantics when needed:

- `contentDescription`
- `semantics`
- `clearAndSetSemantics`
- `mergeDescendants`
- role/state descriptions where appropriate

## XML/View Accessibility

Use Android resources and attributes when needed:

- `android:contentDescription`
- `importantForAccessibility`
- `labelFor`
- proper input hints and errors

## Forms

- Labels must remain visible or programmatically available.
- Error messages should be specific and accessible.
- Validation should not rely only on color.
- Focus should move predictably after submit or error.

## Localization Rules

- Put user-facing strings in resources when repository uses Android resources.
- Avoid hardcoded user-facing strings.
- Use plurals for count-based text.
- Avoid concatenating translated fragments.
- Support placeholders safely.
- Use resource qualifiers where appropriate.

## RTL and Layout

- Use start/end instead of left/right where relevant.
- Check icon mirroring for directional icons.
- Avoid assuming left-to-right layout in alignment and animations.

## Testing

Common checks:

```bash
./gradlew lint
./gradlew test
./gradlew connectedAndroidTest
```

Recommended validation:

- TalkBack smoke test for key flows.
- Font scaling smoke test for UI-heavy changes.
- Locale/RTL smoke test when relevant.
- Compose/Espresso tests for key semantics where practical.

## Output Format

```text
Android accessibility/i18n review: PASS|RISK|BLOCKED
Content descriptions: {summary}
Localization impact: {summary}
Font scaling/RTL impact: {summary}
Tests/checks run: {list}
Remaining risks: {list}
```

## Stop Conditions

Stop or report blocker when:

- User-facing strings cannot follow repository localization pattern.
- UI text overflows or overlaps at expected text sizes.
- Required accessibility behavior cannot be validated.
