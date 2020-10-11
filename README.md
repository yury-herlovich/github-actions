# CD Testing

### Development
`Master` is a main development branch. All push events to the master branch trigger staging CD (`.github/workflows/staging.yml`)

### Release
`Release` is a main release branch. Only pushing a new tag triggers release CD (`.github/workflows/release.yml`)

### Manual deployment
Release can be triggered manual through `Manual Release CD` workflow with any version (tag) (`.github/workflows/manual.yml`)

## Examples

### Staging
- `git push origin master` - will trigger deployment to staging

### Release
- `git checkout release`
- `git merge master`
- `git push origin release` - doesn't trigger deployment
- `git tag v1.0.0` - creates a tag on current commit
- `git push origin v1.0.0` - pushes tag and triggers Release CD

### Manual
- Open GitHub Actions
- Select `Manual Release CD`
- Click `Run workflow`
- Select branch `Release`
- Enter version/tag