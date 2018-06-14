# XCode

```
xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance #569
```

[xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance · Issue #569 · nodejs/node-gyp](https://github.com/nodejs/node-gyp/issues/569)

It worked for me.

```bash
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```