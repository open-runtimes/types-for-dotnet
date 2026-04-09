# Publishing

This package is published to [NuGet](https://www.nuget.org/packages/OpenRuntimes.Types).

## Setup

1. Create a NuGet account at https://www.nuget.org
2. Generate an API key at https://www.nuget.org/account/apikeys
   - Select "Push new packages and package versions" scope
   - Set the glob pattern to `OpenRuntimes.*`
3. Add the API key as a GitHub Actions secret:
   - Secret name: `NUGET_API_KEY`
   - Secret value: the generated API key

## Publishing

Publishing is automated via GitHub Actions. To publish a new version:

1. Create a new GitHub release with a tag matching the desired version (e.g., `0.1.0`)
2. The workflow will automatically update the version in the .csproj and publish to NuGet

## Manual Publishing

```bash
dotnet pack --configuration Release
dotnet nuget push ./bin/Release/OpenRuntimes.Types.*.nupkg --api-key YOUR_API_KEY --source https://api.nuget.org/v3/index.json
```
