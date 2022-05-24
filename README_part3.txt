此README文件对应本次报告中基于ILVR的换脸方式所使用的代码，包括在ILVR模型基础上主要的修改部分以及代码的使用方式。
=======================主要修改部分==========================
1.scripts/ilvr_sample.py中添加了中心对齐操作，从80行开始。
=======================使用方式=============================
1.使用命令行：
python scripts/ilvr_sample.py  --attention_resolutions 16 --class_cond False --diffusion_steps 1000 --dropout 0.0 --image_size 256
 --learn_sigma True --noise_schedule linear --num_channels 128 --num_head_channels 64 --num_res_blocks 1 --resblock_updown True 
--use_fp16 False --use_scale_shift_norm True --model_path models/ffhq_10m.pt --base_samples ref_imgs/test --down_N 8 --range_t 0 --save_dir (your directory)
以完成训练，需要注意的是test/source_inst,test/target_inst文件夹中的inst需要用语义分割模型单独生成，和之前的操作方式相同。这里的inst和前两个任务描述的inst
是一个东西。
需要预训练模型ffhq_10m.pt,可以在ILVR项目中进行下载。
不可以修改down_N！否则会严重影响效果。
2.查看结果：
在自定义的save_dir中查看训练结果，save_dir中会直接保存换脸后的图片。
=======================语义分割模型使用方法=====================
1.源代码仓库下载：https://github.com/zllrunning/face-parsing.PyTorch
2.预训练模型下载：https://jbox.sjtu.edu.cn/l/91LFbn ；放在 ./res/cp 中
3.路径更改：test.py 中 dspth=[dir_of_testset]
4.conda环境下运行 python test.py，10张img约用时4.44秒
5.生成后的label图片在 ./res/test_res 中