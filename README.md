# 三大问题
1. gRPC是什么？
- google的一个开源的远程过程调用系统，将协议缓冲区作为接口定义语言和基础消息交换格式，实现了客户端可以在其他计算机服务端调用方法。
    - 协议缓冲区：google用于序列化结构化数据的开源机制。
2. gRPC能做什么？
- 分布式
- 微服务

3. gRPC怎么使用？
- 安装协议缓冲区编译器
    - 解压后的.exe放在gopath的bin目录中
- 安装协议编译器的go插件
    ```
    export GO111MODULE=on  # Enable module mode
    go get github.com/golang/protobuf/protoc-gen-go
    go get google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.0
    ```
- 创建.go定义proto
- proto所在目录自动生成客户端服务端代码
    ```
    protoc --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative helloworld/helloworld.proto
    ```
- 创建服务端server、客户端client
- 运行server,运行client