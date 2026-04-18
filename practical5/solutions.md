1. Look for *** TASK 1 *** in the code and add a single line that implements the correct forward diffusion process (50 points)
```python
xt = sqrt_alpha_bar_t*x_start + sqrt_one_minus_alpha_bar_t * noise
```

2. Look for *** TASK 2 *** in the code and add a single line that implements the correct reverse diffusion process (50 points)
```python
x0 = (xt-(torch.sqrt(1 - alpha_bar_t)*noise_pred)) / torch.sqrt(alpha_bar_t)
```


3. Look for *** TASK 3 *** in the code and experiment with the number of **reverse diffusion steps**. If you decrease that number (below now-default 1000 steps), what happens and why? If you increase that number (above now-default 1000 steps), what happens and why (and how to fix this)? (50 points)
Your answer to Task 3: We are doing reverse diffusion steps on the MNIST 0-9 numbers. When we reduce the number of denoise steps the resulting images still have tons of noise and are blurry. This is because the model has not ran through enough denoising steps in order to construct an image that is readable.This is because the modle was trained assuming 1000 denoising steps, so fewer steps means each step has to "undo" more noise thatn it was trianed to handle. Thus this explains why running the model of fewer than 1000 denoising steps results in blurry and noisy images.

Additionally, if you increase the number above 1000 steps the image becomes denoised then disappears, ultimately turning into a blank image. This again is because the model was trained to denoise for 1000 timesteps and anything beyond that is sort of undefined behavior. The undefined behavior I believe is that the model starts to treat the clean image itself as noise, hence the blank result. The fix would to either use the 1000 timesteps the model was trained on. Additionally, we could trian the model to handle a longer scheulder e.g 2000.


4. The synthesized images (taken directly from the model) are ... well, okay-ish. Some of them look quite good, and many of them are clear out-of-set samples. Provide an idea for **sampling from a generative model**. That is, what strategy would you put on top of the raw model's output to maximize the probability of generating within-set samples? (50 points)

The model can take ideas from cVAE and cGAN, and take input vector conditioning the model to a specific class or group of classes (0-9). This embedded vector in the model should be passed in every denoising step to condition the model. As described in the other conditioned models, this conditions the models to select and produce images that are in the known distribution. Hopefully, this idea is able to sample from a generative modela nd produce the correct samples rather than out-of-set samples.

Another idea is to train a separate classifer, kinda of like GANs with the generator and discriminator. The classifer at each denoising step nudges the socre function toward high-probability regions of the desired class.