### Repro for an issue with [dotnet-releaser](https://github.com/xoofx/dotnet-releaser).

Steps taken to create this repo:

```
dotnet new console
dotnet-releaser new --project ReleaserRepro.csproj
```

Steps to reproduce issue:

```
❯ dotnet-releaser build --force dotnet-releaser.toml
info: dotnet-releaser[0]
      Loading configuration from C:\Users\reill\source\releaser-repro\dotnet-releaser.toml
fail: dotnet-releaser[1]
      The changelog.path was not setup
info: dotnet-releaser[2]
      Adding default profile for platform [win-x64] with [Zip] package
      Adding default profile for platform [win-arm] with [Zip] package
      Adding default profile for platform [win-arm64] with [Zip] package
      Adding default profile for platform [linux-x64] with [Deb, Tar] packages
      Adding default profile for platform [linux-arm] with [Deb, Tar] packages
      Adding default profile for platform [linux-arm64] with [Deb, Tar] packages
      Adding default profile for platform [rhel-x64] with [Rpm, Tar] packages
      Adding default profile for platform [osx-x64] with [Tar] package
      Adding default profile for platform [osx-arm64] with [Tar] package

fail: dotnet-releaser[3]
      Failing to run dotnet msbuild -p:Configuration=Release -p:CustomAfterMicrosoftCommonTargets="C:\Users\reill\.dotnet\tools\.store\dotnet-releaser\0.1.0\dotnet-releaser\0.1.0\tools\net6.0\any\dotnet-releaser.targets" -nologo -logger:BinaryLogger,"C:\Users\reill\.dotnet\tools\.store\dotnet-releaser\0.1.0\dotnet-releaser\0.1.0\tools\net6.0\any\dotnet-releaser-binary-logger.dll";"C:\Users\reill\AppData\Local\Temp\tmpC534.tmp.binlog" -t:DotNetReleaserGetPackageInfo C:\Users\reill\source\releaser-repro\ReleaserRepro.csproj. Reason: MSBUILD : error MSB4016: The build stopped unexpectedly because the "ReusableLogger" logger failed unexpectedly during initialization. Object reference not set to an instance of an object.
```

