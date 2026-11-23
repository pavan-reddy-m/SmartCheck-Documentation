# GitHub Workflow and Technical Documentation

## 1. Introduction

GitHub is a cloud-based platform used for hosting Git repositories,
version control, software collaboration, and development automation.

It enables development teams to manage source code, track changes,
review code, and automate software delivery.

## 2. Introduction to Git

Git is a distributed version control system used to track changes
in source code throughout the software development lifecycle.

### 2.1 Key Features of Git

- Distributed version control
- Branch management
- Version history
- Code merging
- Change tracking
- Collaboration support

### 2.2 Common Git Commands

| Command | Description |
|---|---|
| git init | Initialize a Git repository |
| git clone | Clone an existing repository |
| git status | Check working directory status |
| git add | Stage changes |
| git commit | Save changes to local history |
| git push | Upload commits to remote repository |
| git pull | Fetch and integrate remote changes |
| git branch | List or manage branches |
| git merge | Merge branches |

## 3. Introduction to GitHub

GitHub is a platform that hosts Git repositories and provides
tools for developers to collaborate on software projects.

### 3.1 Key Features of GitHub

- Repository hosting
- Pull requests
- Code reviews
- Issues and project management
- GitHub Actions
- Branch protection
- Security and access management

## 4. Git vs GitHub

| Git | GitHub |
|---|---|
| Distributed version control system | Cloud-based development platform |
| Tracks source code changes | Hosts Git repositories |
| Works locally | Supports remote collaboration |
| Supports branches and merges | Provides pull requests and reviews |
| Open-source software | Offers free and paid plans |

## 5. GitHub Development Workflow

The GitHub Flow is a lightweight development workflow used
to manage and review software changes.

### 5.1 Workflow Steps

1. Create a GitHub repository.
2. Create a feature branch from the main branch.
3. Make application code changes.
4. Commit changes to the feature branch.
5. Push the feature branch to GitHub.
6. Create a pull request.
7. Review and approve the changes.
8. Merge the pull request into the main branch.

### 5.2 Benefits

- Organized development process
- Better collaboration
- Code review before integration
- Version history management
- Reduced integration risks

## 6. References

- Git Documentation: https://git-scm.com/doc
- GitHub Documentation: https://docs.github.com/en
- GitHub Flow: https://docs.github.com/en/get-started/using-github/github-flow

## 7. GitHub Repository Management

A GitHub repository stores application source code, documentation,
configuration files, and version history.

### 7.1 Repository Visibility

| Type | Description | Use Case |
|---|---|---|
| Public | Accessible to everyone | Open-source projects |
| Private | Accessible to authorized users | Company applications |
| Internal | Accessible within an enterprise | Enterprise collaboration |

Internal repositories are available to eligible GitHub Enterprise
organizations.

### 7.2 Repository Structure

Example application repository:

```text
smartcheck-application/
├── src/
├── tests/
├── docs/
├── .github/
│   └── workflows/
├── Dockerfile
├── README.md
└── .gitignore
```

### 7.3 Branching Strategy

Branches allow developers to work independently without directly
modifying the main application codebase.

Common branch names:

