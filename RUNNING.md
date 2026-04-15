# Running LANAA

## Local Environment

### Step 1: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 2: Run the Notebook
```bash
jupyter notebook L_A_N_A.ipynb
```

Then execute the cells sequentially.

---

## Google Colab (Recommended for Free GPU)

1. **Upload the notebook to Colab**
   - Go to [Google Colab](https://colab.research.google.com/)
   - Upload `L_A_N_A.ipynb`

2. **Install dependencies** (run in first cell)
   ```python
   !pip install -q tensorflow tensorflow-datasets transformers
   ```

3. **Run all cells**
   - Press `Ctrl+F9` to run all cells

### Benefits of Colab:
- ✅ Free GPU/TPU access
- ✅ Pre-installed deep learning libraries
- ✅ Faster training
- ✅ Cloud storage integration

---

## System Requirements

### Minimum
- 4GB RAM
- 2GB storage
- Python 3.10+

### Recommended
- 8GB+ RAM
- 5GB storage
- GPU (CUDA compatible)

---

## Troubleshooting

### Issue: "Module not found" errors
**Solution:** Reinstall requirements with:
```bash
pip install --upgrade -r requirements.txt
```

### Issue: Model training is slow
**Solution:** Use Google Colab or a GPU-enabled environment

### Issue: Memory errors
**Solution:** Reduce batch size in `cargar_dataset_fashion_mnist()` function

---

## Performance Tips

1. **Use GPU**: Set `CUDA_VISIBLE_DEVICES` if multiple GPUs available
2. **Cache Data**: Pre-download Fashion MNIST dataset
3. **Reduce Epochs**: Change `epochs=5` parameter in `cargar_modelo_base()`
4. **Use Smaller Top-K**: Adjust `top_k=5` for faster recommendations

---

## Advanced Usage

### Custom Configuration

Edit these values for different behavior:

```python
# Reduce training epochs
cargar_modelo_base(epochs=3)

# Get more recommendations
generar_recomendaciones(perfil, nombres_clases, top_k=10)

# Adjust category weights
PESOS_PERFIL = {
    "genero": 0.5,    # Less important
    "estilo": 3.0,    # More important
    "ocasion": 2.0,
    "temporada": 1.0,
}
```

### Extend Categories

Add more predefined preferences in `PREGUNTAS_PERFIL` and `CATEGORIAS_POR_PERFIL`.

---

For more information, see [README.md](README.md)
