# gdocs-twine
[Twine](https://twinery.org) is a tool for telling hypertext stories. It's got a cool interface that lets you do things like visualize your story's structure, but it doesn't allow for collaborative editing. Gdocs-twine fills that gap by allowing you to build a Twine story as a Google Doc. 

Gdocs-twine uses as simple syntax for the story's structure: most of the complexity is handled by Twine's story format. Note that it ignores all styles applied in Google Docs. You'll have to style using the Twine story format. A file consists of two parts: the front matter, and a list of passages. The front matter is a series of lines in the form `key: value`. You'll want to set the story's `name` and `format`. After the front matter come the story's passages. Each passage starts with a line in the form `== passage-name`. If you need to start a line in the story with `==`, you can set `passage_separator` to something else in the front matter. That's it!

Here's [an example](https://docs.google.com/document/d/1qehNM140m47Mykxpcj9JO9tE_ghJDUacv4B6fhs_jmY/pub) of the source format, and [what it looks like rendered](https://danielsmc.github.io/gdocs-twine/?doc=https%3A%2F%2Fdocs.google.com%2Fdocument%2Fd%2F1qehNM140m47Mykxpcj9JO9tE_ghJDUacv4B6fhs_jmY%2Fpub).

Right now, two story formats are supported: `Harlow` and `Sugarcube2`. Eventually you might be able to use any format by passing a URL, but since story formats are arbitary javascript, it's a sandboxing nightmare.

## TODO
* Import/Export Tools
* Better documentation
* Support for story scripts and styles