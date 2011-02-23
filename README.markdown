# Markdownify

This module provides the [Markdownify][1] library (included) to Drupal via API
functions and URLs that convert HTTP POSTed input for users with the correct
permissions and output JSON, appropriate for AJAX callbacks. 

Markdownify is a PHP library that converts HTML to Markdown and Markdown Extra.
Markdownify is included, re-licensed for this module under the GPL (see [this 
conversation thread][2]).

# Reference

## API functions

### `markdownify_include()`

Include the markdownify_libraries.

### `markdownify_on()`

Turn on Markdownify. Set a token that can be used for access checking.

## URLs

### `/markdown2html`

The 'input' element of the POST will be converted from Markdown to HTML and
returned as the 'output' element of a JSON object.

### `/html2markdown`

The 'input' element of the POST will be converted from HTML to Markdown and
returned as the 'output' element of a JSON object.

### `/admin/markdownify/test`

Tests, including this README file.

## Hooks

This module defines these `_alter` hooks:

* `markdownify_markdown2html_preprocess`
* `markdownify_markdown2html_postprocess`
* `markdownify_html2markdown_preprocess`
* `markdownify_html2markdown_postprocess`

 [1]: http://milianw.de/projects/markdownify/
 [2]: http://drupal.org/node/299545
