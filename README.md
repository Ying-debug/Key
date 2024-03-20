# Improving the Spatial Resolution of Solar Images Using Super-resolution Diffusion GANs

## Training Super-resolution Diffusion GANs ##
We use the following commands to train Super-resolution Diffusion GANs on the solar image dataset.

```
python3 train_ddgan.py --image_size 256 --exp ddgan_vgg_ T4 --num_channels 3 --num_channels_dae 64 --ch_mult 1 1 2 2 4 4 --num_timesteps 4 --num_res_blocks 2 --batch_size 4 --num_epoch 500 --ngf 64 --embedding_type positional --use_ema --ema_decay 0.999 --r1_gamma 1. --lr_d 1e-5 --lr_g 1.6e-5 --lazy_reg 10 --num_process_per_node 1 --save_content
```
```
python3 train_ddgan.py --dataset cifar10 --exp ddgan_cifar10_exp1 --num_channels 3 --num_channels_dae 128 --num_timesteps 4 \
--num_res_blocks 2 --batch_size 64 --num_epoch 1800 --ngf 64 --nz 100 --z_emb_dim 256 --n_mlp 4 --embedding_type positional \
--use_ema --ema_decay 0.9999 --r1_gamma 0.02 --lr_d 1.25e-4 --lr_g 1.6e-4 --lazy_reg 15 --num_process_per_node 4 \
--ch_mult 1 2 2 2 --save_content
```

