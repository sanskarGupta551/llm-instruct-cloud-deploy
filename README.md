# llm-instruct-cloud-deploy

**Train locally, deploy anywhere.**

> A complete, open-source workflow for instruction-tuning large language models (LLMs) on your own hardware, versioning them on Hugging Face, and enabling one-click, user-owned cloud deployment (GCP or AWS) with a Streamlit UI.

---

## 🚀 Features

- **Local fine-tuning:** Efficiently instruction-tune Llama-2 7B or Mistral 7B on consumer GPUs using quantization (QLoRA).
- **Open-source MLOps:** Full experiment tracking (MLflow/wandb), data versioning (DVC), and reproducible workflows.
- **Model versioning:** Push and manage models on Hugging Face Hub.
- **One-click cloud deployment:** Deploy a Streamlit web app and inference backend to your own AWS or GCP account—no resource sharing.
- **Cloud-native serving:** Uses managed services and Kubernetes for scalable, production-grade inference.
- **Easy teardown:** Remove cloud resources when finished to control costs.

---

## 🛠️ Tech Stack

| Stage              | Local Tools                           | Cloud Tools (AWS/GCP)        |
|--------------------|---------------------------------------|------------------------------|
| Fine-Tuning        | Llama-2 7B/Mistral 7B, QLoRA, Axolotl | N/A                          |
| Experiment Tracking| MLflow, wandb                         | N/A                          |
| Data Versioning    | DVC                                   | N/A                          |
| Model Registry     | Hugging Face Hub                      | Hugging Face Hub             |
| Inference          | llama.cpp, Ollama, LM Studio          | SageMaker/Vertex AI/K8s API  |
| Web UI             | Streamlit (local test)                | Streamlit (containerized)    |
| Orchestration      | Prefect, Airflow, Makefile            | Terraform, Helm, Kubernetes  |

---

## 📋 Workflow Overview

### 1. Local Fine-Tuning & Testing

- Prepare and version your instruction dataset (Alpaca/Self-Instruct) with DVC.
- Download and quantize Llama-2 7B or Mistral 7B for your GPU.
- Fine-tune with Axolotl, Unsloth, or LLaMA Factory; track experiments in MLflow/wandb.
- Evaluate and test the model locally using llama.cpp, Ollama, or LM Studio.

### 2. Model Versioning

- Save and document your fine-tuned model.
- Push to Hugging Face Hub (public or private repo).
- Tag and manage model versions.

### 3. One-Click Cloud Deployment

- Click **Deploy on AWS** or **Deploy on GCP** below.
- Authenticate with your cloud provider.
- Terraform provisions cloud-native infra (EKS/GKE, storage, networking).
- The model is pulled from Hugging Face and served via a scalable API.
- Streamlit UI is deployed for real-time inference and interaction.
- Monitor, use, and teardown resources—all in your own cloud account.

---

## 🚦 Quick Start

### Local Fine-Tuning

```
# Example: Prepare data and train
dvc pull data/alpaca/
python scripts/train.py --config configs/axolotl.yaml
python scripts/evaluate.py --model models/fine-tuned/
```

### Push to Hugging Face

```
huggingface-cli login
python scripts/push_to_hf.py --model models/fine-tuned/
```

---

## ☁️ Deploy to Your Cloud

**Deploy on AWS**  
[![Deploy on AWS](https://img.shields.io/badge/Deploy-AWS-blue?logo=amazon-aws)](https://github.com/llm-instruct-cloud-deploy/actions/workflows/deploy-aws.yml)

**Deploy on GCP**  
[![Deploy on GCP](https://img.shields.io/badge/Deploy-GCP-orange?logo=google-cloud)](https://github.com/llm-instruct-cloud-deploy/actions/workflows/deploy-gcp.yml)

> Clicking a button will guide you to authenticate and provision your own cloud resources. All compute and inference costs are billed to your account.

---

## 📚 Documentation

- **docs/** — Full workflow, configuration, and troubleshooting guides
- **scripts/** — Training, evaluation, deployment automation
- **k8s/** — Kubernetes manifests and Helm charts for cloud deployment
- **terraform/** — IaC modules for AWS and GCP

---

## 🤝 License

Open-source under the Apache 2.0 License.

---

## 🙋 FAQ

- **Do I need a powerful GPU?**  
  No, quantization (QLoRA 4-bit) allows training on 10GB VRAM GPUs (e.g., RTX 3080).

- **Is my model private?**  
  You control Hugging Face repo visibility (public or private).

- **Will I be billed for cloud use?**  
  Yes, all cloud resources are created in your account and you control costs.

---

## 💡 Contributing

Pull requests, issues, and suggestions are welcome!

---

## Acknowledgements

- Llama-2/Mistral, Meta, Mistral AI
- Alpaca/Self-Instruct datasets
- Hugging Face, Axolotl, Unsloth, LLaMA Factory
- Streamlit, Terraform, Kubernetes

