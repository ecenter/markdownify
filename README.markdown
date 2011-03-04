# Markdownify

*Developed and maintained by David Eads (davideads@gmail.com) for Fermi National
Accelerator Laboratory and the U.S. Department of Energy as part of the 
[E-Center Project][1].*

This module provides the [Markdownify][1] library (included) to Drupal via API
functions and URLs that convert HTTP POSTed input for users with the correct
permissions and output JSON, appropriate for AJAX callbacks. 

Markdownify is a PHP library that converts HTML to Markdown and Markdown Extra.
Markdownify is included with this package.

# Reference

## Permissions

Users **must** have the `markdownify access` permission to convert text, and
may only access conversion when `markdownify_on()` is invoked (see below). 

Users with the `convert any text (dangerous)` permission may POST arbitrary
input to the Markdown converters. Grant with care! This permission could easily
allow remote users to use your site to return arbitrary, potentially unsafe
data payloads.

## API functions

### `markdownify_include()`

Include the Markdownify libraries. Call if you need access to the Markdownify
and Markdownify_Extra APIs.

### `markdownify_on()`

Turn on Markdownify. Sets a token that is used for access checking in the
callback functions. Call when using Markdownify on a content editing form.

## AJAX callback URLs

### `/markdown2html`

The 'input' element of the POST will be converted from Markdown to HTML and
returned as the 'output' element of a JSON object.

### `/html2markdown`

The 'input' element of the POST will be converted from HTML to Markdown and
returned as the 'output' element of a JSON object.

### `/admin/markdownify/test`

Tests, including this README file.

## Hooks

This module defines these `_alter` hooks which take an input string as their
parameter:

* `markdownify_markdown2html_preprocess_alter`
* `markdownify_markdown2html_postprocess_alter`
* `markdownify_html2markdown_preprocess_alter`
* `markdownify_html2markdown_postprocess_alter`

Use the alter hooks to manipulate data as it is processed by Markdownify. For
example, use `mymodule_markdownify_html2markdown_postprocess_alter` to remove 
extraneous tags added by TinyMCE when converting TinyMCE source to Markdown.

 [1]: https://cdcvs.fnal.gov/redmine/projects/ecenter/
 [2]: http://milianw.de/projects/markdownify/
