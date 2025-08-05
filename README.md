# Simple React Agent

This project implements a **React-style AI agent** using [LangGraph](https://www.langchain.com/langgraph) and [LangChain](https://www.langchain.com/). The agent is capable of generating structured Markdown reports about companies, managing local files, and generating images via API tools.

---

## Features

- ✅ Generate **company reports** in Markdown format
- 📁 Manage and manipulate files in the `data/` directory
- 🔍 Perform real-time web search using **Tavily API**
- 🖼️ Generate images based on prompts using **Together API**
- 🧠 Uses `deepseek-chat-v3` model via OpenRouter (OpenAI-compatible)

---

## Setup Instructions

1. Clone the repository and install dependencies (assumed in notebook).
2. Set environment variables for API access:

```python
os.environ['OPENAI_API_KEY'] = getpass('Your openrouter api: ')
os.environ['TAVILY_API_KEY'] = getpass('Your travily api: ')
os.environ['TOGETHER_API_KEY'] = getpass('Your together api: ')
```

3. Define your LLM and tools:
    - `ChatOpenAI` with `deepseek-chat-v3`
    - `TavilySearch` for web info
    - `FileManagementToolkit` for directory access
    - `get_image(prompt)` for image generation

---

## Usage

The agent can:

- Accept a company name as input
- Use search tools to gather information
- Generate a well-formatted `.md` file in the `data/` folder
- Optionally generate images and embed them via Markdown links

---

## Image Generation Tool

The `get_image(prompt: str)` tool uses Together's `FLUX.1-schnell-Free` model to create an image and returns a URL that can be embedded in Markdown:

```python
![Generated Image](https://link-to-image.com/photo.jpg)
```

---

## File Management

The agent has access to the `data/` folder and can:

- Read and write files
- Create new Markdown reports
- Append content to existing files

Make sure `data/` directory exists before running the notebook.

---

## Requirements

- `langgraph`
- `langchain`
- `langchain-openai`
- `langchain-community`
- `tavily-python`
- `together`
- `getpass`, `os`

---

## Example Output

The agent will create files like:

```bash
/data/company_report_openai.md
```

Each report includes:

- Company overview
- Recent news
- Financials
- Products & services
- Market trends
- Embedded images

---

## License

MIT or as specified by the author.

---

*Generated on: 2025-08-05*
