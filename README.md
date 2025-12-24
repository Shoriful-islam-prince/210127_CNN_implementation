## Custom Smartphone Image Prediction

After training the CNN model on the CIFAR-10 dataset, the trained model is
evaluated on real-world images captured using a smartphone. These images
represent the same classes as CIFAR-10 and are stored inside the `custom/`
directory.

The following code loads each custom image, applies the same preprocessing
transforms used during training, and predicts the class along with the
confidence score.

```python
custom_dir = "custom"
images = sorted(os.listdir(custom_dir))  # keep order stable

model.eval()
plt.figure(figsize=(15, 6))

for i, img_name in enumerate(images):
    img_path = os.path.join(custom_dir, img_name)
    img = Image.open(img_path).convert("RGB")

    img_t = transform(img).unsqueeze(0).to(device)

    with torch.no_grad():
        output = model(img_t)
        probs = torch.softmax(output, dim=1)
        conf, pred = torch.max(probs, 1)

    plt.subplot(2, 5, i + 1)
    plt.imshow(img)
    plt.title(
        f"{classes[pred.item()]} ({conf.item()*100:.1f}%)",
        fontsize=10
    )
    plt.axis("off")

plt.suptitle("Custom Smartphone Image Predictions (CIFAR-10 CNN)")
plt.tight_layout(rect=[0, 0, 1, 0.92])
plt.show()


