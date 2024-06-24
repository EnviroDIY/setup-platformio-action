# Setup PlatformIO
[![Test action](https://github.com/EnviroDIY/setup-platformio-action/actions/workflows/test-action.yml/badge.svg)](https://github.com/EnviroDIY/setup-platformio-action/actions/workflows/test-action.yml)

This actions sets up PlatformIO for use in actions.

## Usage

### Use newest PlatformIO version
```yaml
- name: Setup PlatformIO
  uses: EnviroDIY/setup-platformio-action@v1.0.2
```

### Specify the version of PlatformIO you want to use
```yaml
- name: Setup PlatformIO
  uses: EnviroDIY/setup-platformio-action@v1.0.2
  with:
    platformio-version: "6.1"
```

> See [inputs](#platformio-version-optional) for more info.

### Example workflow file
To use this example, create a `.github/workflows/build-platformio.yml` file in your repository and paste the contents below in it.

```yaml
name: Build PlatformIO project
on:
  # Triggers the workflow on push or pull request events but only for the main branch
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      # Checkout repository
      - name: Checkout code
        uses: actions/checkout@v4

      # Setup PlatformIO in PATH
      - name: Setup PlatformIO
        uses: EnviroDIY/setup-platformio-action@v1.0.2

      # Build the PlatformIO project
      - name: Build PlatformIO project
        run: pio run
```

### Inputs
Use the `with` keyword to specify these inputs

#### `platformio-version` (optional)
Specify the PlatformIO to set up. Use semantic versioning (e.g. "6.1.11", "6.1" or "6"). If no version is specified, the newest version is used.

## License
Distributed under the MIT license. See [LICENSE.md](LICENSE.md) for more information.

## Acknowledgements
- [PlatformIO](https://platformio.org/)
