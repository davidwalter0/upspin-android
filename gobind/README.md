To build `gobind.aar`, follow these steps:

1.  Make sure go is installed, that `$GOPATH` is set to something and that
    `$GOPATH/bin` is in your `$PATH`:

```bash
test -z "$GOPATH" && export GOPATH="$HOME/go"
export PATH="$GOPATH/bin:$PATH"
```

2.  Download the Android SDK and NDK and extra them somewhere. Set
    `$ANDROID_HOME` and `$NDK_PATH` to their locations, respectively:

```bash
export ANDROID_HOME="$HOME/android/sdk"
export NDK_PATH="$HOME/android/ndk"
```

3.  Install `gomobile` and set it up:

```bash
go get -v golang.org/x/mobile/cmd/...
gomobile init -ndk "$NDK_PATH"
```

4.  Install the gobind package:

```bash
go get -v exp.upspin.io/client/gobind
```

5.  Generate `gobind.aar` and copy it to this folder:

```bash
go generate exp.upspin.io/client/gobind
cp "$GOPATH/src/exp.upspin.io/client/gobind/gobind.aar" ./
```
