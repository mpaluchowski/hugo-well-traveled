# Well Traveled Hugo Theme

Well Traveled is a minimal theme for Hugo—the static website generator. Originally built for use at https://travel.paluchowski.com/, my travel blog.

Its focus is mainly on:

* excellent readability on any device,
* support for high quality photos,
* content organization by subsequent travels I've undertaken.

- [Well Traveled Hugo Theme](#well-traveled-hugo-theme)
  - [Installation](#installation)
  - [Configuration](#configuration)
    - [Site Configuration](#site-configuration)
    - [Content Front Matter](#content-front-matter)
    - [Main Menu](#main-menu)
  - [Content Organization](#content-organization)
    - [Stories](#stories)
    - [Singles](#singles)
    - [Others](#others)
  - [Development](#development)

## Installation

Clone the repository to your `/themes` directory, ie.

```shell
$ cd /your/hugo/site
$ git clone https://github.com/mpaluchowski/hugo-well-traveled themes/well-traveled
```

Build the [SASS](https://sass-lang.com/) files from `/assets/css` into `/static/css`:

```shell
$ sass --no-source-map --style=compressed --update assets:assets
```

Then tell Hugo to render your site with the theme:

```shell
$ hugo --theme=well-traveled
```

## Configuration

### Site Configuration

The theme will use the following site parameters:

```yaml
# Base URL of the site
baseurl: https://travel.paluchowski.com/
# Title of the site
title: Well Traveled
# Language code for the site
languageCode: "en-us"
# Google Analytics ID
googleAnalytics: UA-2971180-12
# Name of the main author
author: "Michał Paluchowski"
# Copyright statement used in the footer
copyright: 'Made around the world by <a href="https://michal.paluchowski.com/">Michał Paluchowski</a>. All content is under a <a href="https://creativecommons.org/licenses/by/4.0/" rel="license">Creative Commons Attribution 4.0 International License</a>.'
params:
  # Relative path to the logo image
  logo: img/compass-rose.svg
  favicon:
    # Path to the favicon image  
    image: favicon.png
    # Mime type of the favicon image
    type: image/png
  # Description used in the main page's META tag
  description: 'Stories from extended travels, endeavored by Milena & Michał Paluchowski. Highly opinionated. Mildly biased. A mixture of intersecting thoughts from our hearts and minds.'
  # Content for the 404 error page
  error404:
    # Title for the page
    title: Lost a page?
    # Text for the page
    text: We couldn't find anything under the address you requested. You may want to start from the <a href="/">homepage</a> or go back and try another link.
```

### Content Front Matter

Content articles may use the following properties:

```yaml
---
# Main date related to the article
date: 2016-10-30T17:54:23+01:00
# Timezone in which the article was written, optional
timezone: CET
# Title of the article
title: The bottom line on Bali
# Tags describing themes covered by the article
tags:
  - Bali
# Main header image of the article; should be 16:9 and best size is 1920x1080px
image: img/bali-2016/bottom-line-on-bali/tegalalang-rice-terrace-statue-header.webp
---
```

### Main Menu

The `main` menu is a short list of links placed in the page's footer. By default it always includes:

* the home page
* the list page of the story section, when a story article is open

To add more pages to the menu, [mark them up in the front matter](https://gohugo.io/content-management/menus/#define-in-front-matter), referencing the `main` menu.

## Content Organization

The content for the blog is organized into three groups:

1. Stories—multi-article series, covering a longer trip,
2. Singles—one-off articles,
3. Others—pages that may cover info about authors, contacts, or similar.

### Stories

Stories rely on Hugo's sections, grouping articles in a subdirectory of `/content`:

```
/content
    /india-2017
        /first-article/index.md
        /second-article/index.md
        ...
```

These will appear on the home page as large blocks with the story's title, last three articles and a link to the page with all the story's content.

### Singles

Singles are meant for short write-ups, ie. from a day-trip that's not part of a bigger series. They should reside directly in the `/content` directory:

```
/content
    /first-single-article/index.md
    /second-single-article/index.md
```

The last three singles will appear at the top of the home page, with a link to browse further.

### Others

Others are meant for pages that don't describe any particular travel, but instead, usually, contain information about the website itself. These can be placed anywhere inside `/content`, but in order for them *not* to appear in any article list, their front matter should exclude them from lists:

```yaml
build:
    list: never
```

They can, instead, be added to the [main menu](#main-menu).

## Development

Run SASS to watch for updates and re-compile automatically:

```shell
$ sass -w .
```
