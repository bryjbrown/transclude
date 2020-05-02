# Transclude Token
Transclude Token is a Drupal module that defines a token that can be used to [transclude](https://en.wikipedia.org/wiki/Transclusion) external content into a node. This can be very handy for when you want to reuse language from an outside source (or even an internal one) without having to copy and paste, which can be a pain if the outside source changes. transclude allows you to reference an @id tag in an external web page and load it dynamically, so that when the outside source changes, the reference in your page changes too.

## Usage
You can transclude content into a Drupal node by using the transclude token, `[transclude:'https://url.to/transclude#anchor']` (be sure to quote the URL). Drupal will recognize this token, load the specified page, extract the section with the specified anchor, and output it into the node wrapped in a `<blockquote class="transclude">` tag.

Please note that in order for tokens to be recognized and expanded within nodes, the token_filter module must be enabled along with token replacement in any text format that it may be used with. See [http://www.ryanwright.me/cookbook/drupal7/contrib-modules/token-filter](http://www.ryanwright.me/cookbook/drupal7/contrib-modules/token-filter) for more information on how to configure token replacement in nodes.

## Prepping external content for transclusion
If you are in control of the external content to be transcluded, the easiest way to make it transclusion-friendly is to wrap the content you want to transclude in a `<div id="name">` tag. The transclusion token will then grab all of the content inside that `<div>`. Note that the transcluded content does not have to be inside any particular element, but `<div>` and `<span>` are the most semantically valid choices.
