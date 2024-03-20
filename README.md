# Improving the Spatial Resolution of Solar Images Using Super-resolution Diffusion GANs
<div align="center">
  Wei&nbsp;Song &emsp; <b>&middot;</b> &emsp;
  Ying&nbsp;Ma &emsp; <b>&middot;</b> &emsp;
  Haoying&nbsp;Sun &emsp; <b>&middot;</b> &emsp;
  Xiaobing&nbsp;Zhao &emsp; <b>&middot;</b> &emsp;
  Ganghua&nbsp;Lin
  <br> <br>
</div>

## Training Super-resolution Diffusion GANs ##
We use the following commands to train Super-resolution Diffusion GANs on the solar image dataset.
```
python3 train_ddgan.py --image_size 256 --exp ddgan_vgg_ T4 --num_channels 3 --num_channels_dae 64 \
--ch_mult 1 1 2 2 4 4 --num_timesteps 4 --num_res_blocks 2 --batch_size 4 --num_epoch 500 --ngf 64 \
--embedding_type positional --use_ema --ema_decay 0.999 --r1_gamma 1. --lr_d 1e-5 --lr_g 1.6e-5 \
--lazy_reg 10 --num_process_per_node 1 --save_content
```
## Evaluation ##
```
python3 test_ddgan_LR.py --image_size 256  --num_channels 3 --num_channels_dae 64  --ch_mult 1 1 2 2 4 4  \
--num_timesteps 4 --num_res_blocks 2  --net_type vgg_lr_T2 --batch_size 1 --epoch_id $EPOCH
```
## Acknowledgement

This project is based on [Denoising Diffusion GANs]([https://github.com/lllyasviel/ControlNet](https://github.com/NVlabs/denoising-diffusion-gan)). Thanks for their awesome work.




