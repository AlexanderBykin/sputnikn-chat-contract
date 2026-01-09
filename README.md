# sputnikn-chat-contract
SputnikN chat network contract


Must install
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest

GO-gRPC
https://github.com/grpc/grpc-go/blob/master/examples/gotutorial.md

Protobuf Golang
https://protobuf.dev/getting-started/gotutorial/

Protobuf Dart
https://protobuf.dev/getting-started/darttutorial/
https://pub.dev/packages/protoc_plugin

protoc -I=$(pwd) --go_out="$(pwd)/go_build" $(pwd)/contract.proto

protoc --go_out="$(pwd)/go_build" --go_opt=paths=source_relative \
    --go-grpc_out="$(pwd)/go_build" --go-grpc_opt=paths=source_relative \
    $(pwd)/contract.proto


===
go get -u google.golang.org/protobuf/cmd/protoc-gen-go
go install google.golang.org/protobuf/cmd/protoc-gen-go

go get -u google.golang.org/grpc/cmd/protoc-gen-go-grpc
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc

# generate the Go messages
 protoc -I="$(pwd)" --go_out="$(pwd)/go_build" "$(pwd)/contract.proto"

# generate the Go services
 protoc -I="$(pwd)" --go-grpc_out="$(pwd)/go_build" "$(pwd)/contract.proto"

# generate the Dart messages
 protoc -I=$(pwd) --dart_out="$(pwd)/dart_build" "$(pwd)/contract.proto"

# generate the Dart services
 protoc -I=$(pwd) --dart_out="grpc:$(pwd)/dart_build" "$(pwd)/contract.proto"