| Branch | Purpose |
|---|---|
| main | Production-ready code |
| develop | Development integration |
| feature/* | New functionality |
| bugfix/* | Bug fixes |
| hotfix/* | Urgent production fixes |

### 7.4 GitHub Flow vs Git Flow

GitHub Flow is a lightweight branching strategy where developers
create short-lived feature branches from the main branch and
merge changes through pull requests.

Git Flow is a structured branching strategy that uses main,
develop, feature, release, and hotfix branches.

### 7.5 Pull Requests and Code Reviews

A pull request is a request to merge code changes from one branch
into another branch.

Typical process:

1. Create a feature branch.
2. Develop and commit code changes.
3. Push the feature branch to GitHub.
4. Create a pull request.
5. Review the code.
6. Run automated checks.
7. Approve and merge the changes.

### 7.6 Branch Protection

Branch protection helps prevent unauthorized or unreviewed changes.

Recommended configurations:

- Require pull requests before merging.
- Require approving reviews.
- Require automated status checks.
- Restrict force pushes.
- Restrict branch deletion.
- Apply appropriate access permissions.

### 7.7 Repository Access Management

| Role | Responsibility |
|---|---|
| Read | View and clone repository |
| Triage | Manage issues and pull requests |
| Write | Push code and contribute |
| Maintain | Manage repository without full administrative access |
| Admin | Full repository administration |

Follow the principle of least privilege when assigning
repository permissions.

## 8. References

- GitHub Repositories:
  https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories
- GitHub Rulesets:
  https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets
- Branch Protection:
  https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches
- GitHub Flow:
  https://docs.github.com/en/get-started/using-github/github-flow

## 9. GitHub Actions

GitHub Actions is a CI/CD automation platform integrated
into GitHub. It automates software development tasks such
as building, testing, scanning, and deploying applications.

### 9.1 Benefits of GitHub Actions

- Automates software builds.
- Executes automated tests.
- Supports continuous integration.
- Supports continuous delivery and deployment.
- Integrates with Docker and cloud platforms.
- Supports reusable automation.
- Reduces manual deployment activities.

### 9.2 Core Components

| Component | Description |
|---|---|
| Workflow | Complete automation process |
| Event | Activity that triggers a workflow |
| Job | Collection of steps executed on a runner |
| Step | Individual task within a job |
| Action | Reusable automation component |
| Runner | Machine that executes workflow jobs |

### 9.3 How GitHub Actions Works

1. Developer pushes code to GitHub.
2. GitHub detects the configured event.
3. The corresponding workflow starts.
4. GitHub schedules the workflow jobs.
5. A runner executes each job.
6. Steps execute within each job.
7. GitHub reports the workflow result.

Jobs run in parallel by default unless job dependencies
are configured using the needs keyword.

### 9.4 GitHub Actions Runners

A runner is a machine that executes GitHub Actions jobs.

Two major runner types are available:

**GitHub-hosted runners**

- Managed by GitHub.
- Available with Linux, Windows, and macOS environments.
- Infrastructure maintenance is handled by GitHub.
- Usage limits and billing depend on the plan.

**Self-hosted runners**

- Managed by the organization.
- Can run on physical servers, virtual machines, or cloud infrastructure.
- Support customized execution environments.
- Require infrastructure maintenance and security management.

### 9.5 Workflow YAML Files

GitHub Actions workflows are written in YAML format.

Workflow files must be stored in:

.github/workflows/

Example structure:

```text
repository/
└── .github/
    └── workflows/
        ├── ci.yml
        ├── cd.yml
        └── security-scan.yml
```

### 9.6 Important Workflow Keywords

| Keyword | Purpose |
|---|---|
| name | Defines workflow name |
| on | Defines workflow triggers |
| permissions | Defines workflow token permissions |
| jobs | Defines workflow jobs |
| runs-on | Selects runner environment |
| steps | Defines tasks within a job |
| uses | Executes a reusable action |
| run | Executes shell commands |
| needs | Defines job dependencies |
| env | Defines environment variables |
| secrets | Accesses configured secrets |

### 9.7 Example GitHub Actions CI Workflow

The following example demonstrates a basic Python CI pipeline.

```yaml
name: Python CI Pipeline

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.12'

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install pytest

      - name: Run tests
        run: |
          pytest
```

**Workflow explanation:**

1. The workflow triggers when code is pushed to main
   or a pull request targets main.
2. GitHub provisions an Ubuntu runner.
3. The checkout action downloads repository code.
4. Python 3.12 is configured.
5. Required dependencies are installed.
6. Pytest executes automated tests.
7. The workflow reports success or failure.

This is an illustrative example. The actual dependency
installation and test commands depend on the application.

### 9.8 Continuous Integration (CI)

Continuous Integration is the practice of frequently
integrating code changes into a shared repository.

Typical CI activities:

- Source code checkout.
- Dependency installation.
- Application compilation or build.
- Unit testing.
- Integration testing.
- Code quality analysis.
- Security checks.

### 9.9 Continuous Delivery and Continuous Deployment

**Continuous Delivery:**

Application changes are automatically built and tested
and prepared for deployment. Production deployment may
require manual approval.

**Continuous Deployment:**

Every change that successfully passes the required
pipeline checks is automatically deployed to production.

### 9.10 GitHub Actions Security

Recommended security practices:

- Store sensitive credentials in GitHub Secrets.
- Apply least-privilege workflow permissions.
- Avoid exposing credentials in workflow logs.
- Pin third-party actions to verified commit SHAs.
- Review third-party actions before using them.
- Protect production deployment environments.
- Avoid executing untrusted pull-request code with privileged secrets.

## 10. References

- Understanding GitHub Actions:
  https://docs.github.com/en/actions/get-started/understand-github-actions
- Workflow Documentation:
  https://docs.github.com/en/actions/concepts/workflows-and-actions/workflows
- Workflow Syntax:
  https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax
- Creating an Example Workflow:
  https://docs.github.com/en/actions/tutorials/create-an-example-workflow
- Secure Use Reference:
  https://docs.github.com/en/actions/reference/security/secure-use
