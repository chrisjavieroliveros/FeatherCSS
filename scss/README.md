# FeatherCSS SCSS Architecture

This project uses a modular SCSS architecture for scalability, maintainability, and clarity. Below is an overview of the folder structure and purpose of each directory:

## Structure

- **main.scss**: Entry point for compiling all styles. Imports global and modular SCSS files.
- **abstracts/**: Contains non-output helpers like variables, functions, mixins, and responsive utilities.
  - `_colors.scss`, `_variables.scss`, `_functions.scss`, `_mixins.scss`, `_responsive.scss`, `_index.scss`
- **base/**: Base styles such as resets and typography.
  - `_reset.scss`, `_typography.scss`, `_index.scss`
- **layout/**: Layout-related styles (containers, grid, split layouts).
  - `_container.scss`, `_split.scss`, `_index.scss`
- **components/**: Reusable UI components (buttons, cards, etc.).
  - `_buttons.scss`, `_index.scss`
- **pages/**: Page-specific styles.
  - `_home.scss`, `_index.scss`
- **utilities/**: Utility/helper classes for spacing, display, etc.
  - `_spacing.scss`, `_display.scss`, `_index.scss`

## Usage

- Each folder has an `index.scss` to centralize imports for that module.
- Use `@use` to import modules in `main.scss` or `global.scss`.
- Abstracts are loaded first for access to variables and mixins throughout the project.
- Utilities provide quick helper classes for rapid prototyping and utility-first styling.

## Extending

- Add new components to `components/` and import them in `components/index.scss`.
- Add new page styles to `pages/` and import them in `pages/index.scss`.
- For new utility classes, add files to `utilities/` and update `utilities/index.scss`.

## Best Practices

- Keep variables and mixins in `abstracts/` for reusability.
- Use base styles for resets and typography to ensure consistency.
- Organize layout and components for modularity and scalability.
- Use page styles only for page-specific overrides.
- Document new modules and keep `index.scss` files updated.

---

This architecture is designed for maintainable, scalable, and robust CSS development. Feel free to extend or modify as your project grows.
