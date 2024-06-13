Tags: #generator #text2image

---

# Text-to-image Generator Framework
- __Description:__ Note for 【生成式AI】Stable Diffusion、DALL-E、Imagen 背後共同的套路
- __Author:__ Kuan-Hsien Wu
- __Contact:__ jordankhwu@gmail.com
- __Date:__ 2024/02/25
- __Sources__:
    - [【生成式AI】Stable Diffusion、DALL-E、Imagen 背後共同的套路](https://www.youtube.com/watch?v=JbfcAaBT66U)

## 0. Framework
1. Text Encoder
    - Encode input text to intermediate products for generation
2. Generation Model
    - Generate image intermediate product from random-sampled image and text intermediate products
3. Decoder
    - Decode generated intermediate products to real-world images

## 1. Text encoder
- Encode input text to intermediate products for generation
- Model valuation
    - Frechet Inception Distance (FID)
        1. Use pre-trained image classification model to generate representation
        2. Find the distance between two latent representation groups (assuming Gaussian distribution)
            1. Real images
            2. Generated images
        3. The smaller the better
        4. Cons: Requires enormous samples
    - Contrastive Language-Image Pre-Training score (CLIP score)
        1. Put text and image into respective encoder
        2. Find the distance of two vectors
        3. If input text and image are in pair: the smaller the better
        4. If input text and image are NOT in pair: the larger the better

## 2. Generation Model
- Generate image intermediate product from random-sampled image and text intermediate products
- Model in industrials
    - Diffusion Model (Stable Diffusion)
    - Autoregressive (DALL-E)
    - Imagen (Google)
        - Generate small images as intermediate products
- Training process according to intermediate products
    - Latent representation
        1. Encoder
            - Convert image into latent representation
            - Input: Original images
            - Output: Latent representation
        2. Add noise
            - Add noise to latent representation
            - Input: Latent representation
            - Output: Noise-added latent representation
        2. Noise predictor
            - Predict noise from noise-added latent representation
            - Input
                1. Image noise-added latent representation
                2. Text latent representation
                3. Step of noise-addition process
                    -  How many times noise are added to latent representation
            - Output: Predicted Noise
- Inference process
    - Use noise predictor to predict current noises and remove them
    - Input:
        1. Normal distribution sampled latent representation
        2. Text latent representation
    - Output: De-noised latent representation

## 3. Decoder
- Decode generated intermediate products to real-world images
- Training process according to intermediate products
    - Latent representation
        - Training:
            - Train an auto-encoder model and use its decoder as decoder
            - Input: Original images
            - Output: Original images
    - Small image
        - Training:
            - Use input samples and output samples to train and decoder
            - Input: Down-sampled images
                1. Down-sampling original image into smaller samples
            - Output: Original images
- Pros: Can be trained without labelled data
