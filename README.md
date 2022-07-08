
This fails
```
GOPATH=$PWD/gopath gcloud app deploy gopath/src/example.com/embedder
```

```
ERROR: (gcloud.app.deploy) Staging command [/usr/lib/google-cloud-sdk/platform/google_appengine/go-app-stager /home/ryan/embed/gopath/src/example.com/embedder/app.yaml /home/ryan/embed/gopath/src/example.com/embedder /tmp/tmpj5304m6z/tmpsupd859i] failed with return code [1].

------------------------------------ STDOUT ------------------------------------
------------------------------------ STDERR ------------------------------------
2022/07/08 16:06:17 staging for go1.16
2022/07/08 16:06:17 GO111MODULE=auto, but no go.mod found, so building with dependencies from GOPATH
main-package: example.com/embedder
2022/07/08 16:06:17 Staging app (GOPATH mode): failed analyzing /home/ryan/embed/gopath/src/example.com/embedder: cannot find package "embed" in any of:
        ($GOROOT not set)
        /home/ryan/embed/gopath/src/embed (from $GOPATH)
GOPATH: /home/ryan/embed/gopath
--------------------------------------------------------------------------------
```

The same app works in module mode:

```
gcloud app deploy mod
```