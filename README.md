# mkdocs-labeled-user-defined-values

This is a plugin for a MkDocs which allows pages to have user defined input values.

The difference with the original mkdocs-user-defined-values is the capability to categorize keywords.

## Setup

Install the plugin using pip:

`pip install mkdocs-labeled-user-defined-values`

Activate the plugin in `mkdocs.yml`:

```yaml
plugins:
  - search
  - labeled-user-defined-values:
      input-placeholder: "{{{user-defined-values}}}"
      keywords:
        cat1:
          YOUR_AWS_REGION:
            placeholder: e.g. ap-southeast-2
          YOUR_AWS_ACCOUNT_ID:
            placeholder: e.g. 12355224536
        cat2:
          ANOTHER_KEYWORD:
            label: any label that I want to display
            placeholder: e.g. any placeholder that I want to display
```

> **Note:** If you have no `plugins` entry in your config file yet, you'll likely also want to add the `search` plugin. MkDocs enables it by default if there is no `plugins` entry set, but now you have to enable it explicitly.

More information about plugins in the [MkDocs documentation][mkdocs-plugins].

## Config

- `keywords` - This is a list of keywords which you want to allow a user to modify.
- `input-placeholder` - This is a placeholder where you want the plugin to generate the form for user to provide dynamic values for each keyword. Default value is `{{{user-defined-values}}}`.
Please note that appart from `keywords` and *category names* (`cat1` and `cat2` in the above example), most of the parameters are optional.

## Usage

- Provide a list of `keywords` you want a user to provide dynamically.
- Place `{{{user-defined-values}}}` in your page or template where you want to generate the form for user to provide dynamic values.
- You can replace *category names* by any name you desire.

## See Also

More information about templates [here][mkdocs-template].

More information about blocks [here][mkdocs-block].

[mkdocs-plugins]: http://www.mkdocs.org/user-guide/plugins/
[mkdocs-template]: https://www.mkdocs.org/user-guide/custom-themes/#template-variables
[mkdocs-block]: https://www.mkdocs.org/user-guide/styling-your-docs/#overriding-template-blocks
