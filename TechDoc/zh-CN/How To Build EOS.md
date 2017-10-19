## 如何建立EOS。IO--如何构建EOS。IO

介绍了如何以下载、编辑并配置一个EOS。IO节点。

以下说明，概述过程中获得的软件、建立和运行一个简单的试验网络，产生块。

描述了如何下载，编译，并且配置一个EOS。IO的节点。

以下的操作说明概况了如何获得，构建和运行一个能产生区块的简单测试网络的整个过程。

## 设立一个建设/发展的环境--搭建一个用于构建/开发的环境

这个项目是编写主要是用C++14和使用CMake作为其建立的系统。 一个最新C++的工具(例如铛或海湾合作委员会)和最新版本的CMake建议。 在编写本文时，内森使用铛4.0.0和CMake3.8.0的。

这个项目主要是用C++14编并且使用了CMake作为它的构建系统。推荐使用最新的C++工具链（以铛以海湾合作委员会）和最新版本的CMake。在撰写本文档时，内森使用的是铛4.0.0和CMake3.8.0。

## 安装的依赖关系--安装依赖包

驻外办事处具有以下外部的依赖，必须安装在你的系统：

EOS有如下的外部依赖包必须在你的系统上安装：

- 提升1.64
- OpenSSL
- 编程4.0
- [secp256k1-zkp(Cryptonomex分)](https://github.com/cryptonomex/secp256k1-zkp)

    git克隆https://github.com/cryptonomex/secp256k1-zkp.git
    cd secp256k1-zkp
    ./autogen.sh
    ./配置
    让
    sudo make install
    

## 如何建立编程和铛为WASM--如何为WASM并编程和铛

默认情况下编程和铛不包括WASM建立的目标，所以你必须建立它自己。 注意到以下这些指令将建立一个版本的编程只能建立WASM目标。

编程和铛默认是不包括WASM的构建目标的，所以你必须要自己构建。注意以下的操作指令将会创建一个只用来构建WASM的一个LLVM的版本。

    mkdir~/wasm编译器
    cd~/wasm编译器
    git克隆--深入1--单一的分支--支release_40https://github.com/llvm-mirror/llvm.git
    cd编程/工具
    git克隆--深入1--单一的分支--支release_40https://github.com/llvm-mirror/clang.git
    cd..
    mkdir建立
    cd建立
    cmake-G"Unix生成文件"-DCMAKE_INSTALL_PREFIX=.. -DLLVM_TARGETS_TO_BUILD=-DLLVM_EXPERIMENTAL_TARGETS_TO_BUILD=WebAssembly-DCMAKE_BUILD_TYPE=释../
    让-j4安装
    

得到代码--获取代码

下载的所有代码，下载Eos和递归或两个子模块。 最简单的方式得到所有这一切都是做递归的克隆：

为了下载所有的代码，可以递归下载EOS或者下载EOS和两个子模块。下载所有代码最简单的方法是使用一个递归克隆：

    git克隆https://github.com/eosio/eos --recursive
    

如果一个仓库克隆没有--递归的标志，子可以检索的事实后，通过运行这个命令从在repo:

如果在克隆版本库的时候并没有使用--recursive这个命令行参数，那么在下载完成以后可以通过在版本库中运行这个命令来获取子模块：

    git子模块的更新--init--recursive
    

## 配置和建筑--配置和构建

来做一个来源建立，根本的运行cmake的。 从顶级目录。 开源基础也支持。 复盖铛的默认选择在编译器，加入这些标志的CMake命令：

如果要做源码内构建的话，只需要在顶层文件夹运行"cmake的。" EOS也支持源码外构建。为了覆盖在编译器里的铛的默认选择，把这些命令行参数加到Cmake的命令中去：

    -DCMAKE_CXX_COMPILER=/path/to/c++DCMAKE_C_COMPILER=/path/to/cc
    

对于一个调试建立、加DCMAKE_BUILD_TYPE="调试"。 其他共同建立的类型包括释放和RelWithDebInfo的。

如果是调试类型构建的话，加入命令行参数-DCMAKE_BUILD_TYPE="调试"。其他常用的构建类型是释放和RelWithDebInfo。

在成功运行cmake，简单地行使建立的一切。 运行测试后的建设、运行chain_test可执行的试验的文件夹。

cmake成功运行之后，只需要运行作。构建所有的代码。构建以后如果需要运行测试集，就运行测试文件夹中的chain_test等。

## 使用WASM编译器，来执行一个充分建立的项目--使用WASM编译器来对整个项目进行完全构建

该WASM_LLVM_CONFIG环境变量是用来寻找我们最近建立WASM编译器。 这需要编制的例子合同insde eos/合同文件夹和他们各自测试。

与WASM_LLVM_CONFIG这个环境变量来发现我们最近构建的WASM编译器。被eos/合同文件夹里的合约用例和他们各自的测试用例时需要用到这个WASM编译器。

    git克隆https://github.com/eosio/eos --recursive
    mkdir-p eos/建立&&cd eos/建造
    出口WASM_LLVM_CONFIG=~/wasm编译/编程/bin/编程config 
    cmake..
    让-j4
    

如果你正在做的积极发展EOS。IO软件可能需要添加WASM_LLVM_CONFIG到你。bash_profile

如果你需要经常在EOS。IO软件上进行开发的话，你可能会想要把WASM_LLVM_CONFIG加到你的的。bash_profile文件中去。

创建和推出一个单一的节点testnet--创立和启动单节点的测试网络

在成功建设项目，eosd二进制应该存在的程序/eosd目录。 继续运行eosd–它可能会退出一个错误，但如果没有，立即关闭它与Ctrl-C。 注意eosd将创建一个目录，名为数据-dir包含缺省配置(配置。ini)和其他一些内部。 这个默认数据的存放路径可以通过--的数据-dir/path/to/数据eosd的。

在成功构建项目之后，eosd的二进制代码就应该出现在程序/eosd文件夹中。现在可以运行eosd-它可能会由于一个错误而退出，但是如果没有的话，马上用Ctrl-C来关闭它。以eosd会创建一个叫做数据-dir作，里面有默认配置（config。ini)和一些其他的内部文件。可以通过加一个命令行参数--数据-dir/path/to/data。eosd来覆盖掉这个默认的数据存储文件夹。

