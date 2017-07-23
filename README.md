# Well Traveled Hugo Theme

Well Traveled is a minimal theme for Hugo---the static website generator. Originally built for use at http://travel.paluchowski.com/, my travel blog.

Its focus is mainly on:

* excellent readability on any device,
* support for high quality photos,
* content organization by subsequent travels I've undertaken.

## Installation

Clone the repository to your `/themes` directory, ie.

```shell
$ cd /your/hugo/site
$ git clone https://github.com/mpaluchowski/hugo-well-traveled themes/well-traveled
```

Build the [SASS](http://sass-lang.com/) files from `/assets/css` into `/static/css`:

```shell
$ sass -E UTF-8 --sourcemap=none --style compressed --watch assets:static
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
# Copyright statement used in the footer
copyright: 'Made around the world by <a href="https://michal.paluchowski.com/">Michał Paluchowski</a>. All content is under a <a href="http://creativecommons.org/licenses/by/4.0/" rel="license">Creative Commons Attribution 4.0 International License</a>.'
params:
  # Description used in the main page's META tag
  description: 'Stories from extended travels, endeavored by Milena & Michał Paluchowski. Highly opinionated. Mildly biased. A mixture of intersecting thoughts from our hearts and minds.'
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
image: img/bali-2016/bottom-line-on-bali/tegalalang-rice-terrace-statue-header.jpg
---
```
