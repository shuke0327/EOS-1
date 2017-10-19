## eosd RPC口--eosd种

介绍了如何接口与eosd通过HTTP RPC。 更多...

eosd使用余RPC界面插件可以注册他们自己的端点与API服务器。 本节会解释如何使用的一些Api获取信息有关的区块链和发送交易。

描述如何通过HTTP RPC式eosd口。 详情...

eosd。其余RPC口，这样插件可以使用API服务器注册自己的功能。此页将描述如何使用API接口来取得区块链信息和发送交易。

## 链API构--区API。

之前你可以查询eosd您必须首先使API插件。 要做到这一添加下面一行 你的配置。ini

使用eosd前需要先开启API插件，在配置。ini中加入如下行开启

    插件=eos::chain_api_plugin
    

通过默认HTTP服务器将开始在127.0.0.1:8888；但是，你也可以改变这与以下价值的线：

在HTTP服务地址、端口为127的。0.0.1:8888，也可以在下面的配置中更改

    http服务器的端点=127.0.0.1:8888
    

## "内情向量"

该"内情向量"RPC命令可以发现：

"内情向量"RPC量:

    卷毛http://127.0.0.1:8888/v1/chain/get_info
    

它应该返回的东西，如：

它将返回类似以下内容：

     {
    "head_block_num":449,
    "last_irreversible_block_num":434,
    "head_block_id":"000001c1a0f072a5ca76831ac6c6e2988efcf162e953eb40046ec2ceca817a9f",
    "head_block_time":"2017-07-18T21:02:24",
    "head_block_producer":"initd",
    "recent_slots":"0000000000000000000000000000000000000000000000000000000000001111",
    "participation_rate":"0.06250000000000000"
    }
    
    

## 将

例将使用情况

将示：

    卷毛http://localhost:8888/v1/chain/get_block -X后d'{"block_num_or_id":5}'
    卷毛http://localhost:8888/v1/chain/get_block -X后d'{"block_num_or_id":0000000445a9f27898383fd7de32835d5d6a978cc14ce40d9f327b5329de796b}'
    

例将结果

将返回信息示例：

    {
    "以前":"0000000445a9f27898383fd7de32835d5d6a978cc14ce40d9f327b5329de796b",
    "timestamp":"2017-07-18T20:16:36"中，
    "transaction_merkle_root":"0000000000000000000000000000000000000000000000000000000000000000",
    "生产":"initf",
    "producer_changes":[],
    "producer_signature":"204cb94b3186c3b4a7f88be4e9db9f8af2ffdb7ef0f27a065c8177a5fcfacf876f684e59c39fb009903c0c59220b147bb07f1144df1c65d26c57b534a76dd29073",
    "循环":[],
    "id":"000000050c0175cbf218a70131ddc3c3fab8b6e954edef77e0bfe7c36b599b1d",
    "block_num":5,
    "refBlockPrefix":27728114
    }
    
    

## push_transaction

这种方法预计的事务关系图来描述软件所需的依赖，并将试图将其应用于区块链 push_transaction

此方法使用JSON格式接收交易并试图在区块链中提交。

成功的回应 在成功，它将返回HTTP200和交易的身份证。

成功返回

进HTTP。200及对应的交易。 

    {
    '返回有关数据库级事务的信息':"..."
    }
    

仅仅因为交易是推动本地并不意味着事务已纳入一个方框。

因为交易只在本地提交所以并不意味交易已经被打包在区块中。

错误的响应

错误返回

如果发生错误，就会返回HTTP400(无效的论点)或500(内部服务器错误)

如果有错误发生的。HTTP400(参数非法)或500(服务器内部错误)

    HTTP/1.1 500内部服务器的错误
    Content-Length:1466
    ...错误的消息...
    

例push_transaction使用情况

push_transaction示

* * *

这个例子假设传输操作。 该refBlockNum和refBlockPrefix提供作为结果/v1/链/将

如下示例发起一个交易，refBlockNum和refBlockPrefix的数据值由/v1/链/将。。

    卷毛http://localhost:8888/v1/chain/push_transaction -X后d'{"refBlockNum":"5","refBlockPrefix":"27728114","expiration":"2017-07-18T22:28:49","scope":["initb","initc"],"messages":[{"code":"currency","type":"transfer","recipients":["initb","initc"],"authorization":[{"account":"initb","permission":"active"}],"data":"c9252a0000000000050f14dc29000000d00700000000000008454f530000000000"}],"signatures":[],"authorizations":[]}'