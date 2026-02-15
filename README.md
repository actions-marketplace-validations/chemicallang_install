# Setup Chemical Action

This action installs the Chemical compiler and adds it to the system PATH.

## Features
- **Fast Installation**: Uses a direct download and extraction method.
- **Version Support**: Install specific versions (e.g., `v0.0.30`) or the `latest` stable release.
- **Cross-Platform**: Works on `ubuntu-latest` and `windows-latest` runners.

## Usage

```yaml
steps:
  - uses: actions/checkout@v4
  - name: Setup Chemical
    uses: chemicallang/chemical/action@main
    with:
      version: 'latest'
  - run: chemical --version
```

## Inputs

| Name | Description | Default |
|------|-------------|---------|
| `version` | Version of Chemical to install | `latest` |