编辑的配置。ini文件，添加以下设置的违约已经到位：

编辑配置。ini文件，把以下设置加到已经存在的默认设置中：

    #载testnet创世纪的状态下，这就造成了一些初步框生产者与默认的关键
    genesis-json=/path/to/eos/来源/成因。json
    #使生产上的一个陈旧的，链，因为一个节点试验链是几乎总是陈旧的
    enable-陈旧的生产=true
    #使块生产与生产者testnet
    生产国-name=inita
    生产国-name=initb
    生产国-name=initc
    生产国-name=initd
    生产国-name=inite
    生产国-name=initf
    生产国-name=initg
    生产国-name=inith
    生产国-name=因素有关
    生产国-name=initj
    生产国-name=initk
    生产国-name=initl
    生产国-name=initm
    生产国-name=initn
    生产国-name=inito
    生产国-name=initp
    生产国-name=initq
    生产国-name=initr
    生产国-name=inits
    生产国-name=initt
    生产国-name=initu
    #载块生产的插件，所以我们可以生产块
    插件=eos::producer_plugin
    

现在应该能够运行eosd，并看到它开始生产模块。 目前，P2P码不是实现的，所以只有个节的结构是可能的。 当P2P网络实现的，这些指示将进行更新，以显示如何创建一个例子多节点testnet的。

现在是应该可以运行eosd并且可以看到它开始产生区块。目P2P的代码还未实现，所以只可能有一个单节点的配置。在P2P代码实现以后，将会更新这些操作说明来表明如何创建一个多节点测试网络的用例。