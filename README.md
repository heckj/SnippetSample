# SnippetSample

A sample project that provides an example of a swift package with a library and associated snippets.

The library has only the empty, default swift file generated, [SnippetSample.swift](Sources/SnippetSample/SnippetSample.swift) - so there's no symbols the Swift compiler will generate, but there **is** an explicit module name for this package: `SnippetSample`.

The (single) associated snippet file [FirstExample.swift](Snippets/FirstExample.swift), is a "hello world" print statement. You can run and validate the snippet using the command:

- `swift run FirstExample`

The output it generates is something akin to:

```bash
Building for debugging...
[1/1] Write swift-version--58304C5D6DBC2206.txt
Build of product 'FirstExample' complete! (0.24s)
hello world
```

## Using the sample

To see the documentation (and investigate the symbolgraphs generated), I use the preview-documentation command from the [swift-docc-plugin](https://github.com/swiftlang/swift-docc-plugin):

- `swift package --disable-sandbox preview-documentation --target SnippetSample`

output:

```bash
Building for debugging...
[1/1] Write swift-version--58304C5D6DBC2206.txt
Build of product 'snippet-extract' complete! (0.44s)
Building for debugging...
[1/1] Write swift-version--58304C5D6DBC2206.txt
Build of target: 'SnippetSample' complete! (0.22s)
Template: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/share/docc/render
========================================
Starting Local Preview Server
	 Address: http://localhost:8080/documentation/snippetsample
========================================
```

After running the preview, you can find the symbol graphs generated in the process of seeing the preview:

- `./.build/plugins/Swift-DocC Preview/outputs/.build/symbol-graphs/unified-symbol-graphs/SnippetSample-3/SnippetSample-snippets.symbols.json`
- `./.build/plugins/Swift-DocC Preview/outputs/.build/symbol-graphs/unified-symbol-graphs/SnippetSample-3/target-symbol-graphs/SnippetSample.symbols.json`

I prettified the JSON and copied the two into the root directory:

- [SnippetSample-snippet.symbols.json](./SnippetSample-snippet.symbols.json)
- [SnippetSample.symbols.json](./SnippetSample.symbols.json)
