#aux_source_directory(. SRC_LIST)
set(SRC_LIST 
    mprpcapplication.cc 
    rpcprovider.cc 
    mprpcconfig.cc
    rpcheader.pb.cc 
    mprpcchannel.cc
    mprpccontroller.cc
    logger.cc
    zookeeperutil.cc
    )
# muduo是静态库，因此这里也生成静态库
add_library(mprpc ${SRC_LIST})//使用add_library命令将源文件列表${SRC_LIST}编译为名为mprpc的静态库。
target_link_libraries(mprpc muduo_net muduo_base pthread zookeeper_mt)//将静态库mprpc与其他库进行链接。具体来说，它将mprpc库与muduo_net、muduo_base、pthread和zookeeper_mt库进行链接。
