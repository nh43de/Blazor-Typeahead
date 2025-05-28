# Versioning Strategy

This project uses [MinVer](https://github.com/adamralph/minver) for automatic versioning based on Git tags and commits.

## How it works

### Release Versions
- When you create a Git tag with format `v1.2.3`, MinVer will use `1.2.3` as the version
- These are published to NuGet as stable releases
- Example: `git tag v1.0.0` → NuGet package version `1.0.0`

### Pre-release Versions
- Commits on the main branch without tags get pre-release versions
- Format: `{next-version}-preview.{height}+{commit-sha}`
- These are published to NuGet as pre-release packages
- Example: `1.0.1-preview.5+abc1234`

## Workflow Behavior

### Main Branch Pushes
- Builds and tests the code
- Packs the NuGet package with MinVer version
- Publishes to NuGet as pre-release (unless it's a tagged commit)

### Tagged Commits
- Same as main branch pushes
- But publishes to NuGet as a stable release
- Also deploys the sample site to GitHub Pages

### Pull Requests
- Only builds and tests
- No publishing or deployment

## Creating a Release

1. Ensure your code is ready for release
2. Create and push a tag: `git tag v1.2.3 && git push origin v1.2.3`
3. The workflow will automatically publish the stable version to NuGet
4. Optionally create a GitHub release for better visibility

## MinVer Configuration

The project is configured with:
- `MinVerDefaultPreReleaseIdentifiers`: `preview` - Sets the pre-release identifier
- `MinVerTagPrefix`: `v` - Expects tags to start with 'v' 