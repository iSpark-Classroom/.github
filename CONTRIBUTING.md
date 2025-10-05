# Contributing Guidelines

Welcome to the iSpark Classroom GitHub organization. This guide will help you understand how to contribute to projects and submit your work properly.

## Branch Naming Conventions

Use descriptive branch names that clearly indicate what you're working on:

- `feature/description` - For new features (e.g., `feature/user-login`)
- `bugfix/description` - For fixing bugs (e.g., `bugfix/broken-link`)
- `docs/description` - For documentation updates (e.g., `docs/update-readme`)
- `assignment/your-name` - For personal assignments (e.g., `assignment/john-doe`)

Keep branch names lowercase and use hyphens to separate words.

## Commit Message Guidelines

Good commit messages help everyone understand what changed and why. Follow this simple format:

### Basic Structure
```
<type>: <short description>
```

### Types
- `feat`: Adding a new feature
- `fix`: Fixing a bug
- `docs`: Updating documentation
- `style`: Formatting changes (spaces, semicolons, etc.)
- `refactor`: Improving code without changing functionality
- `test`: Adding or updating tests
- `chore`: Other changes (dependencies, configs, etc.)

### Examples
```
feat: add login form to homepage
```

```
fix: correct calculation error in total price
```

```
docs: add installation steps to README
```

### Tips for Good Commit Messages
- Start with a lowercase letter after the type
- Keep it under 50 characters
- Use present tense ("add" not "added")
- Be specific about what changed
- Don't end with a period

## Writing Good READMEs

A README is the front page of your project. It should explain what your project does and how to use it.

### Essential Sections

**1. Project Title and Description**
Start with a clear title and 1-2 sentences about what the project does.

**2. Installation**
Tell people how to set up your project step by step.
```markdown
## Installation

1. Clone the repository
2. Run `npm install`
3. Start the server with `npm start`
```

**3. Usage**
Show examples of how to use your project.
```markdown
## Usage

Open `index.html` in your browser to see the app.
```

**4. Features**
List what your project can do.

**5. Technologies Used**
Mention the languages, frameworks, or tools you used.

### README Best Practices
- Write clearly and simply
- Use code blocks for commands
- Add screenshots if your project has a visual interface
- Include error solutions if you ran into common problems
- Keep it updated as your project changes
- Test your instructions to make sure they work

### Example README
```markdown
# Todo List App

A simple todo list application built with HTML, CSS, and JavaScript.

## Installation

1. Clone this repository
2. Open `index.html` in your browser

## Usage

- Click "Add Task" to create a new todo
- Click the checkbox to mark tasks as complete
- Click the trash icon to delete tasks

## Features

- Add new tasks
- Mark tasks as complete
- Delete tasks
- Tasks persist in local storage

## Technologies Used

- HTML5
- CSS3
- JavaScript (ES6)

## Screenshots

![App Screenshot](screenshot.png)
```

## Creating Pull Requests

A pull request (PR) is how you submit your work for review.

### Steps to Create a PR

1. **Push your branch**
   ```bash
   git push origin your-branch-name
   ```

2. **Go to the repository on GitHub**
   You'll see a button saying "Compare & pull request"

3. **Fill out the PR form**
   - Write a clear title
   - Describe what you changed and why
   - Mention any issues if applicable

4. **Submit the PR**
   Click "Create pull request"

### PR Description Template

```markdown
## What I Changed
Brief explanation of what this PR does

## Changes Made
- Added login form
- Created user authentication
- Updated navigation menu

## How to Test
1. Run the project
2. Click on the login button
3. Enter credentials and submit

## Screenshots (if applicable)
Add screenshots here
```

### PR Best Practices
- Create one PR per feature or assignment
- Write a clear title that explains what you did
- Describe your changes in detail
- Make sure your code works before submitting
- Respond to feedback and make requested changes
- Keep your PR focused - don't mix unrelated changes

## General Git Workflow

Here's the typical workflow for contributing:

1. **Clone the repository** (first time only)
   ```bash
   git clone <repository-url>
   ```

2. **Create a new branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   Edit files, write code, test your work

4. **Stage your changes**
   ```bash
   git add .
   ```

5. **Commit your changes**
   ```bash
   git commit -m "feat: add new feature"
   ```

6. **Push to GitHub**
   ```bash
   git push origin feature/your-feature-name
   ```

7. **Create a Pull Request**
   Go to GitHub and open a PR from your branch

## Code Quality Tips

- Write clean, readable code
- Add comments to explain complex logic
- Follow consistent formatting (indentation, spacing)
- Test your code before committing
- Break large changes into smaller commits
- Ask for help when stuck

## Getting Help

If you're stuck or have questions:
- Check the project's README first
- Search for similar issues in the repository
- Ask your instructors or classmates
- Open an issue describing your problem

## Remember

- Everyone makes mistakes - that's how we learn
- Don't be afraid to ask questions
- Review others' code to learn different approaches
- Practice makes perfect

Thank you for being part of iSpark Classroom!
