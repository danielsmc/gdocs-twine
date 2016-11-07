# gdocs-twine
[Twine](https://twinery.org) is a tool for telling hypertext stories. It's got a cool interface that lets you do things like visualize your story's structure, but it doesn't allow for collaborative editing. Gdocs-twine fills that gap by allowing you to build a Twine story as a Google Doc, or as a text file anywhere on the web. 

Gdocs-twine uses as simple syntax for the story's structure: most of the complexity is handled by Twine's story format. Note that it ignores all styles applied in Google Docs. You'll have to style using the Twine story format. You may find it helpful to turn off Google Docs' automatic formatting under `Tools>Preferences`. A file consists of two parts: the front matter, and a list of passages. The front matter is a series of lines in the form `key: value`. You'll want to set the story's `name` and `format`. The `format` can either be `Harlowe`, Twine 2's default format, or the url of a web-accessible `format.js` file.

After the front matter come the story's passages. Each passage starts with a line in the form `== passage-name`. If you need to start a line in the story with `==`, you can set `passage_separator` to something else in the front matter. Scripts and styles can be included as passages with the magic names `twine-user-stylesheet` and `twine-user-script`.

To use gdocs-twine with your story, get the URL from `Publish to the Web...` under the File menu and go to [https://danielsmc.github.io/gdocs-twine/](https://danielsmc.github.io/gdocs-twine/). Paste the URL into the box, and click `Render`.

Here's [an example](https://docs.google.com/document/d/1qehNM140m47Mykxpcj9JO9tE_ghJDUacv4B6fhs_jmY/pub) of the source format, and [what it looks like rendered](https://danielsmc.github.io/gdocs-twine/?doc=https%3A%2F%2Fdocs.google.com%2Fdocument%2Fd%2F1qehNM140m47Mykxpcj9JO9tE_ghJDUacv4B6fhs_jmY%2Fpub).

## Issues/Areas for Improvement
* Google Docs' Publish to Web functionality doesn't update immediately when the document is edited. This lag can be frustrating when you're trying to write and test, but I don't think it's possible to avoid without delving deeper into the Google Docs API.
* Because presenting a story means running untrusted javascript, everything is sandboxed. This breaks some features that themes offer, like saved games.
* It would be good to have an import tool to convert Twine XML into our text format. The main stumbling block is that the Twine format stores every passage's location for the graph view. Our text format doesn't have any way to represent these locations, so that data would be lost. We could extend our format to (optionally) store locations, but the Twine ecosystem already has enough jury-rigged markup formats.
* In related news, when we export to XML we lay out the passages very naively. It might be possible to be a little smarter, but we'd need to do things like actually parse each passage's links ourselves.
