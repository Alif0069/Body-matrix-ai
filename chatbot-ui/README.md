# React Chatbot UI (Ollama + Mistral)

This is a mobile-first React chat UI that connects to local Ollama.

## Features

- ChatGPT-style conversation layout
- Distinct user/assistant bubbles
- Typing indicator while waiting for model response
- Sticky bottom input with Enter-to-send (`Shift+Enter` for new line)
- Smooth scroll to latest message
- Responsive design for phone and desktop

## Ollama setup

Make sure Ollama is running and the Mistral model is pulled:

```bash
ollama pull mistral
ollama run mistral
```

You can stop the interactive run after model download (`Ctrl+C`).

## Run the app

From this folder (`chatbot-ui`):

```bash
npm install
npm run dev
```

Then open the local Vite URL shown in terminal (usually `http://localhost:5173`).

## Configuration

1. Copy `.env.example` to `.env`
2. Update values if needed:
   - `VITE_OLLAMA_API_URL` default: `http://localhost:11434/api/generate`
   - `VITE_OLLAMA_MODEL` default: `mistral`

## Notes on CORS / proxy

If your browser blocks direct calls to Ollama (CORS), run requests through a backend proxy in your existing RAG server and set:

`VITE_OLLAMA_API_URL=http://localhost:<your-backend-port>/api/generate`
