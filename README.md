# Assignment 4: Learning PDF using GAN
**Name:** [Sandeep Kaur]
**Roll No:** 102483081

## 1. Transformation Parameters
Based on Roll Number 102483081:
- **a_r**: 0.5
- **b_r**: 0.6
- **Transformation Equation**: z = x + 0.5 * sin(0.6 * x)

## 2. Methodology
1. **Data Preprocessing**: 
   - Loaded 'no2' data from the India Air Quality dataset.
   - Cleaned missing values and applied the transformation equation above.
   - Standardized the data (mean=0, std=1) to ensure stable GAN training.

2. **GAN Architecture**:
   - **Generator**: A 3-layer neural network (Input -> 16 -> 32 -> Output) using LeakyReLU activation. It takes random noise (dimension 5) and outputs a fake sample.
   - **Discriminator**: A 3-layer neural network (Input -> 32 -> 16 -> Output) using LeakyReLU and a final Sigmoid activation to classify samples as Real (1) or Fake (0).

3. **Training**:
   - Trained for 20 epochs with a batch size of 2048.
   - Used Binary Cross Entropy (BCE) Loss and Adam Optimizer (Learning Rate = 0.0002).

## 3. Observations
- **Mode Coverage**: The generated distribution (Red curve in the plot) closely overlaps with the real transformed data (Blue curve), indicating the GAN successfully learned the probability density function.
- **Training Stability**: The Generator and Discriminator losses remained stable and did not diverge, showing a balanced adversarial training process.
- **Quality**: The GAN effectively modeled the unknown PDF without assuming any parametric form (like Gaussian).