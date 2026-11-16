# Changelog

## Unreleased
### Added
- Added `py.typed` file to properly support type checking.
- Enabled Ruff for linting and formatting (replacing Black, isort, flake8).
- Moved development dependencies to `dependency-groups.dev` instead of `optional-dependencies`.

### Fixed
- Put `py.typed` inside the `zen_html` package directory and declare it as package
  data, so built wheels are actually recognized as typed by PEP 561 checkers
  (previously the marker sat at the repository root and never reached the wheel).
- Restored HTML-escaping of `RAW_STR` children in `pretty_dict` output, as per the
  contract established by the test suite since the initial release. The `dict_`
  property still preserves `RAW_STR` children unescaped.

## 0.1.4 - 2025-11-28
### Added
- Support for `H.RAW_STR` to handle unescaped HTML fragments.
- Improved validation for void tags and attributes.

### Changed
- Updated documentation to reflect new API usage.
- Refactored tag generation logic for better maintainability.

### Fixed
- Minor bug fixes in `examples/pandas_pivot.py`.

## 0.1.3 - 2025-11-25
- Allow passing `class_` as `str | Iterable[str] | None` and normalize lists into space-separated class strings.
- Support `children=[...]` keyword argument on every tag; positional and keyword children can no longer be mixed accidentally.
- Document the above ergonomics in both English and Japanese README files.
- Add regression tests for iterable `class_` handling and `children` keyword usage; regenerate tag helpers accordingly.

## 0.1.2 - 2025-11-20
- Initial public release.
