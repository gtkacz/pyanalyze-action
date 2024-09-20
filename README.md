# pyanalyze GitHub Action

A GitHub Action to run [pyanalyze](https://github.com/quora/pyanalyze), a static type analyzer for Python code.

## Overview

This action integrates pyanalyze into your GitHub workflows, allowing you to statically type-check your Python code automatically. It's a great way to catch bugs early and maintain code quality in your project.

## Inputs

### `src`

- **Description**: The source path(s) to run pyanalyze on.
- **Required**: No
- **Default**: `"."` (current directory)
- **Example**: `"./src"`

### `args`

- **Description**: Additional arguments to pass to pyanalyze. You can use `pyanalyze --help` to see all available options.
- **Required**: No
- **Default**: `""` (no additional arguments)
- **Example**: `"--strict-shallow"`

### `version`

- **Description**: The version of pyanalyze to install (e.g., `"==0.33.1"`).
- **Required**: No
- **Default**: `""` (installs the latest version)
- **Example**: `"==0.33.1"`

## Usage

To use this action, include it in your GitHub workflow YAML file. You need to check out your code before running the action.

## Example Workflow

```yaml
name: Static Analysis

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  pyanalyze:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Run pyanalyze
        uses: gtkacz/pyanalyze-action@v1
        with:
          src: "./src"
          args: "--strict-shallow"
          version: "==0.33.1"
```

Replace `gtkacz/pyanalyze-action@v1` with the correct repository and version tag for this action.

## Contributing

Contributions to improve this GitHub Action are welcome! Please feel free to submit issues or pull requests.

## License

This project is licensed under the GNU General Public License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- This action uses [pyanalyze](https://github.com/quora/pyanalyze), created by Quora.
- Thanks to the GitHub Actions team for providing the platform and documentation.

## Support

If you encounter any problems or have any questions, please open an issue in this repository.
