# madmin-go — libreFS Admin Go SDK

Go client library for administering [libreFS](https://github.com/libreFS/libreFS) servers. Forked from `minio/madmin-go`.

This document assumes that you have a working [Golang setup](https://golang.org/doc/install).

## Initialize Admin Client

```go

package main

import (
    "fmt"

    "github.com/minio/madmin-go/v4"
)

func main() {
    // Use a secure connection.
    ssl := true

    // Initialize admin client object.
    mdmClnt, err := madmin.New("your-librefs.example.com:9000", "YOUR-ACCESSKEYID", "YOUR-SECRETKEY", ssl)
    if err != nil {
        fmt.Println(err)
        return
    }

    // Fetch service status.
	info, err := mdmClnt.ClusterInfo(context.Background())
    if err != nil {
        fmt.Println(err)
        return
    }
	fmt.Printf("%#v\n", info)
}
```

## Documentation

All documentation is available on [pkg.go.dev](https://pkg.go.dev/github.com/minio/madmin-go/v4).

## License

Licensed under the GNU AGPLv3 — see the [LICENSE](LICENSE) file.
