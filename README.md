# Dreambooth Project

A complete implementation of [DreamBooth](https://arxiv.org/abs/2208.12242), a powerful fine-tuning technique for text-to-image diffusion models. This project enables personalized image generation by training on just a few images of a subject, allowing the model to generate novel images while preserving distinctive features across diverse scenes and contexts.

## 🌟 Project Highlights

### Why DreamBooth vs. Traditional Text-to-Image Methods?

**Traditional text-to-image models** (like standard Stable Diffusion) have limitations:
- ❌ Cannot generate specific, recognizable subjects (e.g., your pet, a unique object)
- ❌ Limited control over subject identity and appearance
- ❌ Requires extensive prompt engineering to approximate desired subjects
- ❌ Cannot maintain consistent subject features across different scenes

**DreamBooth advantages**:
- ✅ **Personalized Generation**: Train on just 3-5 images to learn a specific subject
- ✅ **Identity Preservation**: Maintains distinctive features across diverse contexts
- ✅ **Recontextualization**: Place your subject in any scene or style you imagine
- ✅ **Fine-grained Control**: Use a unique token identifier for precise subject generation
- ✅ **Efficient Training**: Fine-tune only the UNet, keeping the model lightweight

### User-Friendly Design of This Codebase

This implementation prioritizes ease of use and accessibility:

1. **📓 Jupyter Notebook Workflow**
   - Step-by-step cells with clear explanations
   - No need to write complex training scripts from scratch
   - Interactive execution allows you to understand each step

2. **🎨 Interactive Gradio Interface**
   - Real-time image generation without coding
   - User-friendly web UI for testing your trained model
   - Instant visual feedback on generation results

3. **🔧 Simplified Configuration**
   - All training parameters in one place
   - Clear parameter descriptions and recommended values
   - Easy to customize for your specific use case

4. **☁️ Seamless Hugging Face Integration**
   - One-click model upload to Hugging Face Hub
   - Support for both private and public model sharing
   - Easy model loading for inference anywhere

5. **💾 Automatic Checkpointing**
   - Models saved automatically during training
   - No risk of losing progress
   - Easy to resume training or use intermediate checkpoints

6. **🚀 Production-Ready Optimizations**
   - Memory-efficient training (8-bit Adam, gradient checkpointing)
   - FP16 mixed precision for faster training
   - Works on consumer GPUs (16GB+)

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

## 📊 Results

Our fine-tuned model successfully generates personalized images while maintaining the distinctive features of the training subject:

![Dreambooth Results](https://github.com/Bob17293729/Dreambooth/blob/main/dreambooth_md.png)

The model can generate the subject in various contexts and styles while preserving its unique characteristics.

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

## 📝 Notes

- Training typically requires 3-5 high-quality images of the subject
- Recommended training steps: 300-800 depending on dataset size
- Use a unique identifier token to avoid conflicts with existing concepts
- Prior preservation helps maintain model's general knowledge while learning new concepts

## 🤝 Contributing

Feel free to open issues or submit pull requests for improvements!

---

**Note**: This project is for educational and research purposes. Please ensure you have the right to use any images for training.
