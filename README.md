# 🧠 Product Info Extractor — Fine-Tuning in One Notebook

This project fine-tunes a language model entirely within a single Jupyter Notebook to extract structured fields — `name`, `category`, `manufacturer`, and `price` — from product descriptions.

✅ All logic — dataset prep, model training, and inference — is inside `product_info_finetune.ipynb`.

---

## 💡 Example Task

**Input:**
```
Maggi noodles pack of 2 by Nestlé for $0.50
```

**Expected Output:**
```json
{
  "name": "Maggi noodles",
  "category": "",
  "manufacturer": "Nestlé",
  "price": "$0.50"
}
```

---

## 🧾 What This Notebook Does

✔ Prepares a noisy, realistic dataset of product descriptions  
✔ Handles missing fields gracefully by returning `""`  
✔ Fine-tunes a model (e.g., Mistral, LLaMA, etc.) using TRL or Unsloth  
✔ Runs inference to verify accuracy

---

## 🧠 Tech Stack

- Python 🐍
- Hugging Face Transformers + Datasets
- [Unsloth](https://github.com/unslothai/unsloth) (for fast fine-tuning)
- 🤗 TRL / SFTTrainer
- JSONL formatted training data

---

## 🧪 Example Inference

```python
from transformers import pipeline

pipe = pipeline("text2text-generation", model="your-model-name")

res = pipe("Colgate toothpaste 200g by Colgate-Palmolive for $3")
print(res[0]["generated_text"])
```

Expected:
```json
{
  "name": "Colgate toothpaste",
  "category": "",
  "manufacturer": "Colgate-Palmolive",
  "price": "$3"
}
```

---

## 📁 File Structure

```
├── Fine-Tune.ipynb   # 💥 Everything is in here
├── Data.jsonl            # (optional) saved dataset
├── README.md                     # you're reading this
```

---

## 📖 License

MIT License — free to use, modify, and share.

---

## 🙋‍♂️ Author

Built by Puneet Rawat.  
Feel free to fork, star, or open issues for suggestions or improvements.
