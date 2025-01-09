
# Conventional Commit

The [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of. This convention dovetails with SemVer, by describing the features, fixes, and breaking changes made in commit messages.

## Commit Message Structure
```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

### Explanation of Structure
1. **`type`**: Describes the type of change being made.
2. **`scope`** (optional): Indicates the specific area of the code affected (module, file, feature, etc.).
3. **`subject`**: A brief description of the change (max 72 characters).
4. **`body`** (optional): Detailed explanation of the change.
5. **`footer`** (optional): Additional information such as metadata, issue references, or breaking changes.

---

## Commit Types (`type`)

| **Type**      | **Description**                                          |
|---------------|----------------------------------------------------------|
| `feat`        | Introducing a new feature.                               |
| `fix`         | Fixing a bug.                                            |
| `docs`        | Changes to documentation only.                           |
| `style`       | Code style changes (e.g., formatting, whitespace).       |
| `refactor`    | Code refactoring without adding features or fixing bugs. |
| `perf`        | Changes to improve performance.                          |
| `test`        | Adding or fixing tests.                                  |
| `build`       | Changes to build process or external dependencies.       |
| `ci`          | Changes to CI/CD configuration.                          |
| `chore`       | Routine tasks or updates that do not affect production code. |
| `revert`      | Reverting a previous commit.                             |

---

## Examples

### Adding a New Feature
```
feat(auth): add JWT authentication

Implement JWT-based authentication for secure API access.
Includes login, signup, and token refresh endpoints.
```

### Fixing a Bug
```
fix(ui): resolve button alignment issue on mobile

Fixes the misalignment of the submit button in the mobile view.
Tested on Chrome and Safari.
```

### Documentation Changes
```
docs(README): update installation instructions

Added steps for setting up the project using Laravel Herd.
```

### Performance Improvements
```
perf(api): optimize database queries for user module

Refactored queries to reduce response time by 20%.
```

### Breaking Changes
```
feat(user): introduce mandatory email verification

BREAKING CHANGE: All existing users must verify their email addresses before login.
```

---

## Footer for Issues or Metadata
Use the footer to reference issues or PRs:
```
fix(auth): prevent token expiration errors

Ensure token validation logic checks expiration accurately.
Closes #123
```

---

## Best Practices
- Focus on a single purpose for each commit.
- Use present tense (e.g., "add" instead of "added").
- Test your code before committing.

## Tools
- [Husky](https://typicode.github.io/husky/)
