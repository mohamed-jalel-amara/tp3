# Install 
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
#
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2

# init a module
go mod init google.golang.org/grpc/examples/helloworld/helloworld

# install the gRPC package for Go
go get -u google.golang.org/grpc

# Generate Go code from the proto file
protoc --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go- grpc_opt=paths=source_relative proto/helloworld.proto

# Run server 
go run server/server.go

# Run client 
go run client/client.go