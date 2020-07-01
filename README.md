# docs
The DocQL public documentation repository.

This repository will form the basis of the `Guides` section of [https://docs.docql.io](https://docs.docql.io), DocQL's API Hub.

### overview
This repository serves as the source of DocQL's public documentation and as a live example of the DocQL custom content feature in action. Though this repository is public, repositories used for DocQL's custom content feature are not required to be public.

### guides
Check out the [Guides](./guides/README.md) section of this repo for guides on specific features of the DocQL platform.

### custom content config file
A single `docql.yaml` config file is used to drive the custom content feature in DocQL. This file is expected to be at the root of its repository and defines all customizations which are to be made to the associated DocQL API Hub (from within the https://app.docql.io web application), including custom user guides, theme overrides, style changes, splash page overrides and much more.

The format is as follows:

```yaml
---
# The version of the configuration spec being used (only 1.0 is currently available).
version: 1.0

#
# The configuration file is divided into a few sections.
#

# Configuration options pertinent to custom content.
customContent:
  # Metadata for the API Hub.
  meta:
    # The title of the API Hub site. This directly corresponds to the
    # HTML `title` in the `head` section of the site.
    siteTitle: string | null
    # The brand name to be used in the API Hub; depending on the theme,
    # this will typically appear in the site's title bar.
    brandName: string | null
    # The path to the brand logo image to be used in the API Hub; depending on the theme,
    # this will typically appear in the site's title bar.
    brandLogo: string | null
    # The copyright entity name to be used in the API Hub's footer; this will appear as
    # `© YYYY {copyright} All rights reserved.`, where `YYYY` is the current year.
    copyright: string | null
    # The path to the image to be used as the API Hub's favicon.
    favicon: string | null

  # The `theme` section is dedicated to configuring the theme to be used by the associated API Hub.
  theme:
    # The name of the theme to use for the API Hub.
    #
    # This value will ALWAYS take precedence over any configuration defined in app.docql.io
    # in order to ensure consistent behavior for builds.
    name: string
    # Theme customization options.
    #
    # Every theme has different customization options, and declares those options in its description
    # and also on the docql.io/themes page for each respective theme. As such, customization options
    # should be passed in as key/value pairs under this key.
    customizations: {}

  # The `guide` section is dedicated to how you configure the guides section of your API Hub.
  # This feature is available to all API Hub tiers.
  guide:
    # An alternative name to give to the guides section. Defaults to "Guides".
    name: "Guides"
    # A path to the directory which contains all content to be used in the gudes section.
    dir: string

  # The `schema` section is dedicated to configuring the schema section of the associated API Hub.
  schema:
    # The path to the markdown file to use as the landing page for the schema section; replacing
    # the theme's default.
    landing: string | null
    # The path to the markdown file to use as the landing page for the schema's objects section;
    # replacing the theme's default.
    objects: string | null
    # The path to the markdown file to use as the landing page for the schema's enums section;
    # replacing the theme's default.
    enums: string | null
    # The path to the markdown file to use as the landing page for the schema's input objects
    # section; replacing the theme's default.
    inputs: string | null
    # The path to the markdown file to use as the landing page for the schema's scalars section;
    # replacing the theme's default.
    scalars: string | null
    # The path to the markdown file to use as the landing page for the schema's directives
    # section; replacing the theme's default.
    directives: string | null

#
# Configuration options below are universal, and apply to custom content and custom sites.
#

# Markdown parser configuration, which is applied to the target GraphQL API's schema
# docs & the markdown used in this custom content repo.
schemaMarkdownParser:
  # Soft line breaks in the input translate into hard line breaks in the output.
  hardbreaks: bool | false
  # Punctuation (quotes, full-stops and hyphens) are converted into 'smart' punctuation.
  smart: bool | false
  # GitHub-style `<pre lang="xyz">` is used for fenced code blocks with info tags.
  githubPreLang: bool | true
  # The default info string for fenced code blocks.
  defaultInfoString: string | null
  # Allow rendering of raw HTML and potentially dangerous links.
  unsafe: bool | false
  # Enables the strikethrough extension from the GFM spec.
  extStrikethrough: bool | true
  # Enables the tagfilter extension from the GFM spec.
  extTagfilter: bool | false
  # Enables the table extension from the GFM spec.
  extTable: bool | false
  # Enables the autolink extension from the GFM spec.
  extAutolink: bool | false
  # Enables the task list items extension from the GFM spec.
  extTasklist: bool | false
```
