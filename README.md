# Monet-Painter-Comp
Implemented a **CycleGAN** to translate images between Monet paintings and real-world photographs. It leverages **ResNet-based generators** and **PatchGAN discriminators** to perform high-quality style transfer.

---

### Overview

- Developed a **CycleGAN** with ResNet-based generators and PatchGAN discriminators  
- Trained on Monet paintings and real-world photos  
- Preserves content while translating artistic style  
- Generates high-quality images from one domain to another  
- Used **PyTorch** for model implementation, training, and image generation  

---

### Tech Stack

- Python  
- PyTorch  
- NumPy, OpenCV, Matplotlib  
- PIL / torchvision for image loading and transformations  

---

### Key Steps

1. **Define Generators and Discriminators**  
   - **Generator:** ResNet-based architecture with residual blocks, downsampling, and upsampling layers  
   - **Discriminator:** PatchGAN architecture to evaluate image realism  

2. **Define Loss Functions**  
   - GAN loss (MSELoss)  
   - Cycle-consistency loss (L1Loss)  
   - Identity loss (L1Loss)  

3. **Initialize Models and Optimizers**  
   - Two generators (A→B and B→A)  
   - Two discriminators (A and B)  
   - Adam optimizers with learning rate scheduler  

4. **Load Dataset with DataLoader**  
   - Monet images vs real photos  
   - Applied random horizontal flips and normalization  
   - Prepared both training and testing datasets  

5. **Sample Images**  
   - Visualize real and generated images for both domains  
   - Ensures generators produce high-quality translations  

6. **Training Loop**  
   - Train generators and discriminators simultaneously  
   - Compute GAN, cycle-consistency, and identity losses  
   - Update learning rates using LambdaLR schedule  
   - Periodically save generated images for monitoring  

7. **Image Generation & Export**  
   - Translate test set photos to Monet style using trained generators  
   - Save output images and archive for submission  

---

### Results

- High-quality style transfer between Monet paintings and photos  
- Generators produce visually realistic outputs while preserving content  
- Trained CycleGAN successfully minimizes identity, cycle, and adversarial losses  
- Images are ready for further evaluation or artistic applications  
