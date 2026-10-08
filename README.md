# PowerMon downloads

The download page for **PowerMon**, a per-app power and battery monitor for **Windows 11**.

- Page: https://vampxlr.github.io/powermon-download/
- Downloads: [Releases](https://github.com/vampxlr/powermon-download/releases)

This repository holds only the page and the release files. PowerMon's source code is private.

## Publishing a new version

1. In the PowerMon source repo: `dotnet publish src\PowerMon.App\PowerMon.App.csproj -c Release -r win-x64 -o dist\release -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true -p:EnableCompressionInSingleFile=true -p:DebugType=none --self-contained true`
2. `gh release create vX.Y.Z dist\release\PowerMon.exe --repo vampxlr/powermon-download --title "PowerMon X.Y.Z"`
3. Update the version, size and SHA-256 (`Get-FileHash dist\release\PowerMon.exe`) in `index.html` and push.

The download button links to `releases/latest/download/PowerMon.exe`, so it always serves the newest release.
