# Semantic Versioning

## Overview
[Semantic Versioning (SemVer)](https://semver.org/) is a versioning system that provides a clear and predictable format for managing software releases. The version format is:  
**MAJOR.MINOR.PATCH**

---

## Version Format

1. **MAJOR** (`x.0.0`):  
   Incremented when:  
   - There are incompatible changes (backward-incompatible).  
   - Features or APIs are removed.  
   - Significant changes are made to the codebase or architecture.  
   **Example**: `1.0.0 → 2.0.0`

2. **MINOR** (`0.x.0`):  
   Incremented when:  
   - New features are added in a backward-compatible manner.  
   - Existing APIs or behaviors remain unaffected.  
   **Example**: `1.1.0 → 1.2.0`

3. **PATCH** (`0.0.x`):  
   Incremented when:  
   - Bugs or minor issues are fixed.  
   - Changes do not introduce new features or modify existing behaviors.  
   **Example**: `1.0.1 → 1.0.2`

---

## Principles

1. **Initial Development**:  
   Begin with version `0.1.0` during early development stages (prototype or pre-release).

2. **Stable Release**:  
   Transition to `1.0.0` for the first stable and production-ready version.

3. **Immutability**:  
   Once released, a version number must not be modified. Any changes require a new version.

---

## Best Practices

### Pre-release Versions  
- Use `MAJOR.MINOR.PATCH-PRERELEASE` for versions in testing or pre-release phases.  
  **Examples**:  
  - `1.0.0-alpha`  
  - `1.0.0-beta`  
  - `1.0.0-rc.1`

### Build Metadata  
- Append additional build information using `MAJOR.MINOR.PATCH+BUILD`.  
  **Examples**:  
  - `1.0.0+20250109`  
  - `1.2.3+exp.sha.5114f85`

### Documentation
- Maintain a `CHANGELOG.md` to document changes for each release.

### Git Tagging  
- [Use Git tags to mark releases.](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases)  
  **Commands**:  
  ```bash
  git tag -a v1.0.0 -m "Initial stable release"
  git push origin --tags
