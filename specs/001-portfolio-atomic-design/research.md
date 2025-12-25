# Research: Initial Portfolio Build (MVP)

## 1. End-to-End Testing Framework

### Decision
We will use **Playwright** for end-to-end testing.

### Rationale
The project requires a robust testing strategy to ensure high quality and accessibility. After evaluating the leading options, Playwright was chosen for the following reasons:

- **Cross-Browser Support**: Playwright provides first-class support for Chromium, Firefox, and WebKit, which is essential for verifying that the portfolio's design and animations render consistently across all major browsers.
- **Performance**: Playwright's architecture generally allows for faster test execution compared to alternatives, which will be beneficial for maintaining a quick development and CI/CD cycle.
- **Modern Feature Set**: It has excellent built-in features like test generation (codegen), tracing for debugging, and the ability to handle complex scenarios (if needed in the future) without workarounds.
- **Developer Ecosystem**: As a Microsoft-backed project, it has strong momentum and is rapidly being adopted in the industry, making it a valuable skill to demonstrate in a portfolio.

### Alternatives Considered
- **Cypress**: A very popular and capable framework with an excellent developer experience. However, its historically limited cross-browser support and in-browser execution model were seen as minor drawbacks compared to Playwright's broader capabilities for this project's emphasis on visual consistency and performance.

### Impact on Plan
- The `tests/` directory will be structured for Playwright tests.
- A `playwright.config.ts` file will be added to the project root.
- Test scripts will be added to `package.json`.
