In the context of a command line interpreter, clobbering means overwriting the contents of a file using shell redirection (using the > and >> operators). This is sometimes useful, sometimes catastrophic.

By default, the clobbering is enabled in both zsh and bash, or the be technically correct, the noclobber option is disabled (enabling the noclobber option prevents overwriting of files by redirection). To check this option (works in zsh and bash):
```
$ set -o | grep noclobber
```
If the output is:
```
noclobber       off
```

then the option is disabled and you can overwrite a file by redirection.

[Reference](https://www.victordodon.com/to-clobber-or-to-noclobber/)
