# llm-instruct-cloud-deploy

**Train locally, deploy anywhere.**

## Project Overview

This project demonstrates the complete lifecycle of building, fine-tuning, and deploying a state-of-the-art instruction-following large language model (LLM) using modern MLOps practices. The solution is designed for both technical rigor and resume impact, showcasing hands-on implementation, robust documentation, and production-ready deployment.

## What Was Built

- **Efficient Local Fine-Tuning:**  
  Fine-tuned Llama-2 7B and Mistral 7B models on high-quality instruction datasets (Alpaca, Self-Instruct) using consumer-grade GPUs and memory-efficient quantization (QLoRA 4-bit).

- **End-to-End MLOps Pipeline:**  
  Implemented reproducible data versioning (DVC), experiment tracking (MLflow/wandb), and workflow orchestration (Makefile/Prefect).

- **Model Registry & Documentation:**  
  Versioned and published trained models on Hugging Face Hub with detailed model cards and evaluation metrics.

- **Production-Ready Cloud Serving:**  
  Built a fully automated, one-click deployment system for inference and a Streamlit web UI, deployable on user-owned AWS or GCP accounts using cloud-native infrastructure and Infrastructure as Code (Terraform, Helm, Kubernetes).

- **Comprehensive Documentation:**  
  Provided step-by-step guides, configuration files, and teardown instructions for both local and cloud environments.

## Key Accomplishments

- **Instruction-tuned LLMs** that outperform base models on diverse user prompts and tasks.
- **Reproducible research workflow** with complete experiment and data lineage.
- **Model versioning and sharing** via Hugging Face, enabling easy collaboration and deployment.
- **Cloud-agnostic, scalable inference** with a user-friendly Streamlit interface.
- **Resume-ready, production-grade codebase** demonstrating advanced MLOps, cloud, and AI engineering skills.

## Tech Stack

| Stage              | Local Implementation                        | Cloud Implementation (AWS/GCP)     |
|--------------------|---------------------------------------------|------------------------------------|
| Model Training     | Llama-2 7B/Mistral 7B, QLoRA, Axolotl       | N/A                                |
| Experiment Tracking| MLflow, wandb                               | N/A                                |
| Data Versioning    | DVC                                         | N/A                                |
| Model Registry     | Hugging Face Hub                            | Hugging Face Hub                   |
| Inference          | llama.cpp, Ollama, LM Studio                | SageMaker/Vertex AI/K8s API        |
| Web UI             | Streamlit                                   | Streamlit (containerized)          |
| Orchestration      | Makefile, Prefect, Airflow                  | Terraform, Helm, Kubernetes        |

## Implementation Highlights

### 1. Local Fine-Tuning & Testing

- Versioned and preprocessed instruction datasets with DVC.
- Downloaded and quantized Llama-2 7B/Mistral 7B to enable training on 10GB VRAM GPUs.
- Fine-tuned models using Axolotl/Unsloth, tracked experiments in MLflow/wandb.
- Evaluated and tested models locally using llama.cpp and Ollama for real-world prompts.

### 2. Model Versioning & Sharing

- Packaged and documented models with model cards and evaluation results.
- Published models to Hugging Face Hub with version tags for reproducibility and collaboration.

### 3. Automated Cloud Deployment

- Containerized both the inference backend and Streamlit UI.
- Developed Terraform modules for provisioning EKS (AWS) and GKE (GCP) clusters, networking, and storage.
- Created Kubernetes manifests and Helm charts for seamless deployment.
- Integrated cloud-native monitoring and provided easy teardown scripts.
- Enabled one-click deployment from the GitHub README, empowering users to launch their own scalable inference endpoints and web UIs on their cloud accounts.

## Results

- **Instruction-tuned LLMs** ready for real-world tasks: summarization, Q&A, rewriting, code generation, translation, and more.
- **Fully reproducible pipeline** from data to deployment, with all artifacts and configurations versioned.
- **Cloud-native, user-owned inference** with zero resource sharing and transparent cost control.
- **Streamlit UI** for easy interaction and demonstration of model capabilities.

## Deployment

**Deploy to your own cloud account with a single click:**

| Cloud Provider | One-Click Deploy |
|----------------|------------------|
| **AWS**        | [![Deploy on AWS](https://img.shields.io/badge/Deploy-AWS-blue?github.com/llm-instruct-cloud-deploy/actions/workflows/deploy |
| **GCP**        | [![Deploy on GCP](https://img.shields.io/badge/Deploy-GCP-orange?://github.com/llm-instruct-cloud-deploy/actions/work |

Deployments are fully automated. All resources are provisioned in your account; you retain full control and responsibility for costs.

## Documentation

- **docs/** — Detailed guides for local training, cloud deployment, and troubleshooting.
- **scripts/** — Automation for training, evaluation, and deployment.
- **k8s/** — Kubernetes manifests and Helm charts.
- **terraform/** — Infrastructure as Code for AWS and GCP.

## How to Use

1. **Clone the repo and follow the local training guide in `docs/`.**
2. **Fine-tune and test your model on your own machine.**
3. **Push your model to Hugging Face Hub.**
4. **Click a deploy button above to launch the model and Streamlit UI on your cloud account.**
5. **Access your personalized inference endpoint and web interface.**

## Impact

- Demonstrates advanced skills in MLOps, LLM fine-tuning, cloud engineering, and reproducible AI workflows.
- Ready for inclusion in resumes, portfolios, and technical interviews to showcase end-to-end project delivery and production-readiness.

## License

Apache 2.0 License.

## Acknowledgements

- Meta, Mistral AI, Hugging Face, Axolotl, Unsloth, LLaMA Factory, Streamlit, Terraform, Kubernetes, and the open-source community.

---

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

