# CD Testing

## Development
`Master` is a main development branch. All push events to the master branch trigger staging CD (`.github/workflows/staging.yml`)

## Release
`Release` is a main release branch. Only pushing a new tag triggers release CD (`.github/workflows/release.yml`)

## Release example
- `git checkout release`
- `git merge master`
- `git push release` - doesn't trigger deployment
- `git tag v1.0.0` - create a tag on current commit
- `git push origin v1.0.0` - pushes tag and trigger release CD