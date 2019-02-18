# docs
The DocQL public documentation repository.

### overview
This repository is used as the basis of the `Guides` section of [https://docs.docql.io](https://docs.docql.io). It is publicly available on the API Hub site, as well as here in this repo. This repo is public so that it can serve as an example of how to use the DocQL custom guides features, but custom guide repositories are not required to be public in order to work with DocQL.

### .docql.yaml
The `.docql.yaml` file is the configuration file describing how the repository is to be used when generating the custom user guides section of an API Hub.

The format is as follows:

```yaml
---
# An alternative name to give to the guides section. Defaults to "Guides".
guideName: string

# A list of sections which you want to include in your custom guides.
#
# Sections are rendered in the order which they are listed.
sections:
  # The path to the markdown document for this section, relative to this repo's root.
  #
  # Absolute paths, or paths which point outside of this repo's root will cause validation failure.
  - path: string
    # The optional name to use for this section in the table of contents.
    #
    # If not provided, the documents main header will be used. If the document has no main
    # header, then the file name will be formatted and used.
    tocName: string
```
