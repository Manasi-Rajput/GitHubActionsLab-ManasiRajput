## Workflows

### 1. Dependent Jobs Workflow (Build → Test → Deploy)
- **Purpose:** This workflow runs when code is pushed to the main branch. It ensures the project builds successfully, passes all tests, and only then proceeds to deployment.
- **Key Concepts:** Uses `runs-on` to define the operating system and `needs` to control job dependencies. Jobs execute in order: build → test → deploy. Also uses `actions/checkout` and `actions/setup-java` to prepare the environment.
- **Challenges:** Understanding how the `needs` keyword controls job order was initially challenging. Ensuring the correct folder structure (.github/workflows/) was required for the workflow to trigger properly.

### 2. Multi-Platform Workflow
- **Purpose:** This workflow runs on pull requests to the main branch. It verifies that the project can run across multiple operating systems.
- **Key Concepts:** Demonstrates `runs-on` with different environments (ubuntu-latest, windows-latest, macos-latest). The jobs run independently and in parallel. Each job executes OS-specific commands and creates a simple file.
- **Challenges:** Handling OS-specific commands such as `uname -a` for Linux/macOS and `systeminfo` for Windows required understanding platform differences.

## Key Concepts Demonstrated
- Automation of development workflows using GitHub Actions
- Continuous Integration through automated build and test processes
- Job dependencies using `needs`
- Multi-platform execution using `runs-on`
- Environment setup using reusable GitHub Actions

## Challenges Faced
- Ensuring workflows triggered correctly on push and pull request events
- Understanding job execution order using dependencies
- Configuring Java consistently across runners
- Troubleshooting workflow failures due to configuration issues
