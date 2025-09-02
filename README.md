# TTS Robot Frontend

This project provides a simple web interface for a text-to-speech (TTS) service powered by a remote Ollama server. It allows you to enter text, choose a voice, and adjust the speed of the speech.

## How to Use

1.  Ensure you have a remote Ollama server running and accessible. The server should be running the `OuteAI/Llama-OuteTTS-1.0-1B-GGUF:Q4_K_M` model.
2.  Open the `frontend/index.html` file in your web browser.
3.  Enter the text you want to convert to speech in the text area.
4.  Select a voice and adjust the speed using the controls.
5.  Click the "Generate Speech" button.
6.  The generated audio will play automatically and can be controlled with the audio player.

## ❗️ Important: CORS Configuration

For this application to work, the remote Ollama server **must** be configured to accept cross-origin requests (CORS) from the location where you are hosting or opening the `index.html` file.

If the server is not configured for CORS, your browser will block the request to the Ollama API, and the application will not be able to generate audio. You will see an error message in the browser's developer console.

You may need to set the `OLLAMA_ORIGINS` environment variable when starting your Ollama server to allow requests from your frontend's origin. For example:

```bash
OLLAMA_ORIGINS=http://localhost,http://127.0.0.1,file://* ollama serve
```

Refer to the [Ollama documentation](https://github.com/ollama/ollama/blob/main/docs/faq.md#how-can-i-allow-additional-origins-for-the-ollama-api) for more information on configuring CORS.
