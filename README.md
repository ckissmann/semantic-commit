# 🚀 Semantic Commit Generator

> A beautiful, interactive CLI tool for creating semantic commits with ease.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Rust](https://img.shields.io/badge/rust-%23000000.svg?style=flat&logo=rust&logoColor=white)](https://www.rust-lang.org/)
[![Made with ❤️](https://img.shields.io/badge/Made%20with-%E2%9D%A4%EF%B8%8F-red.svg)](https://github.com/yourusername/semantic-commit)

![Demo](docs/demo.gif)

## ✨ Features

- 🎨 **Beautiful Interactive CLI** - Intuitive prompts with color themes
- 📋 **Conventional Commits** - Follows the [Conventional Commits](https://www.conventionalcommits.org/) specification
- 🌍 **Internationalization** - Multi-language support via i18n
- ✅ **Pre-commit Validation** - Runs tests and lints before committing
- 📝 **Rich Editor Support** - Write detailed commit bodies in your favorite editor
- 🔗 **Issue Tracking** - Automatically link issues in commits
- 🚢 **Auto Push** - Optional automatic push after commit
- 🎯 **Breaking Change Support** - Mark breaking changes explicitly

## 📦 Installation

### From Source

```bash
# Clone the repository
git clone https://github.com/ckissmann/semantic-commit.git
cd semantic-commit

# Build and install
cargo install --path .
```

### From Cargo

```bash
cargo install semantic-commit
```

### Binary Releases

Download pre-built binaries from the [Releases](https://github.com/ckissmann/semantic-commit/releases) page.

## 🚀 Quick Start

Simply run:

```bash
semantic-commit
```

The tool will guide you through:

1. **Running Tests & Lints** - Automatic validation
2. **Selecting Commit Type** - Choose from predefined types
3. **Adding Scope** (optional) - Specify the scope of changes
4. **Writing Description** - Short, imperative description
5. **Adding Body** (optional) - Detailed explanation
6. **Marking Breaking Changes** - Flag incompatible changes
7. **Linking Issues** - Reference GitHub issues
8. **Auto Push** (optional) - Push to remote after commit

## 📖 Semantic Commit Rules

This tool follows the **Conventional Commits** specification:

### Commit Message Format

```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Example

```
feat(auth): add OAuth2 login support

Implemented Google and GitHub OAuth providers.
Users can now login using their social accounts.

BREAKING CHANGE: Old session tokens are no longer valid
Closes #123
Closes #456
```

## 🏷️ Commit Types

| Type | Icon | Description | When to Use |
|------|------|-------------|-------------|
| `feat` | ✨ | New feature | Adding new functionality |
| `fix` | 🐛 | Bug fix | Fixing a bug |
| `docs` | 📚 | Documentation | Changes to documentation only |
| `style` | 💄 | Code style | Formatting, white-space, etc. (no code change) |
| `refactor` | ♻️ | Code refactoring | Neither fixes a bug nor adds a feature |
| `perf` | ⚡ | Performance | Improving performance |
| `test` | ✅ | Tests | Adding or updating tests |
| `build` | 🔧 | Build system | Changes to build system or dependencies |
| `ci` | 👷 | CI/CD | Changes to CI configuration files |
| `chore` | 🔨 | Maintenance | Other changes that don't modify src or test files |
| `revert` | ⏪ | Revert | Reverts a previous commit |

### Type Guidelines

#### `feat` - Features
```bash
feat: add user registration
feat(api): implement GraphQL endpoint
feat(ui)!: redesign dashboard layout
```

**Use when:**
- Adding new functionality
- Implementing new features
- Creating new components/modules

#### `fix` - Bug Fixes
```bash
fix: resolve memory leak in worker thread
fix(auth): correct token validation logic
fix(ui): fix button alignment on mobile
```

**Use when:**
- Fixing bugs
- Resolving issues
- Correcting unexpected behavior

#### `docs` - Documentation
```bash
docs: update API documentation
docs(readme): add installation instructions
docs: fix typos in contributing guide
```

**Use when:**
- Updating README
- Writing/updating documentation
- Adding code comments (substantial ones)

#### `style` - Code Style
```bash
style: format code with prettier
style(api): apply consistent naming convention
style: remove trailing whitespace
```

**Use when:**
- Formatting code
- Fixing linting issues
- Renaming variables (no logic change)

#### `refactor` - Refactoring
```bash
refactor: simplify authentication logic
refactor(db): optimize query structure
refactor: extract helper function
```

**Use when:**
- Restructuring code
- Improving code quality
- Changing implementation without changing behavior

#### `perf` - Performance
```bash
perf: optimize image loading
perf(db): add index to user table
perf: lazy load components
```

**Use when:**
- Improving performance
- Optimizing algorithms
- Reducing resource usage

#### `test` - Tests
```bash
test: add unit tests for auth service
test(api): increase test coverage
test: fix flaky integration test
```

**Use when:**
- Adding tests
- Updating tests
- Fixing test issues

#### `build` - Build System
```bash
build: upgrade webpack to v5
build(deps): bump lodash from 4.17.19 to 4.17.21
build: add docker configuration
```

**Use when:**
- Updating dependencies
- Changing build configuration
- Modifying deployment scripts

#### `ci` - Continuous Integration
```bash
ci: add GitHub Actions workflow
ci: configure automated testing
ci: update deployment pipeline
```

**Use when:**
- Modifying CI/CD pipelines
- Updating GitHub Actions
- Changing deployment configs

#### `chore` - Maintenance
```bash
chore: update gitignore
chore: clean up unused files
chore: update license year
```

**Use when:**
- Routine maintenance tasks
- Updating configs
- Cleaning up codebase

#### `revert` - Reverting Changes
```bash
revert: revert "feat: add experimental feature"
```

**Use when:**
- Reverting previous commits
- Rolling back changes

## 🎯 Scope Guidelines

The **scope** is optional and specifies the part of the codebase affected:

### Common Scopes

```
api         - API/Backend changes
ui          - User interface changes
auth        - Authentication/Authorization
db          - Database changes
docs        - Documentation
config      - Configuration
core        - Core functionality
utils       - Utility functions
tests       - Test-related changes
deps        - Dependencies
```

### Examples

```bash
feat(api): add user search endpoint
fix(ui): correct button styling on mobile
docs(readme): add installation section
refactor(auth): simplify token generation
perf(db): add index to improve query speed
```

## 🚨 Breaking Changes

Mark breaking changes with `!` after the type/scope:

```bash
feat!: remove deprecated API endpoints
feat(api)!: change response format

BREAKING CHANGE: The API now returns JSON instead of XML
```

**When to mark as breaking:**
- Removing features
- Changing public APIs
- Modifying behavior that users depend on
- Upgrading major versions of dependencies

## 🔗 Linking Issues

Reference issues in the footer:

```bash
feat: add dark mode support

Closes #42
Closes #123
Fixes #456
Resolves #789
```

**Keywords:**
- `Closes` - Closes an issue
- `Fixes` - Fixes a bug
- `Resolves` - Resolves an issue

## 🌍 Internationalization

The tool supports multiple languages. Set your language:

```bash
# Set language via environment variable
export LANG=de_DE.UTF-8  # German
export LANG=en_US.UTF-8  # English
```

### Supported Languages

- 🇬🇧 English
- 🇩🇪 German

Want to add your language? See [CONTRIBUTING.md](CONTRIBUTING.md)!

## ⚙️ Configuration

Create a `semantic-commit.toml` in your project root:

```toml
# Pre-commit checks
[pre_commit]
run_tests = true
run_lint = true
run_format = false

# Default values
[defaults]
push = false
breaking = false

# Custom commit types
[[custom_types]]
name = "wip"
description = "🚧 Work in Progress"
```

## 🛠️ Development

### Prerequisites

- Rust 1.70 or higher
- Git

### Setup

```bash
# Clone repository
git clone https://github.com/ckissmann/semantic-commit.git
cd semantic-commit

# Run tests
cargo test

# Run lints
cargo clippy --all-targets --all-features -- -D warnings

# Build
cargo build --release

# Run
cargo run
```

### Project Structure

```
semantic-commit/
├── src/
│   ├── main.rs           # Main CLI logic
│   └── lib.rs            # Library functions
├── i18n/                 # Translations
│   ├── en/               # English
│   └── de/               # German
├── docs/                 # Documentation
├── tests/                # Integration tests
├── Cargo.toml
└── README.md
```

## 🤝 Contributing

Contributions are welcome! Please read our [Contributing Guide](CONTRIBUTING.md) first.

### How to Contribute

1. Fork the repository
2. Create a feature branch: `git checkout -b feat/amazing-feature`
3. Commit your changes: `semantic-commit` 😉
4. Push to the branch: `git push origin feat/amazing-feature`
5. Open a Pull Request

### Code of Conduct

This project adheres to the Contributor Covenant [Code of Conduct](CODE_OF_CONDUCT.md).

## 📝 Changelog

See [CHANGELOG.md](CHANGELOG.md) for a list of changes.

All changes follow [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) format.

## 🐛 Known Issues

- Editor integration requires `$EDITOR` environment variable to be set
- Windows: May require admin rights for git operations

Report issues on [GitHub Issues](https://github.com/ckissmann/semantic-commit/issues).

## 📚 Resources

- [Conventional Commits Specification](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)
- [Keep a Changelog](https://keepachangelog.com/)
- [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 🙏 Acknowledgments

- [dialoguer](https://github.com/console-rs/dialoguer) - Beautiful CLI prompts
- [Conventional Commits](https://www.conventionalcommits.org/) - Specification
- [gitmoji](https://gitmoji.dev/) - Emoji inspiration

## 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=ckissmann/semantic-commit&type=Date)](https://star-history.com/#yourusername/semantic-commit&Date)

## 💬 Support

- 📧 Email: your.email@example.com
- 💬 Discussions: [GitHub Discussions](https://github.com/yourusername/semantic-commit/discussions)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/semantic-commit/issues)

---

Made with ❤️ by [Your Name](https://github.com/ckissmann)

⭐ Star this repo if you find it helpful!