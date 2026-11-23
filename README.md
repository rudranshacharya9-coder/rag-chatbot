# rag-chatbot

Ask questions across multiple PDFs without switching between documents. This Python RAG chatbot provides a Gradio interface to chat with PDFs locally, with model options from Hugging Face and Ollama.

## Features

- Process multiple PDF files for question answering.
- Chat with your documents through a Gradio web interface.
- Use models from Hugging Face or Ollama.
- Run locally or use the Kaggle notebook with an Ngrok tunnel.

## Installation

The commands below assume this standalone repository retains the donor project's Python package and entry point. Replace `YOUR-ORG` with its GitHub owner.

Install [uv](https://docs.astral.sh/uv/) if it is not already available:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Make sure `~/.local/bin` is on your `PATH`. Then clone the repository and install its locked dependencies:

```bash
git clone https://github.com/YOUR-ORG/rag-chatbot.git
cd rag-chatbot
uv sync --locked
```

For Ollama-backed models, install [Ollama](https://ollama.com/) separately. On Linux:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

Alternatively, download the source archive associated with the GitHub `v0.1.0` release tag once that release is published:

```bash
curl -L -o rag-chatbot-v0.1.0.tar.gz https://github.com/YOUR-ORG/rag-chatbot/archive/refs/tags/v0.1.0.tar.gz
```

## Usage

Start the local interface:

```bash
uv run python -m rag_chatbot --host localhost
```

Open **http://localhost:7860/**, provide your PDF files through the interface, and ask questions about their contents.

To run with an Ngrok tunnel instead, install Ngrok, configure your authentication token, and use the supplied script:

```bash
bash ./scripts/run.sh --ngrok
```

An Ngrok URL exposes the interface beyond your machine. Use the localhost command when you only need local access.

## License

Licensed under Apache-2.0. This project is based on [datvodinh/rag-chatbot](https://github.com/datvodinh/rag-chatbot), also licensed under Apache-2.0. Retain the upstream license and applicable attribution notices when redistributing derived code.

## Related projects

Other repositories supplied alongside this project:

- [Sarthakkrishna/casskop-zoqe](https://github.com/Sarthakkrishna/casskop-zoqe): CassKop-related repository; its exact functionality was not specified in the supplied data.
- [EngHirsi/wg-access-server](https://github.com/EngHirsi/wg-access-server): A server for managing WireGuard access.
- [orpofardin/redis-dump-go](https://github.com/orpofardin/redis-dump-go): A Go tool for exporting Redis data.

