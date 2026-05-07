To get started with this plugin you will need to:

1. Install the plugin
2. Authenticate to your Wallabag server
3. Make some decisions about how you want to control the sync of articles

## Pre-requisites
This plugin assumes you are running [Obsidian](https://obsidian.md) and have an active [Wallabag](https://wallabag.it) account.

## 1. Add the plugin to your Obsidian vault
### Within Obsidian

~~Search for `Wallabag` in the list of Community Plugins and install as you would any of the [Community plugins](https://help.obsidian.md/community-plugins).~~

Awaiting community plugin approval.

### Manually

- You need Obsidian v1.0.0+ for latest version of plugin.
- Get the [Latest release of the plugin](https://github.com/quantumgardener/obsidian-wallabag/releases/latest).
- Create a directory for the plugin under you plugins folder, e.g. `[VAULT]/.obsidian/plugins/obsidian-wallabag`.
- Put the release files under that folder.
- Close and reopen Obsidian.
- Make sure Safe Mode is off and the plugins is enabled.

After installing and enabling the plugin first you need to authenticate yourself with your [Wallabag](https://wallabag.it) instance. Authentication requires:

- `Client ID`
- `Client secret`
- `Your login username`
- `Your password`

The `Client ID` and `Client secret` come from your server account. Wallabag's [iOS Setup guide](https://doc.wallabag.org/en/apps/ios.html) will show you how. The process are the same for iOS or the desktop.

## 2. Setup and use

This plugin fulfills a quite straightforward purpose; it syncs Wallabag articles and creates notes from them in various possible formats.

Use the command "Sync Wallabag Articles" to sync new articles (ribbon icon, Ctrl-P (Windows) or Command-P (Mac)). This is the command that you will use most of the time. When you run it, the plugin:

- Connects to your Wallabag server
- Downloads all new articles and formats them using your template

The plugin keeps track of items synced so if you delete a created note, it won't be generated again unless you use the command "Clear synced articles cache" to reset the plugin cache. There is also a "Delete note and remove it from synced articles cache" command to remove an individual note from both the file system and synced article cache. This is useful to fetch any changes you made to the note in Wallabag (such as tags and annotations). More information can be found in [[Settings]].
