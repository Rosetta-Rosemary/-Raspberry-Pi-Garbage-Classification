'''
设计人：     刘煜泽
开始时间：   2021-01-10
项目：       基于树莓派的垃圾分类识别
'''

# 设计需求：   
    基于树莓派的垃圾分类识别，对被识别物体进行拍照，并完成相关的图像识别分类，返回出被识别物的类别以及属于哪一种垃圾

# 设计思想：   
    使用树莓派4B作为一个家庭级的物联网控制服务器，为同一局域网下的相关终端提供相关的服务支持。其中终端部署在设定为能够进行垃圾分类的垃圾筒的入口处，当有垃圾投入时，进行拍照取得垃圾的图片。服务器部分则负责在终端完成拍照之后，读取图片内容并进行图像识别，将识别结果返回给对应的终端进行垃圾处理。客户端部分负责对服务器资源的监控，以及对终端的相关操作发出指令，例如打开垃圾桶盖来方便取出垃圾袋或是更新垃圾桶标签来适配新的垃圾类别。

# 主要特点：   
    跨平台，适配树莓派下的Linux系统以及平时家用的window系统

    具备兼容性，不仅是具备垃圾分类功能的垃圾筒，还能支持家中的灯光、电源等。

    智能化终端，终端开启电源时，即自动在局域网网中寻找服务器，并完成连接等操作，免去相关复杂操作。

# 更新日志
------
## 2021-02-28
    从1月10日开始就在陆陆续续进行相关技术的验证了，但直到今天才正式写下这个readme文档，也算是从今天开始正式开工。
    之前完成了几个基础模块，大部分使用了Qt，未来也会使用Qt来完成客户端
    现在有大概框架的模块主要集中在通讯模块之间，都已经实现了一些基础功能
    之后也会根据主题框架的改变而进行优化改进。
    使用的用于图像识别分类的工具是Tensorflow2.0，window里是直接使用Anaconda进行相关配置，搭配GTX1660 6G显卡进行模型训练，数据集提取自华为云的垃圾分类大赛
    目前已经完成了一个基于VGG16模型迁移训练的7种分类的模型，准确率大概在80%-90%之间，还没出现过拟合等情况
    作为一个保底，等到所有模块都已经完成的差不多之后，也许会继续进行模型优化，对图像识别的种类进行增加。
    Qt使用的版本为Qt5.12.0，搭配使用的环境时 VS code + CMake + MinGW 进行编译，来实现跨平台的使用，但仍需要代码相关兼容性，可能在不同设备中，需要进行代码修改。


