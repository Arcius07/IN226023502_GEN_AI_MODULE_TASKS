# 🤖 Qwen 2.5 AI Chatbot

This project implements an interactive, terminal-based AI chatbot using the **Qwen 2.5 1.5B Instruct model**. It leverages the Hugging Face `transformers` library and PyTorch to provide concise, helpful, and polite responses in a conversational format.

---

## ✨ Features

- **Model**: Powered by `Qwen/Qwen2.5-1.5B-Instruct`, a lightweight yet capable instruction-tuned model.
- **Conversational Memory**: Maintains a rolling window of chat history for context-aware responses.
- **Chat Templates**: Uses the official Qwen chat template for correct role handling.
- **Suppressed Verbosity**: Disables unnecessary Hugging Face logs for a clean terminal experience.
- **Simple Interface**: Command-line chatbot with `exit` and `quit` support.

---

## 📋 Prerequisites

Before running the project, ensure you have:

- Python 3.8+
- PyTorch
- Hugging Face Transformers
- Accelerate (for optimized model loading)

---

## ⚙️ Installation

Install dependencies using pip:

```bash
pip install transformers torch accelerate
```

---

## 🧠 How It Works

### 1. Model Loading
The model is loaded using:

```python
AutoModelForCausalLM.from_pretrained(..., device_map="auto")
```

- Automatically uses GPU (CUDA) if available
- Ensures efficient inference

---

### 2. Conversation Logic

The `generate_reply` function:

- Adds user input to `chat_history`
- Applies Qwen chat template via tokenizer
- Generates response using sampling:
  - `top_p`
  - `temperature`
- Decodes output and updates history

---

### 3. Chat Loop

The `run_chatbot` function:

- Runs an interactive CLI loop
- Uses system prompt:

```text
"You are a helpful, concise AI assistant. Answer clearly and politely."
```

---

## 🚀 Usage

1. Open the notebook:
   ```
   Task_3.ipynb
   ```

2. Run initialization cells (downloads model)

3. Start chatbot:
   ```python
   run_chatbot()
   ```

4. Interact:
   - Type your queries
   - Use `exit` or `quit` to stop

---

## ⚙️ Configuration Details

| Parameter           | Value  | Description                          |
|--------------------|--------|--------------------------------------|
| Max New Tokens     | 256    | Controls response length             |
| Temperature        | 0.7    | Balances creativity & coherence      |
| Repetition Penalty | 1.05   | Prevents repeated outputs            |
| History Limit      | 6      | Number of past exchanges retained    |

---

## 📂 Project Structure

```
.
├── Task_3.ipynb   # Main chatbot implementation
├── README.md      # Project documentation
```

---

## 💡 Notes

- First run may take time due to model download
- Works best with GPU but supports CPU
- Designed for clean and minimal terminal interaction

---

## 🔥 Future Improvements (Optional Ideas)

- Add web UI (Streamlit / React)
- Voice input support
- Deploy as API using FastAPI
- Add persistent chat history

---
