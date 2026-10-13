[update-readmes]   Mode: rewrite — migrating to template structure...
# git-repo-manager

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/git-repo-manager) [![KDE Eco](https://img.shields.io/badge/KDE%20Eco-certified-brightgreen?logo=kde&logoColor=white&style=flat-square)](https://eco.kde.org/) [![Blue Angel](https://img.shields.io/badge/Blue%20Angel-DE--UZ%20215-0055a4?style=flat-square)](https://www.blauer-engel.de/en/certification/criteria)



<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/git-repo-manager.git
cd git-repo-manager
```

## Usage


![git-repo-manager](docs/cli.svg)

### Basic Commands

```bash
# Show help
python cli.py --help

# Clone user repositories
python cli.py clone-user

# Clone group repositories
python cli.py clone-groups

# Clone GitHub user repositories
python cli.py clone-github-user

# Clone GitHub organization repositories
python cli.py clone-github-org organization-name

# Update Composer dependencies
python cli.py update-composer

# Clone all repositories and update Composer dependencies
python cli.py clone-all --update-composer

# Clone to custom output directory
python cli.py clone-user --output-dir /path/to/custom/directory
python cli.py clone-groups --output-dir /path/to/custom/directory
python cli.py clone-github-user --output-dir /path/to/custom/directory

# Initialize configuration (interactive)
python cli.py init-config

# Initialize configuration (non-interactive)
python cli.py init-config --non-interactive

# Show configuration information
python cli.py config-info

# Validate configuration
python cli.py validate-config

### Advanced Usage

```bash
# Clone user repositories with custom settings
python cli.py clone-user \
  --gitlab-url https://gitlab.company.com \
  --token your-token \
  --repo-dir /path/to/repos \
  --max-workers 10

# Clone specific groups
python cli.py clone-groups \
  --group-ids 123456 789012 \
  --repo-dir /path/to/repos

# Clone GitHub user repositories
python cli.py clone-github-user \
  --username username \
  --repo-dir /path/to/repos \
  --max-workers 10

# Clone GitHub organization repositories
python cli.py clone-github-org organization-name \
  --repo-dir /path/to/repos \
  --max-workers 10

# Clone to custom output directory
python cli.py clone-user \
  --output-dir /custom/path \
  --max-workers 10

python cli.py clone-groups \
  --output-dir /custom/path \
  --group-ids 123456 789012

# Update Composer dependencies in specific directory
python cli.py update-composer --directory /path/to/projects

## Configuration


The application uses a YAML configuration file for settings. The tool looks for configuration in this order:
1. Current directory (`config.yml`)
2. User home directory (`~/.git-repo-manager/config.yml`)
3. Default fallback

Environment variables can override these settings.

### Output Directory Management

The tool supports flexible output directory management:

- **Default Directory**: Uses the `repo_dir` setting from configuration
- **Custom Output Directory**: Use `--output-dir` to specify a custom directory for each clone operation
- **Directory Override**: Use `--repo-dir` to override the configured repository directory

**Examples:**
```bash
# Use default directory from config
python cli.py clone-user

# Use custom output directory
python cli.py clone-user --output-dir /path/to/custom/directory

# Override configured repository directory
python cli.py clone-user --repo-dir /path/to/repos

# Combine with other options
python cli.py clone-groups \
  --output-dir /custom/path \
  --group-ids 123456 789012 \
  --max-workers 10
```

The `--output-dir` option takes precedence over the configured `repo_dir` and allows you to organize repositories in different directory structures for different operations.

### Configuration File

You can create a configuration file using the `init-config` command:

```bash
# Interactive configuration setup
python cli.py init-config

# Non-interactive setup (uses defaults)
python cli.py init-config --non-interactive
```

The interactive mode will prompt you for:
- GitLab URL and Personal Access Token
- GitHub URL and Personal Access Token (optional)
- Repository directory
- Maximum concurrent downloads
- Group IDs to clone from
- Composer settings

This will create `~/.git-repo-manager/config.yml` with your settings:

```yaml
gitlab:
  url: "https://gitlab.com"
  private_token: "your-gitlab-token"

github:
  url: "https://api.github.com"
  access_token: "your-github-token"  # Optional

repository:
  repo_dir: "~/gitlab-repos"  # Default repository directory
  max_concurrent_downloads: 5

groups:
  target_group_ids:
    - 2969050   # circlecreative
    - 60830364  # circle-creative-flutter
    # Add your group IDs here

composer:
  enabled: true
  auto_update: false  # Whether to automatically update after cloning
```

### Environment Variables

Environment variables can override configuration file settings:

```bash
export GITLAB_PRIVATE_TOKEN="your-gitlab-token"
export GITLAB_URL="https://gitlab.company.com"
export GITHUB_ACCESS_TOKEN="your-github-token"
export GITHUB_URL="https://api.github.com"
export REPO_DIR="/path/to/repositories"
export MAX_CONCURRENT_DOWNLOADS="10"
```

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/git-repo-manager`](https://github.com/Interested-Deving-1896/git-repo-manager) and mirrored through:

```
Interested-Deving-1896/git-repo-manager  ──►  OpenOS-Project-OSP/git-repo-manager  ──►  OpenOS-Project-Ecosystem-OOC/git-repo-manager
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
| Contributor | Commits |
|---|---|
| [@turahe](https://github.com/turahe) | 13 |
| [@Interested-Deving-1896](https://github.com/Interested-Deving-1896) | 12 |
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream influences recorded._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## Accessibility

<!-- AI:start:accessibility -->
This repo uses automated accessibility auditing via `check-accessibility.yml`.

Checks include: CODEOWNERS ownership coverage, README screen-reader compatibility,
WCAG 2.1 AA HTML compliance, audio overview (espeak-ng), and Braille output (liblouis).




Run the [Check Accessibility](https://github.com/Interested-Deving-1896/git-repo-manager/actions/workflows/check-accessibility.yml)
workflow to generate the first report and accessibility artifacts.
See the [W3C Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/)
for the underlying accessibility reference.
<!-- AI:end:accessibility -->

## License

<!-- AI:start:license -->
[MIT](https://github.com/Interested-Deving-1896/git-repo-manager/blob/master/LICENSE) © 2026 [Interested-Deving-1896](https://github.com/Interested-Deving-1896)
<!-- AI:end:license -->
