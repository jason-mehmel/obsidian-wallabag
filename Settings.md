There are various settings under the plugin settings you can use to personalize your workflow, here are some important ones organised by section.

## Required settings

| Setting                                                | Description                                                                                                                                                     | Default                                                                |
| :----------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------- |
| Server URL                                             | The full URL to your server. For most this is https://app.wallabag.it | `https://app.wallabag.it`|
| Tag to sync                                            | Use this for syncing only the articles tagged with tag. If empty plugin will sync all the articles.                                                             | Blank, ignore tags as a sync filter.                                   |
| Wallabag article notes folder location                  | Select the folder you want synced notes will be created. notes will be created at the vault root.                                                               | Blank, save notes in root of your vault.                               |
| Article note template file                                  | Use to pass a custom template for notes. See the [Templating](#templating) for more details.                                                                    |                                                                        |

## Sync behaviour
| Setting                                                | Description                                                                                                                                                     | Default                                                                |
| :----------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------- |
| Sync on startup                                        | If enabled, articles will be synced on startup.                                                                                                                 | Disabled. Manually sync.                                               |
| Sync unread articles                                   | If enabled, unread articles will be synced.                                                                                                                     | True, all unread articles will be synced.                              |
| Wallabag unread article notes folder location          | Choose the location different from the `Article Notes Folder` where the unread synced article notes will be created.                                            | Blank, save in the `Article Notes Folder`.                             |
| Sync archived articles                                 | If enabled, archived articles will be synced.                                                                                                                   | False, no archived articles will be synced.                            |
| Wallabag archived article notes folder location        | Choose the location different from the `Article Notes Folder` where the archived synced article notes will be created.                                          | Blank, save in the `Article                                            |


## Obsidian note creation

| Setting                                                | Description                                                                                                                                                     | Default                                                                |
| :----------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------- |
| Convert HTML Content extracted by Wallabag to Markdown | If enabled the content of the Wallabag article will be converted to markdown before being used for the new article.                                             | Disabled.                                                              |
| Archive article after sync                             | If enabled the article will be archived after being synced.                                                                                                     | False. Articles are not moved to Wallabag's archive folder after sync. |
| Add article ID in the title                            | If enabled the article ID will be added to title.                                                                                                               | False.                                                                 |
| Tag format                                             | Determines how the tags will be populated in the created not. List(`each tag on a separate line as tag properties`)(default), CSV(`tag1, tag2`) or hashtags(`#tag1`)                                                            |  List                                                                      |
| Link Published By                                      | Determines if author names will be bracketed by `[[ ]]` and become Properties that will link to a note.                                                         | True                                                                   |
| Wallabag ID Property                                   | Allow you to specify the name of the Obsidian property where you are storing the article ID (See id in [Templating](#templating)).                              | wallabag_id                                                            |
| Wallabag URL Property                                  | Allow you to specify the name of the Obsidian property where you are storing a link to the Wallabag article (See `wallabag_link` in [Templating](#templating)). | wallabag_url  |
| Single annotation marker | Freeform text added after every single annotation. Use # to add an inline Obsidian tag. Space separate multiple tags. For example, `#tag1 #tag2` | |
| All annotations marker |   Text included after all annotations if one or more annotations is present. Use # to add inline Obsidian tag. Space separate multiple tags.| |


## Export as PDF
| Setting                                                | Description                                                                                                                                                     | Default                                                                |
| :----------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------- |
| Export as PDF                                          | If enabled synced articles will be exported as PDFs.                                                                                                            | Disabled.                                                              |
| PDF Folder  | Location where PDF files will be created | |
| Create note | Create an Obsidian note as well as a PDF | True |