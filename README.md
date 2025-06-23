# Pneumonia Detection from Chest X-rays

This project focuses on detecting pneumonia from chest X-ray images using deep learning. Two main approaches are implemented and compared:

- **Scratch CNN**: A custom-built convolutional neural network trained from the ground up.
- **Transfer Learning (MobileNetV2)**: A pre-trained MobileNetV2 model fine-tuned for pneumonia classification.

Both models utilize data augmentation to improve generalization and are evaluated on a balanced validation set.

---

## Results

| Model         | Accuracy | Precision | Recall | F1-score |
|---------------|----------|-----------|--------|----------|
| Scratch CNN   | ~84%     | 0.91      | 0.79   | 0.84     |
| MobileNetV2   | ~90%     | 0.94      | 0.86   | 0.89     |

- **MobileNetV2** outperformed the scratch CNN, especially in recall, which is critical in medical diagnosis to minimize false negatives.
- **Saliency maps** were used to visualize model attention, showing reasonable focus on lung areas in X-rays—an encouraging sign for clinical interpretability.

---

## Validation for Medical Use

- **MobileNetV2** demonstrates promising performance and could serve as a supportive diagnostic tool. Its high precision and recall indicate potential for reducing both false positives and false negatives, which is essential in clinical settings.
- **However**, the model has not yet been clinically validated. It was trained and tested on a public dataset under controlled conditions and lacks testing across diverse demographics, imaging devices, and real-world settings.

### To be viable for deployment in healthcare:

- Further validation on larger, heterogeneous datasets is necessary.
- Regulatory compliance (e.g., FDA approval) would be required.
- Integration with radiologist review workflows must be ensured to use the model as a decision support system, not a standalone diagnostic tool.

---

## Learnings

- **Transfer learning** is highly effective for medical imaging, offering high accuracy with less training time.
- **Model interpretability** (saliency maps) is important to build trust in AI-assisted diagnosis.
- The project illustrates a strong proof of concept, but clinical deployment would require extensive testing, ethical review, and validation protocols.

---

## Usage

1. Prepare the dataset in the `chest_xray/` directory with `train/`, `val/`, and `test/` subfolders.
2. Install dependencies:
   ```sh
   pip install tensorflow keras numpy matplotlib seaborn scikit-learn opencv-python pandas
   ```
3. Run the notebook:  
   Open `Pneumonia_Detection_Notebook.ipynb` in Jupyter or VS Code and execute all cells.

---

## Disclaimer

This project is for educational and research purposes only. It is **not** intended for clinical use without further validation and regulatory approval.