# Dalamud Plugins

A shared custom plugin repository for plugins created or maintained by kuchris. Subscribe to one URL and install each plugin separately.

## Install

```text
https://raw.githubusercontent.com/kuchris/DalamudPlugins/main/repo.json
```

1. Open `/xlsettings` in FFXIV.
2. Go to **Experimental** → **Custom Plugin Repositories**.
3. Add the URL above, enable it, and save.
4. Open `/xlplugins` and install the plugins you want.

If you used the earlier `xivaichat/main/repo.json` URL, replace that custom repository entry with the URL above, then refresh the installer. Keep installed plugins and their settings; no uninstall is needed.

## Plugins

| Plugin | Description | Links |
| --- | --- | --- |
| XIV AI Chat | AI reply drafts for the chat channels you choose. | [Source](https://github.com/kuchris/xivaichat) · [Releases](https://github.com/kuchris/xivaichat/releases) |
| MoreMacros | Extra macro pages with native hotbar links, auto-translate, and macro command icons. | [Source](https://github.com/kuchris/moremacros) · [Releases](https://github.com/kuchris/moremacros/releases) |
| Gillionaire | Gil trading plugin by [voidstar0](https://github.com/voidstar0/Gillionaire), with an API 15 fork maintained by kuchris. | [Fork source](https://github.com/kuchris/Gillionaire) · [Fork releases](https://github.com/kuchris/Gillionaire/releases) |
| OCBFR | Occult Crescent automation, currency purchases and loot tracking, with Traditional Chinese / English UI. | [Source](https://github.com/kuchris/OCBFR) · [Setup](#ocbfr) · [Download](https://github.com/kuchris/OCBFR/releases/latest) · [Ko-fi](https://ko-fi.com/kuchris) |

This repository contains the plugin catalogue and OCBFR's installer icon. Plugin source and installation ZIPs are hosted in their respective repositories, including [kuchris/OCBFR](https://github.com/kuchris/OCBFR). Each plugin keeps its own version and configuration.

## OCBFR

OCBFR automates Occult Crescent coffer scanning, treasure routes, currency purchases and re-entry, with a searchable loot history and a **Traditional Chinese / English** interface.

Install **OCBFR** using the catalogue URL above. Requires **Daily Routines**, **vnavmesh** and **BOCCHI**; keep Daily Routines in **Simplified Chinese** for the treasure route names.

[English setup](https://github.com/kuchris/OCBFR/blob/main/docs/INSTALL.en.md) · [繁體中文安裝](https://github.com/kuchris/OCBFR/blob/main/docs/INSTALL.zh-TW.md) · [Validation status](https://github.com/kuchris/OCBFR/blob/main/docs/TEST-STATUS.md) · [Download](https://github.com/kuchris/OCBFR/releases/latest) · [Ko-fi](https://ko-fi.com/kuchris)

## Publish an update

Catalogue updates are currently manual:

1. Build and test the plugin in its source repository.
2. Commit and push its source to its designated repository, then publish its versioned installation ZIP as a GitHub Release asset in that repository. For OCBFR, maintain both source and releases in `kuchris/OCBFR`.
3. Pull the latest `main` of this repository.
4. In `repo.json`, update the object with the matching `InternalName`. Copy the package's version and Dalamud API level, refresh `LastUpdate` (Unix seconds), and set all download links to the published versioned ZIP. Keep other plugin entries intact.
5. Validate the JSON and public download URL, then commit and push.

To add another plugin, append an object with a unique `InternalName` and its own manifest fields and release links. Players keep the same subscription URL.

The earlier catalogue in `kuchris/xivaichat` remains available for existing subscribers, but this repository is the primary catalogue. The XivAiChat release workflow updates that older file only; it does not automatically update this repository. After publishing any plugin, update this catalogue explicitly.
