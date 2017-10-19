> [EOS发展偷窥对于非常早期开发人员](https://steemit.com/eosdev/@dan/eos-development-sneak-peek-for-very-early-developers)

# EOS发展偷窥对于非常早期开发人员--EOS开发早鸟指南

虽然官方的试验网络仍然在制，任何人都可以创造自己的测试环境中在地方节点。 请理解的事情可能会变化；但是，不大幅度如此。

虽然官方测试网络仍在准备中，但任何人都可以在本地节点上创建自己的测试环境。请了解这些内容很可能会发生改动，但不会很大。

我们已经开始把在一起的文件开发商。 这个文件往往滞后的发展和目前远远低于标准是什么，我们计划提供与官方的试验网络。

<https://eosio.github.io/eos/>

我们已经开始为开发人员做了汇总的文档。但该文档经常会落后于开发进度，目前水准也远低于计划和官方测试网络一并提供的文档的水准。

<https://eosio.github.io/eos/>

## 启动本地节点--启动一个本地节点

任何人都可以启动一个本地节点由以下构建指令：

[如何建立EOS。IO(eosd)](https://eosio.github.io/eos/group__howtobuild.html)

任何人都可以通过以下的生成指令来启动一个本地节点：

[如何生成EOS。IO(eosd) ](https://github.com/BlockChainTranslator/EOS/blob/master/TechDoc/How%20To%20Build%20EOS.md)

## 与地方节点的通过RPC--通过RPC与本地节点交互

该`eosd`可执行的可能配置，以获得休息/JSON口超过HTTP。 现有的APIs是相当有限，但将大大扩展的时间。 关于如何接口，与此RPC直接请参阅本文件：

[eosd RPC口](https://eosio.github.io/eos/group__eosiorpc.html)

可以将可执行文件`eosd`配置为通过HTTP来暴露其余/JSON口。以API还非常有限，但随着时间的推移会急剧扩展。有关如何直接与此RPC接口进行交互的信息，请参阅以下文档：

[eosd RPC口](https://github.com/BlockChainTranslator/EOS/blob/master/TechDoc/eosd%20RPC%20Interface.md)

## 与地方节点的通过CLI(eosc)--通过CLI（eosc）与本地节点交互

`eosc`是一种工具，包RPC接口，并使其便于用户查询`eosd`的。 这个工具将最终成为主要的交互方式与`eosd`开发人员希望发布合同的区块链的。

`eosc`是包装了RPC接口的一个工具，以方便用户来查询`eosd`。对于希望将合约发布到区块链的开发人员，这个工具将成为与`eosd`进行交互的主要方式。

对于一个快速的教程，如何创建的帐户，转移资金，以上的合同，并与这些合同通过`eosc`和`eosd`请查看这个：

[eosc-命令行客户](https://eosio.github.io/eos/group__eosc.html)

关于如何创建帐户，转移资产，上传合约以及通过`eosc`和`eosd`与这些合约进行交互的快速教程，请参阅：

[eosc-命令行客户端](https://github.com/BlockchainTranslator/EOS/blob/master/TechDoc/EOS%20Command%20Line%20Client.md)

## 目前的发展状况--开发现状

作为目前的情况区块链是这样做没有签名的认证。 这意味着任何帐户，可以触发的任何行动。 这使得事情很容易测试的逻辑应用程序。 它也意味着它目前不必要的，以维持一个钱包的私钥的使用网络来测试你的应用。

按现状来看，区块链是在没有签名验证的情况下运行的。这意味着任何帐户都可以触发任何操作。这可以很容易地测试应用程序的逻辑。这同时也意味着目前无需维护一个带有私钥的钱包来使用网络对应用程序进行测试。

在接下来的几个星期，我们将建立一个CLI的钱包和使开发者把签证和许可的检查。

在接下来的几个星期内，我们将构建一个CLI在，使开发人员能够启用签名验证和权限检查。

还注意到，目前RPC API使得非常难以查询的合同。 这将予以纠正。

另请注意，当前的RPC API使您很难查询合约的状态。这将在下周得到改进。

## 开始与发展--开发入门

我们有几个[example contracts](https://github.com/EOSIO/eos/tree/master/contracts)，你可以用它作为一个起点：

我们提供了几个[合约示例](https://github.com/EOSIO/eos/tree/master/contracts)，可以作为开发的起点：

有关的信息提供Api请见：

[如何写入合同](https://eosio.github.io/eos/group__contractdev.html)

关于可用API的信息，请参阅：

[如何编写合约](https://github.com/BlockChainTranslator/EOS/blob/master/TechDoc/How%20To%20Write%20Contracts.md) 

还有一个有用的指数[all documentation](https://eosio.github.io/eos/modules.html)的。

这还有一个链接了[所有文档](https://eosio.github.io/eos/modules.html)的索引，非常有用。

## 开发人员通道--开发者频道

我们还创建了一个新的开发人员通道上的电报(tg://加入吗？邀请=EaEnSUPktgfoI-XPfMYtcQ). 这道严重缓和保持的主题集中在开发人员帮助开发人员。 如果你有疑问这是最好的地方获得实时支持社区。 我们的开发人员也将监测这聊天和试图帮助随着时间的许可证。

我们还在报上创建了一个新的开发者频道报(tg://加入吗？邀请=EaEnSUPktgfoI-XPfMYtcQ)。这个频道做了比较严格的限制，以保持主题聚焦在开发人员的互助上。如果您有疑问，这是获得社区实时支持的最佳途径。我们的开发人员也会监控该频道上的讨论，并会在时间允许的情况下提供协助。

我们还想建立[#eosdev](https://steemit.com/trending/eosdev)标记在这里steemit的。 如果你有开发人员的问题和/或回答请后根据这一标签。 我将试图按照它，并把它变成我们自己堆交换。 质量问题、答案和教程将获得最多选票。

我们也在steemit上建立了[#eosdev](https://steemit.com/trending/eosdev)标。如果您有开发者的问题和（或）我们的孩子来说，他们都渴望的请在该标签下发布。我会试着跟进它，并将它变成我们自己的栈交换。高质量的问题、答案及教程将会获得投票。

## 这仅仅是个开始--这仅仅是个开始

这种信息提供的信息，目的仅仅基于社区的需求。 我们将感谢任何的反馈，你可以得到，因为它将帮助我们完善我们如何发展EOS。IO服务的需求，开发。 所有文件和设计仍然受到改变，但是与你的反馈，他们可以变得更好！

这些信息是依据社区需求而提供的，以。我们将非常感谢您的任何反馈意见，因为这将有助于我们改进EOS。IO一种，以满足开发者们的需求。所有的文档和设计仍然会有变化，但随着您的反馈，它们可以变地更好！