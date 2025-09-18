# How to Publish to PyPI

This document explains how to publish the aerodrome-swap-mcp package to PyPI.

## Prerequisites

1. Install the required tools:
```bash
pip install twine build
```

2. Create a PyPI account at https://pypi.org/

3. Generate an API token from your PyPI account settings

## Building the Package

The package has already been configured to build correctly. To build it:

```bash
python -m build
```

This will create:
- `dist/aerodrome_swap_mcp-0.1.0-py3-none-any.whl` (wheel file)
- `dist/aerodrome_swap_mcp-0.1.0.tar.gz` (source distribution)

## Uploading to PyPI

1. Set your PyPI API token as an environment variable:
```bash
export TWINE_USERNAME=__token__
export TWINE_PASSWORD=your_api_token_here
```

2. Upload to TestPyPI first (recommended):
```bash
twine upload --repository testpypi dist/*
```

3. Upload to PyPI:
```bash
twine upload dist/*
```

## Verification

After uploading, you can verify the package is available at:
https://pypi.org/project/aerodrome-swap-mcp/

## Notes

- The package name is `aerodrome-swap-mcp`
- Version is `0.1.0`
- The package includes all necessary files including the OpenAPI specification
- Entry point is `aerodrome-swap-mcp=aerodrome_mcp.server:main`
