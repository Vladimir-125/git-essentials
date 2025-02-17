# Writing Effective Git Commit Messages

A well-crafted commit message is crucial for maintaining a clear and understandable project history. It helps collaborators understand the purpose of changes and makes it easier to track down issues. Here’s a guide on how to write effective commit messages.

## 1. Use a Conventional Format

Adopting a consistent format for commit messages helps maintain clarity. A common convention is:

```
<type>: <subject>
```

### Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **add**: Addition of new files or content
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc.)
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **perf**: A code change that improves performance
- **test**: Adding missing tests or correcting existing tests
- **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation

### Example

```
fix: resolve issue with user authentication
```

## 2. Write a Concise Subject Line

- **Limit to 50 characters**: Keep the subject line brief and to the point.
- **Use the imperative mood**: Start with a verb, e.g., "Add", "Fix", "Update".
- **Capitalize the first letter**: Begin with a capital letter.
- **No period at the end**: Avoid ending the subject line with a period.

### Example

```
feat: add user login functionality
```

## 3. Provide a Detailed Description (Optional)

If necessary, add a detailed description after the subject line. Separate it from the subject with a blank line. This section can include:

- **What**: Describe what was done.
- **Why**: Explain why the change was necessary.
- **How**: Provide insight into how the change was implemented.

### Example

```
fix: resolve issue with user authentication

The authentication module was failing due to incorrect token validation.
Updated the validation logic to handle edge cases and added unit tests.
```

## 4. Reference Issues or Pull Requests

If the commit relates to an issue or pull request, reference it in the message. This helps in tracking the changes related to specific issues.

### Example

```
fix: resolve issue with user authentication

Closes #123
```

## 5. Use Bullet Points for Multiple Changes

If a commit includes multiple changes, use bullet points in the description to list them clearly.

### Example

```
refactor: improve code readability

- Extracted helper functions for data processing
- Renamed variables for clarity
- Removed deprecated methods
```

## Conclusion

By following these guidelines, you can write commit messages that are clear, informative, and helpful for anyone reviewing the project history. Consistent and descriptive commit messages make collaboration more efficient and debugging easier.