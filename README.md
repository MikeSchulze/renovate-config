# <img src="https://github.com/MikeSchulze/gdUnit4/blob/master/icon.png" width="32" height="32"> Renovate Shared Configuration for GdUnit4

This repository contains shared Renovate configurations for our GdUnit4 projects.

## What it does

- **Automatically updates Godot Engine PrRelease versions** in CI workflows
- **Monitors Godot prerelease versions** (dev builds)
- **Creates PRs with detailed information** about the updates
- **Auto-merges after CI passes** (with 12-hour safety delay)

## 📁 Available Configurations

### `default.json`
The main configuration for GdUnit4 projects with standard CI workflows.

**Features:**
- ✅ Updates `ci-pr.yml` and `ci-pr-publish-report.yml`
- ✅ Groups Godot version and status updates
- ✅ Auto-merge with safety delays
- ✅ Detailed PR descriptions
- ✅ Proper labels and assignments

## 🚀 How to use

Add this to your repository's `.github/renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "config:recommended",
    "github>MikeSchulze/renovate-config"
  ]
}
```

## 🔧 Repository-specific customizations

You can override settings in your repository's `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "config:recommended", 
    "github>MikeSchulze/renovate-config"
  ],
  "packageRules": [
    {
      "matchPackageNames": ["godotengine/godot-builds"],
      "minimumReleaseAge": "24 hours",
      "automerge": false
    }
  ]
}
```

## 📋 What gets updated

- **Godot version numbers** in CI matrix configuration
- **Godot status** (dev1, dev2, dev3, etc.)
- **Both files**: `ci-pr.yml` and `ci-pr-publish-report.yml`

## ⚙️ Configuration details

- **Minimum release age**: 12 hours (safety buffer)
- **Auto-merge**: Enabled for passing builds
- **PR limits**: Max 3 concurrent PRs
- **Labels**: `godot-prerelease`, `ci`
- **Assignee/Reviewer**: MikeSchulze

## 🛠️ Maintenance

To update the configuration:
1. Edit `default.json` in this repository
2. All repositories using this config will automatically get the updates
3. Test changes on a single repository first

## 📚 Renovate Documentation

- [Renovate Docs](https://docs.renovatebot.com/)
- [Shareable Config Presets](https://docs.renovatebot.com/config-presets/)
- [Template Fields](https://docs.renovatebot.com/templates/)
