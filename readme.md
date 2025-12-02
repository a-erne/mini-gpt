## **Small Language Model: Decoder Architecture with Shakespeare Dataset**


This project implements a **decoder-only, character-level Transformer language model (GPT-style)** and trains it on the **Shakespeare dataset**.
The goal is to provide a *clear, minimal, and extensible* implementation of a small language model, along with training pipelines for both **Google Colab** and a **Cluster environment**.

For a detailed visual explanation of the Transformer Decoder Architecture:

* 📘 **Documentation:** [Transformer Decoder in Depth](https://a-erne.github.io/mini-gpt/)  
* 🎤 **Slides:** [Small Language Model Slides](https://kdrive.infomaniak.com/app/share/1951205/9f537a0f-63fb-41fe-9760-e2d601eddc60)

---

### **1. Example Output (Shakespeare-Style Generation)**


The model should generate a Shakespearean text as shown below:

**Input Sequence:**
```
O God, O God!
```
**Generated Text:**

```
O God, O God!

GLOUCESTER:
Prantagently, do that I know: consul
In the gates of appeal's a deep, that treater.

LADY CAPULET:
Romeo, come, my goods
Madam, my lord, all at greatermandancely.

Nurse:
Their wulls it subject a man; gentleman?

LADY CAPULET:
Thy lord? Saint Bolingbroke, is meet us the morrow;
For Gloucester's lord, your speak pention;
Let's so return blind him your day to-day.

HASTINGS:
Good's duke much forth, as I would say take there is.

QUEEN MARGARET:
For I may pay Bolingbroke it at with him.

```

> The generated text captures the *structure* and *cadence* of Shakespearean dialogue, though it remains nonsensical at times—expected for a model of this size (~19M parameters).


----

### **2. Training Configuration**

The best parameters used for the model were the following:

| **Parameter**             | **Value** |
|----------------------------|-----------|
| **Batch size**             | 128       |
| **Block size**             | 128       |
| **Maximum iterations**     | 1400      |
| **Learning rate**          | 3e-4      |
| **Evaluation iterations**  | 100       |
| **Embedding size (n_embd)**| 512       |
| **Number of heads (n_head)**| 8         |
| **Number of layers (n_layer)**| 6        |
| **Dropout rate**           | 0.2       |

---


**Results at Optimal Point:**

- **Training Loss**: 1.22
- **Validation Loss**: 1.62
- **Perplexity**: 5.52
- **Training Time (min)**: 18  

📊 Full experimental results:
➡️ [`./Documentation/experiments.md`](./Documentation/experiments.md).

🧪 PyTorch function walkthrough:
➡️ [`./Documentation/pytorch_notebook.ipynb`](./Documentation/pytorch_notebook.ipynb)

----


### **3. Setup & Usage**

Instructions are provided for both **Google Colab** and a **Cluster environment**.

#### **Google Colab**

1. Open the notebook: [`./Code/google_colab_code.ipynb`](./Code/google_colab_code.ipynb).
2. Upload the Shakespeare dataset: [`./Data/dataset.txt`](./Data/dataset.txt)
3. Run the cells to install dependencies, train, and evaluate the model.

#### **Cluster (SLURM or similar)**

See detailed instructions in:
➡️ [`./Code/Cluster/readme.md`](./Code/Cluster/readme.md)

---


### **4. Project Structure**

```
/
├── Code/
│   ├── google_colab_code.ipynb
│   └── Cluster/
│        └── readme.md
├── Data/
│   └── dataset.txt
├── Documentation/
│   ├── experiments.md
│   └── pytorch_notebook.ipynb
├── model/
│   ├── attention.py
│   ├── decoder_block.py
│   ├── transformer.py
│   └── utils.py
└── README.md
```

---

### **5. References & Inspiration**

This project builds on concepts from the following excellent resources:

* [Let's build GPT: from scratch, in code, spelled out.](https://www.youtube.com/watch?v=kCc8FmEb1nY)
* [ Create a Large Language Model from Scratch with Python – Tutorial ](https://www.youtube.com/watch?v=UU1WVnMk4E8&t=8658s)

These tutorials provide strong foundational intuition for decoder-only Transformers.

---

### **6. License**

MIT License.  
Original diagrams  — reuse permitted with attribution.  
Parts of this work are inspired by publicly available tutorials.
