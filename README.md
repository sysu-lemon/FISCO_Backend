# FISCO_Backend + FISCO_Chainend

## Build & Run FISCO_Chained

### 搭建单群组FISCO BCOS联盟链的并启动

[FISCO-BCOS/FISCO-BCOS](https://github.com/FISCO-BCOS/FISCO-BCOS)

### 控制台下载，主要使用其中的solidity转java功能

[FISCO-BCOS/console](https://github.com/FISCO-BCOS/console)

## Build & Run FISCO_Backend

### 把联盟链证书`<chainend>/nodes/127.0.0.1/sdk/*`放置在`<backend>/src/main/resources/`

### 编译项目
```
$ ./gradlew build
```

### 启动项目
```
$ ./gradlew bootRun
```

## Setting

### `<backend>/src/main/resources/application.yml`

如果需要重新部署合约
- 删除文件下 "contract.addr" 字段
- `./gradlew bootRun`
- `curl localhost:8000/api/v1/admin -XPOST`
- 把输出的 "contractAddr" 和 "auth" 记录下来，分别为合约地址和管理员私钥
- 把 "contractAddr" 记录到`<backend>/src/main/resources/application.yml`文件中
