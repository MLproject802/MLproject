此README文件对应本次报告中仅使用importance loss增强纯生成模型所使用的代码，包括在pix2pix-HD模型基础上主要的修改部分以及代码的使用方式。
=======================主要修改部分==========================
1.models/pix2pixHD_model.py中添加了importance loss，从281行开始，具体函数参考代码。
=======================使用方式=============================
1.使用命令行：
CUDA_VISIBLE_DEVICES=(index of device) python train.py --name (your training name) --label_nc 19 --loadSize (your input size) --dataroot ./datasets/faceOrigin/ --label_feat
以完成训练，需要注意的是数据文件夹中的label和inst需要用语义分割模型单独生成，这一部分在之后会介绍。label和inst使用一个灰度图。
2.查看结果：
在checkpoints中查看训练结果，这一部分由于和换脸无关，我们没有写测试的脚本，查看训练生成的图片即可。
=======================语义分割模型使用方法=====================
1.源代码仓库下载：https://github.com/zllrunning/face-parsing.PyTorch
2.预训练模型下载：https://jbox.sjtu.edu.cn/l/91LFbn ；放在 ./res/cp 中
3.路径更改：test.py 中 dspth=[dir_of_testset]
4.conda环境下运行 python test.py，10张img约用时4.44秒
5.生成后的label图片在 ./res/test_res 中