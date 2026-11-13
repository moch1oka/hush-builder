# Configuration Guide

Configure apps to patch in `config.toml`.

## Quick Example

```toml
[TikTok-Hush]
app-name = "TikTok"
patches-source = "SysAdminDoc/hushfeed"
cli-source = "MorpheApp/morphe-cli"
rv-brand = "Hush"
build-mode = "apk"
arch = "arm64-v8a"
pkg-name = "com.zhiliaoapp.musically"
apkpure-dlurl = "true"
included-patches = "'AMOLED dark theme'"
```

> [!WARNING]
> When a patch name itself contains a single quote, double it inside the string (e.g. `'Hide ''Get Music Premium'''`).

## Options Reference

```toml
# Global options
enable-module-update = false         # Disable module updates when building APKs only
parallel-jobs = 1                   # Amount of concurrent patch jobs (default: 1)
compression-level = 9               # Module zip compression level
remove-rv-integrations-checks = false # Remove integrations checks if needed
dpi = "nodpi anydpi 120-640dpi"     # DPI packages to search in order
arch = "arm64-v8a"                  # Default architecture: arm64-v8a, arm-v7a, all
build-mode = "apk"                  # 'apk', 'module', or 'both'

patches-source = "MorpheApp/morphe-patches" # Default patches source repository
cli-source = "MorpheApp/morphe-cli"         # Default CLI source repository
rv-brand = "Hush"                           # Default brand name
patches-version = "latest"                  # 'latest', 'dev', or a specific tag
cli-version = "latest"                      # 'latest', 'dev', or a specific tag

[Some-App]
app-name = "SomeApp"                # Custom display name for the app
enabled = true                      # Whether to build this app (default: true)
build-mode = "apk"                  # 'apk', 'module', or 'both'
arch = "arm64-v8a"                  # Target CPU architecture
pkg-name = "com.example.app"        # Android package name
version = "auto"                    # 'auto' selects highest supported version by patches
version-code = "123456789"          # Pin specific versionCode for APKPure CDN download (e.g. Facebook)

apkpure-dlurl = "true"              # Enable downloading base APK via APKPure / apkeep
apkmirror-dlurl = "https://..."     # Fallback APKMirror URL if needed
direct-dlurl = "https://..."        # Direct APK download link

included-patches = "'Some Patch'"   # Space-separated list of additional patches to enable
excluded-patches = "'Other Patch'"  # Space-separated list of patches to disable
patcher-args = "-Ooption=value"     # Additional arguments passed to the CLI patcher
```
