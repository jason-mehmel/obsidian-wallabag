Templating defines how the Wallabag article displays as an Obsidian note. 

By default this plugin offers two builtin templates; one for inserting the content of the article as a note and one for creating a note with a link to the exported PDF, when the option is enabled. Both the templates include link to the original articles, a link to the Wallabag item and tags. 

## Default note template

```
---
wallabag_id: {{id}}
tags: {{tags}}
---
## {{article_title}} [original]({{original_link}}), [wallabag]({{wallabag_link}})
{{content}}
```

This template displays any tags you have configured in the setup, the article title as a level 2 heading, with links to both the original article and Wallabag copy, followed by the content of the article itself.

## Default PDF template

```
---
wallabag_id: {{id}}
tags: {{tags}}
---
## {{article_title}} [original]({{original_link}}), [wallabag]({{wallabag_link}})
PDF: [[{{pdf_link}}]]
```

The default PDF template is almost identical to the [Default note template](#default-note-template) except it has a link to the downloaded PDF instead of embedding the article content in the note.

## Custom templates

You can use a custom template for greater control over your Obsidian note layout. Each of the variables listed below can occur anywhere in your template file, even more than once. The template is nothing more than a dedicated Markdown note in your Obsidian vault. For it to be used, you will need to set `Article Note Template` (see [[Settings]]).

You can use a custom template, in that case plugin will pass the following variables. Within your template, surround each variable with `{{` and `}}`, eg. `{{id}}` or `{{content}}`.

| Variable            | Description                                                                                                        |
| :------------------ | :----------------------------------------------------------------------------------------------------------------- |
| `id`                | Wallabag ID of the article (see [ID Is a Special Variable](#id-is-a-special-variable) below)                                                    |
| `article_title`     | Title of the article                                                                                               |
| `authors`           | Display publishers/authors on a single line.                                                                       |
| `authors_list`      | Display publishers/authors as a list. Both options are the same.                                                   |
| `content`           | HTML content extracted by wallabag                                                                                 |
| `created_at`        | Creation date of the article in Wallabag                                                                           |
| `domain_name`       | Link to the source domain article                                                                                  |
| `given_url`         | Given link to the source page                                                                                      |
| `is_archived`       | Whether the article is archived or not                                                                             |
| `is_starred`        | Whether the article is starred or not                                                                              |
| `original_link`     | Link to the source article                                                                                         |
| `pdf_link`          | An Obsidian wikilink to the exported pdf file. <sub><br> Only populated if the PDF export option is choosen.</sub> |
| `preview_picture`   | link to preview picture of the article                                                                             |
| `published_at`      | When the article was originally published according to Wallabag                                                    |
| `published_by`      | Alternative to `authors`. Same result.                                                                             |
| `published_by_list` | Alternative to `authors_list`. Same result.                                                                        |
| `reading_time`      | Reading time of the article                                                                                        |
| `tags`              | Tags attached to the Wallabag article, format depends on the setting                                               |
| `updated_at`        | Last modification date of the article in Wallabag RemoveCurrentFromSyncedArticlesCacheCommand                      |
| `wallabag_link`     | Link to the article in Wallabag                                                                                    |

### ID is a special variable

If you want to make use of any of the additional plugin [[Commands]], you **must** have `{{id}}` in your template as an Obsidian property. The ID makes the connection between the Wallabag article and your Obsidian note.

Once synced, `https://app.wallabag.it/view/27659680` is linked to an Obsidian note with the same value.

```
---
wallabag_id: 27659680
---
```

> [!TIP] You're not stuck with `wallabag_id`
> The  `Wallabag ID Property` allows you to store your ID in a field called something different than `wallabag_id`. It allows you to have a property name consistent with your own naming conventions.

### Article title and punctuation

Property values with `'`, `:` or `?` will confuse Obsidian's parsing of the YAML at the top of a note. Since titles often contain these characters you can avoid problems by wrapping your `article_title` with quotes.

```
---
title: "{{article_title}}"
---
```

### Extra tags
When using the `List` format for tags, if you want add additional tags beyond what's in Wallabag, set your template up like this.

```
---
tags: {{tags}}
  - extra_tag1
  - extra_tag2
---
```

### Annotating PDFs

You can use the `pdf_link` tag with this plugin to export articles as pdfs and use [Annotator](https://github.com/elias-sundqvist/obsidian-annotator) to read using the following template.

```
---
annotation-target: {{pdf_link}}
---
```

### Difference between *authors* and *authors_list*

`authors` will display all authors on a single line and `authors_list` displays them as a list. The list format is more suitable for links from the Properties panel when paired with the `Link Published By` setting.

If your template is:

```
---
author: {{authors}}
---
```

your note will show:

```
---
author: Stephen King, Brandon Sanderson
---
```

Compare this to the list version and note how the template field is on the next line.

```
---
author:
{{authors_list}}
---
```

which generates

```
---
author:
  - Stephen King
  - Brandon Sanderson
---
```

The list format is best paired with `Link Published By` **enabled** to provide you with clickable links in the Properties tab.

```
---
author:
  - "[[Stephen King]]"
  - "[[Brandon Sanderson]]"
---
```

## Sample custom template

This is my template.

```
---
tags:
  - class/source
datetime: {{published_at}}
updated: 
title: "{{article_title}}"
author:
{{published_by_list}} 
year: 
recommender: 
url: {{given_url}}
wallabag_id: {{id}}
wallabag-link: {{wallabag_link}}
---

## Annotations

{{annotations}}

## Content

{{content}}
```
