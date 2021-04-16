# NVIDIA TRT 2021 Hackathon Competion

## 开发环境
拉取docker镜像
```bash
docker pull dudubiududubiu/mmdetection:latest
```
## TODO
- [X] 准备MMDetection3D环境     
    镜像已上传，使用脚本待准备，XX
- [ ] 准备TensorRT环境     
    镜像未上传，XX
- [ ] MMDetection3D导出PointPillars ONNX模型            
    云端服务器已经配置好docker镜像，该镜像可以运行训练mmdetection3d检测框架，在该镜像内导出pointpillars/lyft/secfpn版本的[预训练网络](https://github.com/open-mmlab/mmdetection3d/blob/master/configs/pointpillars/README.md) - ZSS
- [ ] TensorRT通过ONNX Parser解析导出的模型，并转换为TensorRT model          
    在tensorrt环境中搭建pointpillars网络，能够完整运行网络，XX
- [ ] 通过API和Plugin实现ONNX无法导出的层          
    关注scatter层和最后head层，XX
- [ ] 处理waymo数据，用来测试网络inference性能           
- [ ] 使用INT8量化，加速网络         
    准备int8加速的相关内容，网络实现后采用该方法实现加速 - WY
- [ ] 对比两种不同实现模式的推理性能，libtorch+TensorRT和纯TensorRT实现
- [ ] 对比两种不同网络构建模式的推理性能，ONNX和纯API实现
- [ ] 对比不同量化等级的推理性能，以及对精度的损失，FP32，FP16以及INT8
- [ ] 如果INT8量化精度损失比较严重，找到最佳的INT8量化组合方案，例如Backbone采用INT8，但是Neck和Head部分采用FP16

### Ref
 1. [PointPillars](https://arxiv.org/abs/1812.05784)
 2. [Nutonomy_pointpillars](https://github.com/SmallMunich/nutonomy_pointpillars)
 3. [MMDetection3D](https://github.com/open-mmlab/mmdetection3d)
 4. [TensorRT Tutorial](https://zhuanlan.zhihu.com/p/297002406)
 5. [Pytorch转ONNX教程](https://zhuanlan.zhihu.com/p/272767300)
 6. [nn_tools](https://github.com/hahnyuan/nn_tools) converter from pytorch to caffe
 7. [apolloauto](https://github.com/ApolloAuto/apollo/tree/master/modules/perception)