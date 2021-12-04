[![Build Status](https://github.com/minhjh/go-service-qingstor/workflows/Unit%20Test/badge.svg?branch=master)](https://github.com/minhjh/go-service-qingstor/actions?query=workflow%3A%22Unit+Test%22)
[![Integration Tests](https://teamcity.minhjh.io/app/rest/builds/buildType:(id:GoServiceQingstor_IntegrationTests)/statusIcon)](https://teamcity.minhjh.io/buildConfiguration/GoServiceQingstor_IntegrationTests)
[![License](https://img.shields.io/badge/license-apache%20v2-blue.svg)](https://github.com/Xuanwo/storage/blob/master/LICENSE)
[![](https://img.shields.io/matrix/minhjh@go-storage:matrix.org.svg?logo=matrix)](https://matrix.to/#/#minhjh@go-storage:matrix.org)

# go-services-qingstor

[QingStor Object Storage](https://www.qingcloud.com/products/objectstorage/) service support for [go-storage](https://github.com/minhjh/go-storage).

## Install

```go
go get github.com/minhjh/go-service-qingstor/v3
```

## Usage

```go
import (
	"log"

	_ "github.com/minhjh/go-service-qingstor/v3"
	"github.com/minhjh/go-storage/v4/services"
)

func main() {
	store, err := services.NewStoragerFromString("qingstor://bucket_name/path/to/workdir?credential=hmac:access_key_id:secret_access_key&endpoint=https:qingstor.com")
	if err != nil {
		log.Fatal(err)
	}
	
	// Write data from io.Reader into hello.txt
	n, err := store.Write("hello.txt", r, length)
}
```

- See more examples in [go-storage-example](https://github.com/minhjh/go-storage-example).
- Read [more docs](https://minhjh.io/docs/go-storage/services/qingstor) about go-service-qingstor.
