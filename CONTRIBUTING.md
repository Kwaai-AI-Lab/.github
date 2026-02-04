# Contributing to Kwaai-AI-Lab

Thank you for your interest in contributing to Kwaai! We welcome contributions from developers, researchers, designers, and community members who share our mission of democratizing AI access.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Workflow](#development-workflow)
- [Coding Standards](#coding-standards)
- [Pull Request Process](#pull-request-process)
- [Issue Guidelines](#issue-guidelines)
- [Community](#community)

---

## Code of Conduct

### Our Pledge

Kwaai-AI-Lab is committed to providing a welcoming, inclusive, and harassment-free environment for everyone, regardless of age, body size, disability, ethnicity, gender identity and expression, level of experience, nationality, personal appearance, race, religion, or sexual identity and orientation.

### Expected Behavior

- Be respectful and considerate in communication
- Provide constructive feedback and criticism
- Focus on what's best for the community
- Show empathy towards other community members
- Welcome newcomers and help them get started
- Acknowledge different perspectives and experiences

### Unacceptable Behavior

- Harassment, intimidation, or discrimination
- Offensive comments or personal attacks
- Trolling or insulting remarks
- Publishing others' private information
- Any conduct that could be considered inappropriate in a professional setting

### Reporting

If you experience or witness unacceptable behavior, please report it to [conduct@kwaai.ai](mailto:conduct@kwaai.ai). All reports will be handled with discretion and confidentiality.

---

## Getting Started

### Prerequisites

Before contributing, ensure you have:

- **Git** installed and configured
- **Development environment** for the project's primary language:
  - **Rust**: rustc 1.70+, cargo
  - **Python**: Python 3.9+, pip, virtualenv
  - **TypeScript/JavaScript**: Node.js 18+, npm or yarn
- **GitHub account** with SSH keys configured
- **Slack account** (optional but recommended): [kwaaiailab.slack.com](https://kwaaiailab.slack.com)

### Finding a Project

1. Browse the [organization profile](https://github.com/Kwaai-AI-Lab) to find projects that interest you
2. Read the project's README and documentation
3. Look for issues tagged with:
   - `good first issue` - Suitable for newcomers
   - `help wanted` - Community contributions welcome
   - `documentation` - Documentation improvements
   - `bug` - Bug fixes needed

### Setting Up Your Environment

```bash
# Fork the repository on GitHub, then clone your fork
git clone git@github.com:YOUR_USERNAME/REPOSITORY_NAME.git
cd REPOSITORY_NAME

# Add upstream remote
git remote add upstream git@github.com:Kwaai-AI-Lab/REPOSITORY_NAME.git

# Create a development branch
git checkout -b feature/your-feature-name
```

---

## How to Contribute

### Types of Contributions

We welcome various types of contributions:

#### 🐛 Bug Reports

- Search existing issues to avoid duplicates
- Use the bug report template
- Include reproduction steps, expected behavior, and actual behavior
- Provide system information (OS, version, environment)

#### ✨ Feature Requests

- Check if the feature has already been requested
- Use the feature request template
- Explain the use case and benefits
- Consider implementation approaches

#### 📝 Documentation

- Fix typos, clarify explanations, add examples
- Improve API documentation
- Write tutorials or guides
- Translate documentation to other languages

#### 🔧 Code Contributions

- Bug fixes
- New features
- Performance improvements
- Refactoring
- Tests

#### 🎨 Design Contributions

- UI/UX improvements
- Visual assets
- Accessibility enhancements

#### 🔬 Research Contributions

- Novel algorithms or architectures
- Experimental results
- Literature reviews
- Benchmarking studies

---

## Development Workflow

### 1. Create an Issue (Optional but Recommended)

For significant changes, create an issue first to discuss the approach:

```markdown
**Title**: Brief description of the change

**Description**:
- What problem does this solve?
- What approach will you take?
- Are there alternative approaches?

**Related Issues**: #123, #456
```

### 2. Set Up Development Environment

Each project may have specific setup instructions. Common patterns:

**Rust Projects:**
```bash
# Install dependencies
cargo build

# Run tests
cargo test

# Format code
cargo fmt

# Run linter
cargo clippy
```

**Python Projects:**
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
pip install -r requirements-dev.txt  # Development dependencies

# Run tests
pytest

# Format code
black .
isort .

# Type checking
mypy .
```

**TypeScript/JavaScript Projects:**
```bash
# Install dependencies
npm install

# Run tests
npm test

# Format code
npm run format

# Lint
npm run lint

# Build
npm run build
```

### 3. Make Your Changes

- Write clean, readable code following the project's style
- Add tests for new functionality
- Update documentation as needed
- Commit frequently with meaningful messages

### 4. Test Your Changes

Before submitting:

- Run the full test suite: `cargo test`, `pytest`, or `npm test`
- Run linters and formatters
- Test manually if applicable
- Verify documentation builds correctly

### 5. Commit Your Changes

Follow the commit message convention:

```
type(scope): Brief summary (50 chars or less)

Detailed explanation of what changed and why. Wrap at 72 characters.
Include any breaking changes or important notes.

Fixes #123
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code refactoring
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `chore`: Maintenance tasks (dependencies, build, etc.)

**Examples:**

```bash
git commit -m "feat(kwaai-net): Add peer discovery via mDNS"

git commit -m "fix(pai-os): Resolve memory leak in agent lifecycle

The agent cleanup process was not properly releasing resources,
causing memory to accumulate over time. This commit ensures all
resources are freed when agents are destroyed.

Fixes #456"

git commit -m "docs(readme): Update installation instructions"
```

### 6. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 7. Create a Pull Request

- Go to the original repository on GitHub
- Click "New Pull Request"
- Select your fork and branch
- Fill out the pull request template
- Link related issues

---

## Coding Standards

### General Principles

- **Clarity over cleverness**: Write code that's easy to understand
- **Consistency**: Follow existing patterns in the codebase
- **Simplicity**: Keep solutions as simple as possible
- **Documentation**: Document complex logic and public APIs
- **Testing**: Write tests for new functionality

### Language-Specific Standards

#### Rust

- Follow [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/)
- Use `cargo fmt` for formatting
- Run `cargo clippy` and address warnings
- Document public APIs with `///` doc comments
- Use `Result` for error handling, avoid panics in library code
- Prefer iterators over explicit loops where appropriate

```rust
/// Validates a peer ID according to Kwaai network standards.
///
/// # Arguments
///
/// * `peer_id` - The peer identifier to validate
///
/// # Returns
///
/// Returns `Ok(())` if valid, or an error describing the validation failure.
///
/// # Example
///
/// ```
/// use kwaai_net::validate_peer_id;
///
/// assert!(validate_peer_id("peer-123").is_ok());
/// ```
pub fn validate_peer_id(peer_id: &str) -> Result<(), ValidationError> {
    // Implementation
}
```

#### Python

- Follow [PEP 8](https://peps.python.org/pep-0008/) style guide
- Use type hints for function signatures
- Use `black` for formatting (line length: 88)
- Use `isort` for import sorting
- Document using Google-style docstrings
- Use `mypy` for static type checking

```python
from typing import List, Optional

def process_query(
    query: str,
    max_results: int = 10,
    filter_params: Optional[dict] = None
) -> List[dict]:
    """Process a user query and return relevant results.

    Args:
        query: The search query string
        max_results: Maximum number of results to return
        filter_params: Optional filtering parameters

    Returns:
        A list of result dictionaries containing matched items

    Raises:
        ValueError: If query is empty or max_results is negative

    Example:
        >>> results = process_query("AI research", max_results=5)
        >>> len(results)
        5
    """
    # Implementation
    pass
```

#### TypeScript/JavaScript

- Follow [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- Use TypeScript for new code
- Use ESLint with project configuration
- Use Prettier for formatting
- Document using JSDoc for public APIs
- Prefer functional programming patterns

```typescript
/**
 * Fetches user data from the API.
 *
 * @param userId - The unique identifier for the user
 * @param options - Optional configuration parameters
 * @returns A promise that resolves to the user data
 * @throws {APIError} If the request fails or user is not found
 *
 * @example
 * ```typescript
 * const user = await fetchUserData('user-123');
 * console.log(user.name);
 * ```
 */
export async function fetchUserData(
  userId: string,
  options?: FetchOptions
): Promise<UserData> {
  // Implementation
}
```

### Testing Standards

- Write tests for new functionality
- Maintain or improve code coverage
- Test edge cases and error conditions
- Use descriptive test names

```rust
// Rust
#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_validate_peer_id_accepts_valid_format() {
        assert!(validate_peer_id("peer-123").is_ok());
    }

    #[test]
    fn test_validate_peer_id_rejects_invalid_format() {
        assert!(validate_peer_id("invalid").is_err());
    }
}
```

```python
# Python
def test_process_query_returns_correct_number_of_results():
    """Test that process_query respects the max_results parameter."""
    results = process_query("test", max_results=5)
    assert len(results) == 5

def test_process_query_raises_on_empty_query():
    """Test that process_query raises ValueError for empty query."""
    with pytest.raises(ValueError):
        process_query("")
```

---

## Pull Request Process

### Before Submitting

- [ ] Code follows the project's style guidelines
- [ ] All tests pass locally
- [ ] New tests added for new functionality
- [ ] Documentation updated (code comments, README, etc.)
- [ ] Commit messages follow the convention
- [ ] Branch is up to date with main/master

```bash
# Update your branch
git fetch upstream
git rebase upstream/main
```

### Pull Request Template

```markdown
## Description

Brief description of what this PR does.

## Motivation and Context

Why is this change needed? What problem does it solve?
If it fixes an open issue, link to the issue here.

## Type of Change

- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring

## How Has This Been Tested?

Describe the tests you ran and how to reproduce them.

- [ ] Test A
- [ ] Test B

## Checklist

- [ ] My code follows the code style of this project
- [ ] I have updated the documentation accordingly
- [ ] I have added tests to cover my changes
- [ ] All new and existing tests passed
- [ ] My changes generate no new warnings

## Screenshots (if applicable)

Add screenshots to help explain your changes.

## Additional Notes

Any additional information or context.
```

### Review Process

1. **Automated Checks**: CI/CD will run tests and linters
2. **Code Review**: Maintainers will review your code
3. **Discussion**: Address feedback and questions
4. **Approval**: Once approved, a maintainer will merge

### Addressing Feedback

- Respond to all comments
- Make requested changes
- Push new commits (don't force-push during review)
- Mark conversations as resolved when addressed

```bash
# Make changes based on feedback
git add .
git commit -m "Address review feedback: improve error handling"
git push origin feature/your-feature-name
```

---

## Issue Guidelines

### Creating Issues

Use the appropriate template:

**Bug Report:**
```markdown
**Describe the bug**
A clear description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '...'
3. See error

**Expected behavior**
What you expected to happen.

**Actual behavior**
What actually happened.

**Environment**
- OS: [e.g., Ubuntu 22.04]
- Version: [e.g., 0.1.0]
- Rust/Python/Node version: [e.g., 1.70, 3.9, 18.0]

**Additional context**
Any other relevant information.
```

**Feature Request:**
```markdown
**Is your feature request related to a problem?**
A clear description of the problem.

**Describe the solution you'd like**
A clear description of what you want to happen.

**Describe alternatives you've considered**
Alternative solutions or features you've considered.

**Additional context**
Any other relevant information, mockups, or examples.
```

### Working on Issues

- Comment on the issue to express interest
- Wait for assignment or approval before starting work
- Ask questions if requirements are unclear
- Update the issue with progress or blockers

---

## Community

### Communication Channels

- **Slack**: [kwaaiailab.slack.com](https://kwaaiailab.slack.com)
  - `#contributors` - General contributor discussions
  - `#dev-*` - Project-specific development channels
  - `#research` - Research collaborations
- **GitHub Discussions**: For longer-form discussions and Q&A
- **Email**: [contributors@kwaai.ai](mailto:contributors@kwaai.ai)

### Getting Help

- Check the project's README and documentation
- Search existing issues and discussions
- Ask in the appropriate Slack channel
- Create a GitHub issue if you've found a bug

### Recognition

We value all contributions! Contributors are:

- Listed in project CONTRIBUTORS files
- Mentioned in release notes
- Recognized in the community

---

## License

By contributing to Kwaai-AI-Lab, you agree that your contributions will be licensed under the same license as the project you're contributing to. Most projects use:

- **MIT License** - For libraries and tools
- **Apache 2.0** - For larger frameworks
- **GPL v3** - For applications

Check the LICENSE file in the specific repository for details.

---

## Questions?

If you have questions about contributing, reach out:

- **Slack**: [kwaaiailab.slack.com](https://kwaaiailab.slack.com)
- **Email**: [contributors@kwaai.ai](mailto:contributors@kwaai.ai)
- **GitHub Discussions**: Create a discussion in the relevant repository

---

Thank you for contributing to Kwaai! Your efforts help democratize AI and build a better future for everyone. 🚀
