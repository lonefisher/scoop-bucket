# lonefisher's Scoop Bucket

[![Tests](https://github.com/lonefisher/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/lonefisher/scoop-bucket/actions/workflows/ci.yml)
[![Excavator](https://github.com/lonefisher/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/lonefisher/scoop-bucket/actions/workflows/excavator.yml)

Personal [Scoop](https://scoop.sh) bucket for Windows applications that are not available in the buckets I use.

## Add this bucket

```powershell
scoop bucket add lonefisher https://github.com/lonefisher/scoop-bucket
```

## Available manifests

### FishGram Beta

[FishGram](https://github.com/lonefisher/fishgram) is an unofficial Telegram Desktop client for Windows 11 x64 with restricted-chat global search.

```powershell
scoop install lonefisher/fishgram-beta
```

Run `fishgram` or use the **FishGram (Beta)** shortcut. Scoop preserves accounts and settings in `FishGramData` and manages updates; the client's built-in updater is disabled. The first Beta ships before the remaining manual search and update-recovery tests; see the [Release notes](https://github.com/lonefisher/fishgram/releases) for known limitations.

### RHI

[RHI](https://github.com/RankFTW/RHI) is a ReShade HDR installer and graphics mod manager for Windows games.

```powershell
scoop install lonefisher/rhi
```

RHI requires the .NET 8 Desktop Runtime. If it is not already installed:

```powershell
scoop bucket add versions
scoop install versions/windowsdesktop-runtime-8.0
```

The RHI manifest is configured for Scoop's Inno Setup extraction and is automatically checked for upstream GitHub releases by the repository's Excavator workflow.

### Veyra (NVIDIA)

[Veyra](https://github.com/Likely7/Veyra-NRVideo) is a Windows 11 x64 video player with GPU video enhancement. This manifest installs the NVIDIA portable package (not the AMD package).

```powershell
scoop install lonefisher/veyra-nvidia
```

Scoop creates a **Veyra (NVIDIA)** Start Menu shortcut and preserves `runtime_local/user-data-2.0.0` between updates. The upstream archive includes a top-level folder, which the manifest flattens during installation. The repository's Excavator workflow checks official GitHub releases for updates.

### Jasna (NVIDIA)

[Jasna](https://github.com/Kruk2/jasna) is a GPU-accelerated video mosaic detection and restoration tool. This manifest installs the official **Windows NVIDIA** release, which is distributed as a multi-part 7z archive (approximately 6.5 GiB for v0.11.3).

```powershell
scoop install lonefisher/jasna
```

Scoop verifies each archive part using its SHA-256, extracts the first `.7z.001` volume, and creates a **Jasna** Start Menu shortcut. The `model_weights` directory is persisted between updates so locally compiled GPU engines survive. New bundled model files are merged into the persisted directory during upgrades.

Jasna requires an NVIDIA GPU and a recent driver. Its installation path must contain only English/ASCII characters and should be on a local NTFS SSD.

## Updating

Normal Scoop updates are sufficient:

```powershell
scoop update
scoop update rhi
scoop update veyra-nvidia
scoop update jasna
```
