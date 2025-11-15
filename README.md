# Dreambooth Project

A complete implementation of [DreamBooth](https://arxiv.org/abs/2208.12242), a powerful fine-tuning technique for text-to-image diffusion models. This project enables personalized image generation by training on just a few images of a subject, allowing the model to generate novel images while preserving distinctive features across diverse scenes and contexts.

## 🌟 Project Highlights

### 1. **Complete End-to-End Implementation**
- Full training pipeline from data preparation to model deployment
- Custom `DreamBoothDataset` class with support for instance and class images
- Integrated data preprocessing and augmentation pipeline

### 2. **Advanced Training Optimizations**
- **8-bit Adam Optimizer**: Reduces memory usage while maintaining training quality
- **Gradient Checkpointing**: Enables training on GPUs with limited memory
- **Mixed Precision Training (FP16)**: Accelerates training and reduces memory footprint
- **Gradient Accumulation**: Supports effective larger batch sizes
- **Prior Preservation Loss**: Prevents overfitting and maintains model generalization

### 3. **State-of-the-Art Model Architecture**
- Built on **Stable Diffusion 2** for high-quality image generation
- Fine-tuned UNet while keeping VAE and text encoder frozen for efficiency
- Support for custom token identifiers for subject-specific generation

### 4. **User-Friendly Interface**
- **Gradio Integration**: Interactive web UI for real-time image generation
- **Jupyter Notebook**: Step-by-step training workflow with clear explanations
- **Easy Model Deployment**: One-click upload to Hugging Face Hub

### 5. **Production-Ready Features**
- Automatic checkpoint saving during training
- Model conversion to FP16 for efficient inference
- Seamless integration with Hugging Face ecosystem
- Support for both private and public model sharing

### 6. **Practical Application**
- Successfully trained a personalized cat toy concept model
- Demonstrated recontextualization capabilities (placing subjects in novel scenes)
- Generated high-quality results with minimal training data (3-4 images)

## 📊 Results

Our fine-tuned model successfully generates personalized images while maintaining the distinctive features of the training subject:

![Dreambooth Results](https://github.com/Bob17293729/Dreambooth/blob/main/dreambooth_md.png)

The model can generate the subject in various contexts and styles while preserving its unique characteristics.

## 🚀 Quick Start

1. **Install Dependencies**
   ```bash
   pip install -U git+https://github.com/huggingface/diffusers.git
   pip install accelerate tensorboard transformers ftfy gradio
   pip install bitsandbytes
   ```

2. **Prepare Training Images**
   - Collect 3-5 images of your subject
   - Ensure images are diverse (different angles, backgrounds, lighting)

3. **Configure Training Parameters**
   - Set your unique identifier token (e.g., "sks toy")
   - Adjust learning rate, batch size, and training steps
   - Optionally enable prior preservation for better generalization

4. **Run Training**
   - Execute the training cells in `dreambooth_train.ipynb`
   - Monitor training progress with TensorBoard
   - Model checkpoints are saved automatically

5. **Generate Images**
   - Use the Gradio interface for interactive generation
   - Or use the trained pipeline programmatically

## 📁 Project Structure

```
Dreambooth/
├── dreambooth_train.ipynb    # Main training notebook
├── README.md                  # This file
├── dreambooth_md.png          # Training results showcase
└── result_recontextualization.png  # Recontextualization examples
```

## 🔗 Resources

- **Trained Model**: [Hugging Face Model](https://huggingface.co/sd-dreambooth-library/musecat-ppt-model)
- **Original Paper**: [DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation](https://arxiv.org/abs/2208.12242)
- **Project Report**: See `Dreambooth_Project_ cps.pdf` for detailed analysis

## 💡 Key Technical Features

- **Memory Efficient**: Optimized for training on consumer GPUs (16GB+)
- **Fast Training**: ~300 steps for convergence (adjustable)
- **Flexible**: Supports custom prompts and various generation styles
- **Scalable**: Can be extended to multiple subjects or concepts

## 📝 Notes

- Training typically requires 3-5 high-quality images of the subject
- Recommended training steps: 300-800 depending on dataset size
- Use a unique identifier token to avoid conflicts with existing concepts
- Prior preservation helps maintain model's general knowledge while learning new concepts

## 🤝 Contributing

Feel free to open issues or submit pull requests for improvements!

---

**Note**: This project is for educational and research purposes. Please ensure you have the right to use any images for training.
