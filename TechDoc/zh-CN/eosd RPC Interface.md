## eosd RPC Interface -- eosd RPC接口

Describes how to interface with eosd over HTTP RPC. More...

eosd uses a REST RPC interface where plugins can register their own endpoints with the API server. This page will explain how to use some of the APIs to get information about the blockchain and send transactions.

描述如何通过 HTTP RPC 协议使用 eosd 接口。 详情...

eosd 使用 REST RPC 接口，这样插件可以使用 API 服务器注册自己的功能。此页将描述如何使用 API 接口来取得区块链信息和发送交易。

## Chain API Configuration -- 区块 API 配置

Before you can query eosd you must first enable an API plugin. To do this add the following line to your config.ini

使用 eosd 前需要先开启 API 插件，在 config.ini 中加入如下行开启

    plugin = eos::chain_api_plugin
    

By default an HTTP server will start on 127.0.0.1:8888; however, you can also change this with the following configureation line:

默认 HTTP服务地址、端口为127.0.0.1:8888，也可以在下面的配置中更改

    http-server-endpoint = 127.0.0.1:8888
    

## get_info

The get_info RPC command can be found at:

get_info RPC 命令如下:

    curl http://127.0.0.1:8888/v1/chain/get_info
    

And it should return something like:

它将返回类似以下内容：

     {
     "head_block_num":449,
     "last_irreversible_block_num": 434,
     "head_block_id":"000001c1a0f072a5ca76831ac6c6e2988efcf162e953eb40046ec2ceca817a9f",
     "head_block_time":"2017-07-18T21:02:24",
     "head_block_producer":"initd",
     "recent_slots":"0000000000000000000000000000000000000000000000000000000000001111",
     "participation_rate":"0.06250000000000000"
     }
    
    

## get_block

Example get_block Usage

get_block 示例：

    curl http://localhost:8888/v1/chain/get_block -X POST -d '{"block_num_or_id":5}'
    curl http://localhost:8888/v1/chain/get_block -X POST -d  '{"block_num_or_id":0000000445a9f27898383fd7de32835d5d6a978cc14ce40d9f327b5329de796b}'
    

Example get_block Result

get_block 返回信息示例：

    {
     "previous": "0000000445a9f27898383fd7de32835d5d6a978cc14ce40d9f327b5329de796b",
     "timestamp": "2017-07-18T20:16:36",
     "transaction_merkle_root": "0000000000000000000000000000000000000000000000000000000000000000",
     "producer": "initf",
     "producer_changes": [ ],
     "producer_signature":  "204cb94b3186c3b4a7f88be4e9db9f8af2ffdb7ef0f27a065c8177a5fcfacf876f684e59c39fb009903c0c59220b147bb07f1144df1c65d26c57b534a76dd29073",
    "cycles": [ ],
    "id":"000000050c0175cbf218a70131ddc3c3fab8b6e954edef77e0bfe7c36b599b1d",
    "block_num":5,
    "refBlockPrefix":27728114
    }
    
    

## push_transaction

This method expects a transaction in JSON format and will attempt to apply it to the blockchain, push_transaction

此方法使用 JSON 格式接收交易并试图在区块链中提交。

Success Response On success it will return HTTP 200 and the transaction ID.

成功返回

如果成功 HTTP 返回 200 及对应的交易 ID。 

    {
    'transaction_id' : "..."
    }
    

Just because the transaction is pushed locally does not mean that the transaction has been incorporated into a block.

因为交易只在本地提交所以并不意味交易已经被打包在区块中。

Error Response

错误返回

If an error occurs it will return either HTTP 400 (Invalid arguments) or 500 (Internal Server Error)

如果有错误发生，返回 HTTP 400 (参数非法) 或 500 (服务器内部错误)

    HTTP/1.1 500 Internal Server Error
    Content-Length: 1466
    ...error message...
    

Example push_transaction Usage

push_transaction 示例

* * *

This example assumes a transfer operation. The refBlockNum and refBlockPrefix are provided as a result of /v1/chain/get_block

如下示例发起一个交易， refBlockNum 和 refBlockPrefix 的数据值由 /v1/chain/get_block 取得。

    curl http://localhost:8888/v1/chain/push_transaction -X POST -d '{"refBlockNum":"5","refBlockPrefix":"27728114","expiration":"2017-07-18T22:28:49","scope":["initb","initc"],"messages":[{"code":"currency","type":"transfer","recipients":["initb","initc"],"authorization":[{"account":"initb","permission":"active"}],"data":"c9252a0000000000050f14dc29000000d00700000000000008454f530000000000"}],"signatures":[],"authorizations":[]}'