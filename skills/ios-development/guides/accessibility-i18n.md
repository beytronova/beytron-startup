# iOS Accessibility and i18n Guide

Use this guide when iOS work touches UI, forms, navigation, text, localization, Dynamic Type, VoiceOver, RTL, or user-facing content.

## Accessibility Rules

- Provide accessibility labels for meaningful icon-only controls and images.
- Do not label decorative elements unless needed.
- Preserve meaningful button, link, and form field traits.
- Support VoiceOver focus order.
- Avoid color-only meaning.
- Maintain sufficient contrast according to product standards.
- Respect Dynamic Type where possible.
- Avoid clipping or overlapping text at larger content sizes.
- Announce important state changes when appropriate.

## SwiftUI Accessibility

Use SwiftUI accessibility APIs when needed:

- `accessibilityLabel`
- `accessibilityHint`
- `accessibilityValue`
- `accessibilityIdentifier`
- `accessibilityElement`
- `accessibilityAddTraits`

## UIKit Accessibility

Use UIKit accessibility APIs when needed:

- `isAccessibilityElement`
- `accessibilityLabel`
- `accessibilityHint`
- `accessibilityValue`
- `accessibilityIdentifier`
- traits and custom actions where appropriate

## Forms

- Labels must remain visible or programmatically available.
- Error messages should be specific and accessible.
- Validation should not rely only on color.
- Focus should move predictably after submit or error.

## Localization Rules

- Do not hardcode user-facing strings when the repo uses localization.
- Use `Localizable.strings`, `.stringsdict`, String Catalogs, or repository convention.
- Avoid concatenating translated string fragments.
- Use pluralization for count-based text.
- Keep interpolation safe and translatable.

## RTL and Layout

- Use leading/trailing where relevant.
- Check directional icons and animations.
- Avoid assuming left-to-right layout.

## Testing

Common checks:

```bash
xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 16' test
```

Recommended validation:

- VoiceOver smoke test for key flows.
- Dynamic Type smoke test for UI-heavy changes.
- Locale/RTL smoke test when relevant.
- UI tests using accessibility identifiers for critical controls.

## Output Format

```text
iOS accessibility/i18n review: PASS|RISK|BLOCKED
Accessibility labels/traits: {summary}
Localization impact: {summary}
Dynamic Type/RTL impact: {summary}
Tests/checks run: {list}
Remaining risks: {list}
```

## Stop Conditions

Stop or report blocker when:

- User-facing strings cannot follow repository localization pattern.
- UI text overflows or overlaps at expected content sizes.
- Required accessibility behavior cannot be validated.
