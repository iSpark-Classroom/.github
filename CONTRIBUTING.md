# Contributing Guidelines

Thank you for your interest in contributing to this project. This document outlines the standards and workflows expected from all contributors.

## Table of Contents

- [Contributing Guidelines](#contributing-guidelines)
  - [Table of Contents](#table-of-contents)
  - [Understanding Git and GitHub Workflows](#understanding-git-and-github-workflows)
  - [1. Git Workflow (Local Development)](#1-git-workflow-local-development)
    - [Basic Git Process](#basic-git-process)
    - [Important Git Commands](#important-git-commands)
    - [Git Workflow Best Practices](#git-workflow-best-practices)
  - [2. GitHub Workflow (Collaboration)](#2-github-workflow-collaboration)
    - [GitHub Collaboration Process](#github-collaboration-process)
    - [GitHub Workflow Best Practices](#github-workflow-best-practices)
    - [Understanding CI/CD Automation](#understanding-cicd-automation)
  - [Branch Naming Conventions](#branch-naming-conventions)
  - [Commit Message Guidelines](#commit-message-guidelines)
    - [Format](#format)
    - [Types](#types)
    - [Examples](#examples)
    - [Best Practices](#best-practices)
  - [Writing Good READMEs](#writing-good-readmes)
    - [Essential Sections](#essential-sections)
    - [Best Practices](#best-practices-1)
    - [Example Structure](#example-structure)
  - [Pull Request Process](#pull-request-process)
    - [Pull Request Template](#pull-request-template)
    - [Pull Request Best Practices](#pull-request-best-practices)
  - [Code Review Guidelines](#code-review-guidelines)
  - [Additional Resources](#additional-resources)
    - [Git and GitHub Learning](#git-and-github-learning)
    - [Commit Message Standards](#commit-message-standards)
    - [CI/CD](#cicd)
  - [Questions or Issues?](#questions-or-issues)

## Understanding Git and GitHub Workflows

As a trainee, you'll be working with two distinct workflows: the Git workflow for version control and the GitHub workflow for collaboration. Understanding both is essential for contributing effectively.

## 1. Git Workflow (Local Development)

The Git workflow is how you manage code changes on your local machine. This is the day-to-day process you'll follow:

### Basic Git Process

1. **Clone the Repository** (first time only)
   ```bash
   git clone <repository-url>
   cd <project-directory>
   ```

2. **Create a New Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```
   Always create a new branch for your work. Never commit directly to `main`.

3. **Make Your Changes**
   - Edit files, write code, add features or fix bugs
   - Save your work regularly

4. **Check What Changed**
   ```bash
   git status
   git diff
   ```
   Review your changes before committing.

5. **Stage Your Changes**
   ```bash
   git add <filename>        # Add specific files
   git add .                 # Add all changes
   ```

6. **Commit Your Changes**
   ```bash
   git commit -m "feat: add user login functionality"
   ```
   Use clear, descriptive commit messages following the [Commit Message Guidelines](#commit-message-guidelines).

7. **Push to GitHub**
   ```bash
   git push origin feature/your-feature-name
   ```

### Important Git Commands

- `git pull origin main` - Update your local main branch with remote changes
- `git branch` - List all branches
- `git checkout <branch-name>` - Switch to a different branch
- `git log` - View commit history
- `git reset HEAD~1` - Undo the last commit (use carefully)

### Git Workflow Best Practices

- **Commit often**: Make small, focused commits rather than large ones
- **Pull before you push**: Always update your branch before pushing
- **Keep commits atomic**: Each commit should represent one logical change
- **Write meaningful messages**: Your future self will thank you

## 2. GitHub Workflow (Collaboration)

The GitHub workflow is how you collaborate with the team through pull requests and code reviews. This happens after you've pushed your code.

### GitHub Collaboration Process

1. **Push Your Branch**
   After committing locally, push your branch to GitHub:
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Create a Pull Request (PR)**
   - Go to the repository on GitHub
   - Click "Pull requests" then "New pull request"
   - Select your branch to merge into `main`
   - Fill out the PR template with:
     - Clear title describing the change
     - Description of what and why
     - List of changes made
     - Testing performed
     - Related issue numbers

3. **Automated Checks Run**
   GitHub will automatically run CI/CD workflows:
   - Code linting and formatting checks
   - Automated tests
   - Build verification
   
   Wait for these checks to complete. If any fail, click "Details" to see why and fix the issues.

4. **Request Reviews**
   - Assign reviewers from your team
   - Wait for feedback
   - Be patient and professional

5. **Address Feedback**
   When reviewers leave comments:
   - Make requested changes in your local branch
   - Commit and push the updates
   - Reply to comments explaining your changes
   - Request re-review when ready

6. **Merge**
   Once approved and all checks pass:
   - A maintainer will merge your PR
   - Your changes are now part of the main codebase
   - Delete your feature branch (GitHub offers this option)

7. **Update Your Local Repository**
   ```bash
   git checkout main
   git pull origin main
   git branch -d feature/your-feature-name  # Delete local branch
   ```

### GitHub Workflow Best Practices

- **One PR per feature**: Keep pull requests focused on a single change
- **Small PRs are better**: Easier to review and less likely to have conflicts
- **Respond promptly**: Address review comments within 24-48 hours
- **Test before submitting**: Always test your changes locally first
- **Link issues**: Reference related issues using `#issue-number`
- **Keep PRs updated**: Regularly merge main into your branch to avoid conflicts

### Understanding CI/CD Automation

When you create a pull request, automated workflows run in the background:

- **Continuous Integration (CI)**: Automatically tests your code
  - Runs linters to check code quality
  - Executes test suites
  - Builds the project to catch errors
  
- **Continuous Deployment (CD)**: Automates deployment (after merge)
  - Creates production builds
  - Deploys to staging/production environments
  - Generates release notes

You'll see these as status checks on your PR. All must pass before merging.

## Branch Naming Conventions

Use descriptive branch names that indicate the type of work being done:

- `feature/description` - For new features (e.g., `feature/user-authentication`)
- `bugfix/description` - For bug fixes (e.g., `bugfix/login-error`)
- `hotfix/description` - For urgent production fixes
- `docs/description` - For documentation updates
- `refactor/description` - For code refactoring
- `test/description` - For adding or updating tests

Keep branch names lowercase and use hyphens to separate words.

## Commit Message Guidelines

Write clear, meaningful commit messages that explain what changed and why:

### Format
```
<type>: <subject>

<body (optional)>

<footer (optional)>
```

### Types
- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, missing semicolons, etc.)
- `refactor`: Code changes that neither fix bugs nor add features
- `test`: Adding or updating tests
- `chore`: Maintenance tasks, dependency updates

### Examples
```
feat: add user profile page

Implemented a new profile page that displays user information
and allows users to update their details.
```

```
fix: resolve null pointer exception in login handler

Added null check before accessing user object to prevent
crashes when session expires.
```

```
docs: update installation instructions in README
```

### Best Practices
- Use the imperative mood ("add feature" not "added feature")
- Keep the subject line under 50 characters
- Capitalize the subject line
- Do not end the subject line with a period
- Separate subject from body with a blank line
- Wrap the body at 72 characters
- Use the body to explain what and why, not how

## Writing Good READMEs

A README is often the first thing people see in your project. Make it count:

### Essential Sections
1. **Project Title and Description**: Clearly state what the project does
2. **Installation**: Step-by-step instructions to get started
3. **Usage**: Examples showing how to use the project
4. **Features**: Key functionality and capabilities
5. **Requirements**: Dependencies and prerequisites
6. **Contributing**: Link to this CONTRIBUTING.md file
7. **License**: State the project license

### Best Practices
- Write for someone who knows nothing about your project
- Use code blocks for commands and examples
- Include screenshots or GIFs for visual projects
- Keep it concise but comprehensive
- Update it as the project evolves
- Use proper Markdown formatting
- Test all instructions before publishing

### Example Structure
```markdown
# Project Name

Brief description of what this project does.

## Installation

\`\`\`bash
npm install
\`\`\`

## Usage

\`\`\`javascript
const example = require('./example');
example.run();
\`\`\`

## Features

- Feature one
- Feature two
- Feature three

## Contributing

See CONTRIBUTING.md for guidelines.

## License

MIT
```

## Pull Request Process

Follow these steps when submitting a pull request:

1. **Create a Branch**: Branch off from `main` using proper [naming conventions](#branch-naming-conventions)
2. **Make Changes**: Implement your feature or fix
3. **Test Locally**: Ensure all tests pass and the code works as expected
4. **Commit**: Use proper [commit message format](#commit-message-guidelines)
5. **Push**: Push your branch to the repository
6. **Open PR**: Create a pull request with a clear title and description

### Pull Request Template

When opening a PR, include:

```markdown
## Description
Brief explanation of what this PR does

## Changes Made
- List of specific changes
- Another change
- Yet another change

## Testing
Describe how you tested these changes

## Related Issues
Closes #123
```

### Pull Request Best Practices
- Keep PRs focused on a single feature or fix
- Write a clear, descriptive title
- Explain the problem and your solution
- Reference related issues
- Request reviews from relevant team members
- Respond to feedback promptly
- Ensure CI checks pass before requesting review

## Code Review Guidelines

When reviewing code:
- Be respectful and constructive
- Focus on the code, not the person
- Explain your reasoning
- Suggest improvements, don't demand them
- Approve when satisfied with the changes

When receiving reviews:
- Don't take feedback personally
- Ask for clarification if needed
- Make requested changes or discuss alternatives
- Thank reviewers for their time

## Additional Resources

### Git and GitHub Learning
- [Official Git Documentation](https://git-scm.com/doc) - Comprehensive Git reference
- [GitHub Docs](https://docs.github.com) - Complete guide to GitHub features


### Commit Message Standards
- [Conventional Commits](https://www.conventionalcommits.org/) - Standardized commit message format
- [How to Write a Git Commit Message]([https://chris.beams.io/posts/git-commit](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/)/) - Best practices guide


### CI/CD
- [GitHub Actions Documentation](https://docs.github.com/en/actions) - Automate workflows
- [Introduction to CI/CD](https://www.redhat.com/en/topics/devops/what-is-ci-cd) - Understand the concepts



## Questions or Issues?

If you have questions about these guidelines or need help with the contribution process, please open an issue or reach out to a maintainer.

Thank you for contributing to this project!
