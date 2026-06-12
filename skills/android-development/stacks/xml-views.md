# Android XML Views Stack Deep Dive

Use this when a native Android repository uses XML layouts, Fragments, Activities, ViewBinding, DataBinding, RecyclerView, or Navigation Component.

## Stack Signals

- Layouts exist under `res/layout`.
- Code uses `Activity`, `Fragment`, `ViewBinding`, `DataBinding`, `RecyclerView`, `Adapter`, or `NavHostFragment`.
- Navigation uses XML navigation graphs.

## Primary Languages

- Kotlin for new code when possible.
- Java only when the repository is Java-first or interop is required.
- XML for layouts, resources, navigation graphs, menus, and drawables.

## File Structure Rules

- Keep Activities and Fragments thin.
- Keep rendering and click binding in UI layer.
- Keep business logic in ViewModels, use cases, repositories, or services.
- Keep adapters focused on binding list items.
- Keep reusable UI resources in existing resource structure.

## Architecture Rules

- Prefer MVVM or repository-established architecture.
- Use lifecycle-aware observation/collection.
- Avoid storing view references beyond lifecycle.
- Clear bindings in Fragments according to repository convention.
- Keep navigation actions predictable and testable.

## RecyclerView Rules

- Use `ListAdapter` and `DiffUtil` when repository convention supports it.
- Keep item identity stable.
- Avoid doing heavy work in `onBindViewHolder`.
- Handle empty, loading, error, and pagination states where relevant.

## UI State Rules

- Model loading, empty, error, success, permission, and offline states.
- Preserve content descriptions for icon/image controls.
- Keep text in string resources when repo uses Android resources.
- Support font scaling and RTL when applicable.

## Testing

Common checks:

```bash
./gradlew test
./gradlew connectedAndroidTest
./gradlew lint
./gradlew assembleDebug
```

Use Robolectric, Espresso, or repository-standard UI tests for critical flows.

## Do Not Do

- Do not put network or database calls in Activities, Fragments, or adapters.
- Do not leak binding, Activity, Fragment, or Context references.
- Do not hardcode user-facing strings in XML or Kotlin when resources are used.
- Do not bypass lifecycle-aware collection.

## Output Notes

When using this stack, report:

- Activities/Fragments/layouts changed
- ViewBinding/DataBinding impact
- Navigation graph impact
- RecyclerView/list impact
- Accessibility/resource notes
- Tests/checks run
