# SnippetSample

A sample project that provides an example of a swift package with a library and associated snippets.

## Using the sample

To generate the symbol graphs and base level archives, run the following command:

```bash
swift package generate-documentation
```

The resulting output should look roughly like the following:

```bash
Building for debugging...
[61/61] Applying snippet-extract-tool
Build of product 'snippet-extract' complete! (4.95s)
Extracting symbol information for 'SnippetSample'...
Building for debugging...
[1/1] Write swift-version--58304C5D6DBC2206.txt
Build of target: 'SnippetSample' complete! (0.13s)
Finished extracting symbol information for 'SnippetSample'. (0.23s)
Building documentation for 'SnippetSample'...
Finished building documentation for 'SnippetSample' (0.06s)
Extracting symbol information for 'FirstExample'...
Building for debugging...
[1/1] Write swift-version--58304C5D6DBC2206.txt
Build of target: 'FirstExample' complete! (0.13s)
Finished extracting symbol information for 'FirstExample'. (0.20s)
Building documentation for 'FirstExample'...
Finished building documentation for 'FirstExample' (0.03s)
Generated 2 documentation archives:
  /Users/heckj/src/SnippetSample/.build/plugins/Swift-DocC/outputs/FirstExample.doccarchive
  /Users/heckj/src/SnippetSample/.build/plugins/Swift-DocC/outputs/SnippetSample.doccarchive
```

Generate the preview:

`swift package --disable-sandbox preview-documentation --target SnippetSample`

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

After running the preview, you can find the symbol graph dumps:

- `./.build/plugins/Swift-DocC Preview/outputs/.build/symbol-graphs/snippet-symbol-graphs/SnippetSample-snippetsample/SnippetSample-snippets.symbols.json`
- `./.build/plugins/Swift-DocC Preview/outputs/.build/symbol-graphs/unified-symbol-graphs/SnippetSample-3/SnippetSample-snippets.symbols.json`
- `./.build/plugins/Swift-DocC Preview/outputs/.build/symbol-graphs/unified-symbol-graphs/SnippetSample-3/target-symbol-graphs/SnippetSample.symbols.json`

