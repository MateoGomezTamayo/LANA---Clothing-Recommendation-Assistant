# LANAA - Clothing Recommendation Assistant

An intelligent AI-powered system that recommends clothing based on user preferences, deep learning, and advanced natural language processing.

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Latest-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## 📋 Overview

LANAA combines multiple AI techniques to provide personalized clothing recommendations:

- **User Profiling**: Gathers preferences through interactive questionnaires
- **Deep Learning (CNN)**: Classifies garments using a TensorFlow model trained on Fashion MNIST
- **NLP Classification**: Analyzes free-text descriptions using Zero-Shot Classification
- **Hybrid Ranking System**: Intelligently merges profile-based and NLP-based recommendations

## ✨ Features

- 🎯 **Intelligent User Profiling**
  - Gender preferences
  - Style preferences (Casual, Formal, Sport, Elegant)
  - Occasion (Daily, Work, Events, Sports)
  - Season awareness
  - Budget constraints

- 🧠 **Deep Learning Integration**
  - CNN model trained on Fashion MNIST dataset
  - Early stopping to prevent overfitting
  - Automatic performance evaluation

- 💬 **NLP-Powered Text Analysis**
  - Understands free-form user descriptions
  - Zero-shot classification with Facebook BART-MNLI
  - Context-aware recommendations

- 📊 **Visual Examples**
  - Displays sample garments for recommendations
  - Grid-based visualization using Matplotlib

## 🛠️ Installation

### Prerequisites
- Python 3.10 or higher
- pip or conda

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/MateoGomezTamayo/LANA---Clothing-Recommendation-Assistant.git
   cd LANA---Clothing-Recommendation-Assistant
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

   Or manually:
   ```bash
   pip install tensorflow tensorflow-datasets matplotlib transformers duckduckgo-search
   ```

3. **Run the notebook**
   - Open `L_A_N_A.ipynb` in Jupyter Notebook or VS Code
   - Execute the cells sequentially

## 🚀 Usage

### Running LANAA

```python
# Call the main function
main()
```

The system will:
1. Load the Fashion MNIST dataset and train the CNN model
2. Ask you questions about your preferences
3. Generate profile-based recommendations
4. Analyze your free-text description
5. Combine results into a final ranking
6. Display visual examples of recommended garments

### Example Interaction

```
¿Con qué género te identificas?
1. Masculino
2. Femenino
3. No binario/Otro
Selecciona una opción (1-3): 1

¿Qué estilo de ropa prefieres?
1. Casual
2. Formal
3. Deportivo
4. Elegante
Selecciona una opción (1-4): 1

... (more questions) ...

Escribe libremente cómo te gustaría tu outfit o prenda ideal: 
I want comfortable casual wear for summer, something light and breathable
```

## 🏗️ Architecture

### Components

1. **Data Pipeline** (`cargar_dataset_fashion_mnist`)
   - Loads Fashion MNIST dataset
   - Normalizes images
   - Batch processing with caching

2. **Deep Learning Model** (`crear_modelo_cnn`)
   - Conv2D layers for feature extraction
   - MaxPooling for dimensionality reduction
   - Dense layers for classification
   - Dropout for regularization

3. **User Profiling** (`sistema_perfilado_usuario`)
   - Interactive questionnaire
   - Input validation
   - Profile storage

4. **Recommendation Engine** (`generar_recomendaciones`)
   - Weighted scoring system
   - Category matching
   - Top-K filtering

5. **NLP Module** (`recomendar_por_texto`)
   - Zero-shot classification
   - Confidence scoring
   - Text normalization

6. **Result Fusion** (`unificar_recomendaciones`)
   - Combines profile and NLP scores
   - Ranking by combined relevance

## 📊 Model Performance

The CNN model achieves strong accuracy on the Fashion MNIST test set with:
- Early stopping to prevent overfitting
- Validation monitoring
- Accuracy and loss metrics

## 🔧 Configuration

### Weighting System

Recommendation weights can be adjusted in `PESOS_PERFIL`:

```python
PESOS_PERFIL = {
    "genero": 1.0,
    "estilo": 2.0,      # Style has high importance
    "ocasion": 2.0,     # Occasion has high importance
    "temporada": 1.5,   # Season is moderately important
}
```

### Category Mappings

Customize category recommendations by modifying `CATEGORIAS_POR_PERFIL` dictionary entries.

## 📦 Dependencies

- **tensorflow** - Deep learning framework
- **tensorflow-datasets** - Dataset loading
- **matplotlib** - Visualization
- **transformers** - NLP models (Hugging Face)
- **duckduckgo-search** - Web search integration (optional)

See `requirements.txt` for full details.

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest features
- Submit pull requests

## 📝 License

This project is licensed under the MIT License - see LICENSE file for details.

## 🎓 Educational Value

LANAA demonstrates:
- CNN architecture for image classification
- Transfer learning concepts
- Zero-shot NLP classification
- Hybrid recommendation systems
- Interactive Python applications

## 📧 Contact

For questions or suggestions, please open an issue on GitHub.

---

**Built with ❤️ by Mateo Gomez Tamayo**
