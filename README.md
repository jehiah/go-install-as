### go-install-as

`go install` a package under a specific import path

### Installation

    $ make install

You will need to have `$GOPATH` set. Ideally it should start with a 'development' path, and end with the
default go path.

    export GOPATH=/usr/local/go/site-packages/go1:/usr/local/go

You will also need to setup your development "site-packages" dir

    mkdir -p /usr/local/go/site-packages/go1/src
    mkdir -p /usr/local/go/site-packages/go1/pkg
    mkdir -p /usr/local/go/site-packages/go1/bin

### Why

When building code for production you often want to finer grain control over dependencies.

This tool allows you to `go install` packages, regardless of their source (private, etc.), into whatever import path you specify.

### Example

We have a private-repository on github, say `github.com/bitly/go-simplejson` and we want the import path to be `bitly/simplejson` for our Go client applications...

    $ git clone git@github.com:bitly/go-simplejson.git
    $ cd go-simplejson
    $ go tool install_as --import-as=bitly/simplejson
