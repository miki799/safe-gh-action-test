# safe-gh-action-test

## Input/Context Flow Demonstrator

This action intentionally demonstrates unsafe dataflow patterns where untrusted inputs or workflow context values flow into:
- command execution,
- environment variables,
- outputs.

It is designed for security testing and CI policy validation.

### Usage

```yaml
name: Demo
on:
  workflow_dispatch:
    inputs:
      user_text:
        description: "Test string"
        required: true

jobs:
  demo:
    runs-on: ubuntu-latest
    steps:
      - uses: YOUR_ORG/YOUR_ACTION_REPO@v1
        with:
          user_text: ${{ inputs.user_text }}