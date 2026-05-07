You can give the plugin any of the following commands. All can be accessed via the Command Palette (CTRL-P (Windows) or Command-P (Mac)). 

## Sync Wallabag Articles

This command retrieves all new articles from Wallabag and stores them according to your [[Settings]] and [[Templating]].

A list of previously synced files is kept so that they are not synced again.

## Clear synced articles cache

This command clears the synced articles list. When [Sync Wallabag Articles](#sync-wallabag-articles) is next run it will retrieve all your Wallabag articles as if for the first time. 

Clearing the cache is useful in the early days when you are first setting up your system and trialling new template designs.

###Delete note and remove it from synced articles cache

This command deletes a single article and removes it from the synced articles cache. When [Sync Wallabag Articles](#sync-wallabag-articles) is next run, and assuming the article is still present in your Wallabag list of articles, the article will be retrieved again.

> [!WARNING] 
> `{{id}}` must be present in your template for this command to work

## Delete article from Wallabag

This command:

- Deletes the article from Wallabag
- Keeps your Obsidian Note
	- Removes any reference to ``wallabag_id`` and ``wallabag_url``[^1]

> [!WARNING] 
> `{{id}}` must be present in your template for this command to work

## Delete note and article

This command:

- Deletes the article from Wallabag
- Deletes your note from Obsidian

> [!WARNING] 
> `{{id}}` must be present in your template for this command to work