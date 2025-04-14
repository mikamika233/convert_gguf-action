AI-generate
# HF-to-GGUF Converter (with Quantization)

This GitHub Action workflow automates the process of:

- Downloading a Hugging Face model
- Converting it to GGUF format using `llama.cpp`
- Quantizing the model to one or more precision levels
- Uploading the result as an artifact

## ✅ Features

- Input your Hugging Face `repo_id` (e.g. `TheBloke/Mistral-7B-Instruct-v0.1`)
- Optionally specify a branch (e.g. `main`, `GGUF`)
- Choose one or more quantization levels (e.g. `Q4_K_M,Q5_K_M,Q8_0`)
- Fully automated, no local setup needed

## 📦 Inputs

| Name | Required | Description |
|------|----------|-------------|
| `repo_id` | ✅ | Hugging Face repository ID |
| `branch` | ❌ | Branch to download (default: `main`) |
| `quantization_levels` | ❌ | Comma-separated levels, default `Q4_K_M` |

## 🔐 Required Secrets

You must add a secret to your GitHub repo:

- `HF_TOKEN`: Your Hugging Face access token

## 🚀 How to Use

1. Go to the **Actions** tab of your GitHub repo.
2. Select the `Convert HF Model to GGUF and Quantize` workflow.
3. Click **Run workflow**.
4. Fill in:
   - Model Repo ID: e.g. `TheBloke/Mistral-7B-Instruct-v0.1`
   - Branch: `main` or other
   - Quantization Levels: `Q4_K_M,Q5_K_M,Q8_0`
5. Wait for it to finish, then download the artifacts.

## 📁 Output

You will receive `.gguf` model files for each quantization level, like:

