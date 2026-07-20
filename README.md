# Tiny-WiFo
H. Zhang, S. Gao, X. Cheng, “Tiny-WiFo: A Lightweight Wireless Foundation Model for Channel Prediction via Multi-Component Adaptive Knowledge Distillation. ” IEEE Wireless Communications Letters,  vol. 15, pp. 1846-1850, 2026. 
<br>


## Dependencies and Installation
- Python 3.9 (Recommend to use [Anaconda](https://www.anaconda.com/))
- Pytorch 2.0.0
- NVIDIA GPU + CUDA
- Python packages: `pip install -r requirements.txt`


## Dataset Preparation
The dataset used for inference is available in [[Testing Dataset]](https://huggingface.co/datasets/liuboxun/WiFo-dataset).


## Get Started
We have released the weights of Tiny-WiFo (distilled from WiFo-Base) model. Tiny-WiFo obtains key knowledge from WiFo-Base through the Multi-Component Adaptive Knowledge Distillation (MCAKD) framework.

### Inference command for multi-dataset unified learning
```
python main.py --device_id 1 --size Distil --mask_strategy_random none --mask_strategy temporal --dataset D1*D2*D3*D4*D5*D6*D7*D8*D9*D10*D11*D12*D13*D14*D15*D16 --file_load_path ./weights/Tiny_WiFo --few_ratio 0.0 --t_patch_size 4 --patch_size 4 --batch_size 128 --pos_emb SinCos_3D
```
```
python main.py --device_id 1 --size Distil --mask_strategy_random none --mask_strategy fre --dataset D1*D2*D3*D4*D5*D6*D7*D8*D9*D10*D11*D12*D13*D14*D15*D16 --file_load_path ./weights/Tiny_WiFo --few_ratio 0.0 --t_patch_size 4 --patch_size 4 --batch_size 128 --pos_emb SinCos_3D
```
### Inference command for zero-shot generalization
```
python main.py --device_id 1 --size Distil --mask_strategy_random none --mask_strategy temporal --dataset D17 --file_load_path ./weights/Tiny_WiFo --few_ratio 0.0 --t_patch_size 4 --patch_size 4 --batch_size 128 --pos_emb SinCos_3D
```
## Citation
If you find this repo helpful, please cite our paper.
```latex
@article{zhang2026tinywifo,
  author  = {Zhang, Haotian and Gao, Shijian and Cheng, Xiang},
  title   = {{Tiny-WiFo: A Lightweight Wireless Foundation Model for Channel Prediction via Multi-Component Adaptive Knowledge Distillation}},
  journal = {IEEE Wirless Commun. Lett.},
  volume  = {15},
  pages   = {1846-1850},
  year    = {2026},
  doi     = {10.1109/LWC.2026.3664439}
}
```
