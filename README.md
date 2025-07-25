# Model Card for SmolLM2-FT-MyDataset

- This model is a fine-tuned version of [HuggingFaceTB/SmolLM2-135M](https://huggingface.co/HuggingFaceTB/SmolLM2-135M).
- It has been trained using [TRL](https://github.com/huggingface/trl). 
- It has been trained on the [smoltalk dataset](https://huggingface.co/datasets/HuggingFaceTB/smoltalk).

![image](https://github.com/user-attachments/assets/d1f68157-fbaa-44fb-b10e-a188d83a6e32)

---
base_model: HuggingFaceTB/SmolLM2-135M
library_name: transformers
model_name: SmolLM2-FT-MyDataset
datasets: "HuggingFaceTB/smoltalk"
tags: "generated_from_trainer, smol-course, module_1, trl, sft"
---

## Quick start

```python
from transformers import pipeline
question = "If you had a time machine, but could only go to the past or the future once and never return, which would you choose and why?"
generator = pipeline("text-generation", model="gauri-sharan/SmolLM2-FT-MyDataset", device="cuda")
output = generator([{"role": "user", "content": question}], max_new_tokens=128, return_full_text=False)[0]
print(output["generated_text"])
```

## Training procedure

 


This model was trained with SFT.

### Framework versions

- TRL: 0.13.0
- Transformers: 4.48.1
- Pytorch: 2.5.0
- Datasets: 3.0.1
- Tokenizers: 0.21.0

## Citations



Cite TRL as:
    
```bibtex
@misc{vonwerra2022trl,
	title        = {{TRL: Transformer Reinforcement Learning}},
	author       = {Leandro von Werra and Younes Belkada and Lewis Tunstall and Edward Beeching and Tristan Thrush and Nathan Lambert and Shengyi Huang and Kashif Rasul and Quentin GallouÃ©dec},
	year         = 2020,
	journal      = {GitHub repository},
	publisher    = {GitHub},
	howpublished = {\url{https://github.com/huggingface/trl}}
}
```
