
## Supported Platforms

Please refer to the [Requirements](./REQUIREMENTS.md) document for support matrices.

Our editor uses DirectX and must be ran in Windows, but you can host and play your game on any desktop os that supports OpenGL.

We're open to expanding to new platforms (mobile, web, etc) but don't have the capacity to do so at this time. If you're interested in helping out let us know!

## Compiling/Development

### Dependencies

#### Required

- [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0), verified for v8.0.12 (SDK 8.0.405)
- git: required for cloning submodules, if you want to do this manually you don't need this and use the .zip download but that is not supported
  - Tested on 2.47.1

### Getting started

After cloning or updating,
- on all platforms run `git submodule update --init --recursive`
- on non-Windows platforms, additionally run `git apply disable-windows-only.patch`

Before updating on non-Windows platforms, run `git apply -R disable-windows-only.patch`

**Note**: The client **will not run** from the debugger **without** assets being added into `assets/development/client` (e.g. from Intersect-Assets)!

It is recommended that you create a symbolic link from your own custom resources repository (or a clone of the `main_full` branch of `Intersect-Assets`) to `assets/development/client/resources` for development.

### Compiling

To compile either use an IDE or one of the following commands:
- `dotnet build -p:Configuration=Debug -p:PackageVersion=0.8.0-beta -p:Version=0.8.0`
  - Debug builds, all debug builds will _not_ create single-file binary outputs
- `dotnet build -p:Configuration=Release -p:PackageVersion=0.8.0-beta -p:Version=0.8.0`
	- Release builds will create single-file binary outputs but to get a clean output use `dotnet publish`
- `dotnet publish -p:Configuration=Release -p:PackageVersion=0.8.0-beta -p:Version=0.8.0 -r <runtime-id>`
	- e.g. `dotnet publish -p:Configuration=Release -p:PackageVersion=0.8.0-beta -p:Version=0.8.0 -r linux-x64`
	- The automated builds use the above command for the RIDs `linux-x64`, `osx-x64` and `win-x64`
 * Use our [community forums](https://ascensiongamedev.com/) for support questions.
 * The [official documentation](https://docs.freemmorpgmaker.com) is on our website.
 * The official [Intersect Assets](https://github.com/AscensionGameDev/Intersect-Assets) repo is separate and can be found on GitHub.
 * Download stable and development [installers and packages](https://freemmorpgmaker.com/download).
