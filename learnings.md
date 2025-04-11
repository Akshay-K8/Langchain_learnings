# 🔥 Temperature in Language Models

The `temperature` parameter controls the **randomness** of a language model's output. It influences how **creative** or **deterministic** the responses are.

- **Lower values** (<code>0.0 - 0.3</code>) → More **deterministic** and predictable.
- **Higher values** (<code>0.7 - 1.5</code>) → More **random**, creative, and diverse.

## 📌 Recommended Temperature Settings

<table>
  <thead>
    <tr>
      <th>Use Case</th>
      <th>Recommended Temperature</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Factual answers (math, code, facts)</td>
      <td><code>0.0 - 0.3</code></td>
    </tr>
    <tr>
      <td>Balanced response (general QA, explanations)</td>
      <td><code>0.5 - 0.7</code></td>
    </tr>
    <tr>
      <td>Creative writing, storytelling, jokes</td>
      <td><code>0.9 - 1.2</code></td>
    </tr>
    <tr>
      <td>Maximum randomness (wild ideas, brainstorming)</td>
      <td><code>1.5+</code></td>
    </tr>
  </tbody>
</table>

# 🆓 Open Source Models

**Open-source language models** are **freely available AI models** that can be **downloaded, modified, fine-tuned,** and **deployed** without restrictions from a central provider.  
Unlike closed-source models such as **OpenAI's GPT-4, Anthropic's Claude, or Google's Gemini**, open-source models allow **full control and customization**.

## 🔍 Comparison: Open-Source vs Closed-Source Models

| Feature       | Open-Source Models  | Closed-Source Models |
|--------------|--------------------|----------------------|
| **Cost**       | Free to use (no API costs) | Paid API usage (e.g., OpenAI charges per token) |
| **Control**    | Can modify, fine-tune, and deploy anywhere | Locked to provider’s infrastructure |
| **Data Privacy** | Runs locally (no data sent to external servers) | Sends queries to provider’s servers |
| **Customization** | Can fine-tune on specific datasets | No access to fine-tuning in most cases |
| **Deployment**  | Can be deployed on **on-premise** servers or **cloud** | Must use vendor’s API |

Open-source models provide **greater flexibility, control, and privacy**, making them suitable for organizations that require **custom AI solutions** without dependency on third-party providers. 🚀

# 🌟 Some Famous Open Source Models

| **Model**            | **Developer**    | **Parameters**  | **Best Use Case**  |
|----------------------|-----------------|----------------|--------------------|
| **LLaMA-2-7B/13B/70B** | Meta AI        | 7B - 70B       | General-purpose text generation |
| **Mixtral-8x7B**     | Mistral AI      | 8×7B (MoE)     | Efficient & fast responses |
| **Mistral-7B**       | Mistral AI      | 7B             | Best small-scale model (outperforms LLaMA-2-13B) |
| **Falcon-7B/40B**    | TII UAE         | 7B - 40B       | High-speed inference |
| **BLOOM-176B**       | BigScience      | 176B           | Multilingual text generation |
| **GPT-J-6B**        | EleutherAI      | 6B             | Lightweight and efficient |
| **GPT-NeoX-20B**    | EleutherAI      | 20B            | Large-scale applications |
| **StableLM**        | Stability AI    | 3B - 7B        | Compact models for chatbots |

## 🔍 Where to Find Them?

You can explore and access these models on **Hugging Face**, which hosts the **largest repository of open-source LLMs**.

[🔗 Hugging Face - Explore Open-Source LLMs](https://huggingface.co/models?pipeline_tag=text-generation&sort=trending)

# 🔹 Ways to Use Open-Source Models

Open-source models can be utilized in two primary ways:

1. **Using HF Inference API**  
   - Access models via Hugging Face’s cloud-based API.
   - No need for local setup.
   - Suitable for quick inference and testing.

2. **Running Locally**  
   - Download and run models on your machine.
   - Provides full control and customization.
   - Ensures data privacy without external API calls.

# 🚨 Disadvantages of Open-Source Models

| **Disadvantage**               | **Details** |
|--------------------------------|------------|
| **High Hardware Requirements** | Running large models (e.g., LLaMA-2-70B) requires expensive GPUs. |
| **Setup Complexity**           | Requires installation of dependencies like **PyTorch, CUDA, transformers**. |
| **Lack of RLHF**               | Most open-source models don’t have **fine-tuning with human feedback**, making them weaker in instruction-following. |
| **Limited Multimodal Abilities** | Open models don’t support **images, audio, or video** like GPT-4V. |



## 🧠 LangChain Agent using Gemini with Tools

### ✅ Objective:
To build a **tool-using agent** that works seamlessly with **Gemini (Google Generative AI)** using `langchain` with structured tool-calling.
```python
# Agents
from langchain.agents import create_structured_chat_agent

agent =create_structured_chat_agent(llm,tools,prompt)
agent
```

---

### 📦 Prompt Used:V
```python
from langchain import hub

prompt = hub.pull("hwchase17/structured-chat-agent")

