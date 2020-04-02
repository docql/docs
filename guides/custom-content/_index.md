+++
title = "Custom Content"
weight = 0
+++

Custom Content
==============
DocQL offers a feature for integrating custom user content into API Hubs.

This is a work in progress.

### supported section config
The following details the available section configuration options along with their default values.

```toml
# The HTML title to be used for the section.
title = ""

# Used by the parent section to order its subsections. Lower values have higher priority.
# This is primarily seen in the site's navigation.
weight = 0

# This determines whether to insert a link for each header like the ones you can
# see on this site if you hover over a header.
#
# This value can be "left", "right" or "none".
insert_anchor_links = "left"

# If set to "true", the section pages will be in the search index.
in_search_index = true

# If set to "true", the section homepage is rendered.
# Useful when the section is used to organize pages (not used directly).
render = true

# This determines whether to redirect when a user lands on the section.
# Similar to `render`, except this causes redirects instead of a 404.
# Example: redirect_to = "guides/custom-content/overview"
redirect_to = ""

# If set to `true`, the section will pass its pages on to the parent section.
# Useful when the section shouldn't split up the parent section.
transparent = false

# Use aliases if you are moving content but want to redirect previous URLs to the
# current one. This takes an array of paths, not URLs.
aliases = []
```

Variables which can not be configured and which are controlled by DocQL:
- `description`: doesn't serve any purpose in the DocQL use case.
- `sort_by`: always set to `"weight"`, so that the weight variables is used for sorting pages of the section.
- `template`: this is determined by the DocQL theme being used.
- `page_template`: this is determined by the DocQL theme being used.
- `paginate_by`: pagination is not supported.
- `paginate_path`: pagination is not supported.

