# FeatherCSS

FeatherCSS is a lightweight, modular CSS framework designed for scalability and developer experience. It leverages modern SCSS features like `@use` and `@forward` to create a clean and efficient architecture.

## SCSS Architecture

The project uses a modular SCSS architecture designed to minimize unused CSS and provide a clear separation of concerns.

### Directory Structure

```text
scss/
├── abstracts/          # Helpers (Variables, Mixins, Functions) - No CSS output
├── base/               # Boilerplate (Reset, Typography)
├── components/         # UI Components (Buttons, Navbar, etc.)
├── pages/              # Page-specific entry points
└── global.scss         # Main entry point for global styles
```

### Key Concepts

-   **Global vs. Page-Specific**:
    -   `global.scss`: Generates `global.css`. Contains base styles (reset, typography) and CSS variables. This should be included on every page.
    -   `pages/*.scss`: Generates page-specific CSS (e.g., `home.css`). Contains styles specific to that page and imports only the components used on that page.

-   **@use and @forward**:
    -   We use `@use` to import modules. This namespaces variables and mixins, preventing naming collisions.
    -   We use `@forward` in `_index.scss` files to expose members from a directory as a single module.

### Compilation

To compile the SCSS files, use the `sass` command (or `npx sass` if installed locally):

```bash
# Compile global styles
npx sass scss/global.scss css/global.css

# Compile page-specific styles
npx sass scss/pages/home.scss css/home.css
```

### Usage

1.  **Abstracts**: Import abstracts to use variables, mixins, or functions.
    ```scss
    @use '../abstracts' as *;
    
    .my-element {
      color: $primary-color;
      @include flex-center;
    }
    ```

2.  **Components**: Create components in `scss/components` and import them in your page files.
    ```scss
    // scss/pages/home.scss
    @use '../components/buttons';
    ```

3.  **HTML**: Include the global CSS and the specific page CSS in your HTML file.
    ```html
    <link rel="stylesheet" href="css/global.css">
    <link rel="stylesheet" href="css/home.css">
    ```
