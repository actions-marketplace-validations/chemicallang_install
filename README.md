# Setup Chemical Action

This GitHub Action installs the **Chemical** compiler and adds it to the system `PATH`. It is designed to be fast, cross-platform, and dependencies-free (only requires `curl` and `git`, which are standard on GitHub Runners).

## Features
- **Fast Installation**: Direct binary download and extraction.
- **Auto-Versioning**: Automatically fetches and installs the latest stable release by default.
- **Cross-Platform**: Support for `ubuntu-latest` and `windows-latest`.
- **Environment Integration**: Automatically sets `CHEMICAL_HOME` and updates `GITHUB_PATH`.

## Usage

Add this step to your workflow:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest # or windows-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Chemical
        uses: chemicallang/install@v1.1 # or @main
        with:
          version: 'latest' # Optional: Specify a tag like 'v0.0.30'
          
      - name: Verify Installation
        run: chemical --version
```

## Inputs

| Name      | Description                                                                                         | Default  |
|-----------|-----------------------------------------------------------------------------------------------------|----------|
| `version` | The version of Chemical to install. Set to `latest` to automatically fetch the most recent release. | `latest` |
| `variant` | The variant of Chemical to install (e.g., `tcc`).                                                   | (empty)  |

## Environment Variables
This action sets the following environment variables for subsequent steps:
- `CHEMICAL_HOME`: The path to the directory where Chemical is installed.
- `PATH`: Updated to include the `chemical` binary.

---
Created by the [Chemical Language Foundation](https://github.com/chemicallang).