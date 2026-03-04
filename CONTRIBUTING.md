# Contributing to Api Playground

Thank you for considering contributing to the **Api Playground** project! 

This document outlines the best practices and guidelines for contributing to the project.

## General Guidelines

- **Code Style:** Follow the coding standards defined in the `.editorconfig` file.

- **Commit Messages:**
  - Follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification with **strict formatting**
  - **Subject line (first line) MUST be ≤ 50 characters maximum**
  - Format: `<type>(<scope>): <message>` (lowercase, imperative mood, no period)
    - Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`
    - Scopes: `frontend`, `backend`, `infra`, `api`, `db`, etc.
  - Use the body to provide additional context (wrap at 72 characters)
  - Valid example (44 characters):
    ```
    feat(backend): implement user authentication

    Add OAuth2 authentication flow with login and logout.
    Updated User model to include OAuth tokens.
    Implements #123.
    ```
  - Invalid examples (exceeds 50 char limit):
    ```
    ❌ feat: Add new user authentication with OAuth2 (❌ 45 chars, missing scope)
    ❌ feat(backend): implement user OAuth2 authentication (❌ 51 chars - TOO LONG)
    ❌ docs: Update documentation and guides for the system (❌ scope missing)
    ```
- **Pull Requests:**
  - Ensure your branch is up-to-date with `main` before opening a pull request.
  - Include a clear description of the changes and reference any related issues. See a description sample in [Pull Request template.](.devops/pull_request_template.md)
  - Add screenshots or examples if applicable.

- **Testing:** Write unit tests for new features or bug fixes. Ensure all tests pass before submitting your changes.

- **Documentation:** Update relevant documentation for any changes made.

## Documentation Best Practices

- **Location:**
  - All documentation files should be placed in the `docs` folder at the root of the repository.
  - Use subfolders to organize documentation by topic or feature if necessary.

- **File Naming:**
  - Use clear and descriptive names for documentation files.
  - For feature-specific documentation, use the format `feature-name.README.md`. Example:
    ```
    docs/
      authentication.README.md
      deployment.README.md
      api-guidelines.README.md
    ```

- **Content Structure:**
  - Start each documentation file with a brief summary of its purpose.
  - Use headings (`#`, `##`, `###`) to organize content into logical sections.
  - Include examples, diagrams, or code snippets where applicable.

- **Markdown Standards:**
  - Follow Markdownlint rules to ensure consistency.
  - Use proper formatting for lists, tables, and links.
  - Avoid long lines; wrap text at 120 characters where possible.

- **Versioning:**
  - If documentation is tied to specific versions of the project, include a version number or changelog section.

- **Review Process:**
  - All documentation changes should be reviewed as part of the pull request process.
  - Ensure that documentation is up-to-date with the latest code changes.


## .NET Core Best Practices

- **Project Structure:**
  - For the MVP, adopt a **pragmatic Clean Architecture** approach combined with **Vertical Slicing**:
    - Organize code by feature, grouping related models, services, and endpoints together.
    - Maintain clear boundaries between layers (e.g., Application, Domain, Infrastructure) where it adds value.
    - Avoid over-engineering; prioritize simplicity and rapid iteration.
- **API Design:**
  - Prefer using **Minimal APIs** over traditional WebAPI controllers to simplify the codebase and improve performance.
  - Avoid using controllers unless absolutely necessary.

- **Dependency Injection:**
  - Use built-in dependency injection for managing services.

- **Error Handling:**
  - Implement global exception handling using middleware.

- **Logging:**
  - Use `ILogger` for structured logging.

- **Testing:**
  - Write unit tests using `xUnit`.
  - Mock dependencies with libraries like **nSubstitute**.


## Terraform Best Practices

- **File Organization:**
  - Use separate files for `variables.tf`, `outputs.tf`, and `main.tf`.
  - Group resources logically by module.

- **State Management:**
  - Use remote state storage (e.g., Azure Storage) to manage Terraform state.

- **Versioning:**
  - Pin provider versions in the `required_providers` block.

- **Validation:**
  - Run `terraform validate` and `terraform fmt` before committing.
  - Always validate commit message before pushing (max 50 chars for subject line)

- **Security:**
  - Avoid hardcoding sensitive values. Use environment variables or secret management tools.



## Additional Notes

- If you have any questions, feel free to open an issue or reach out to the maintainers.
