# Pulse AI

Pulse AI is an Electron-based desktop application designed to make meetings more interactive and engaging. The app can record audio, transcribe the conversation, and generate short multiple-choice quiz questions from the discussion so users can stay focused and test their understanding in real time.

This project was built as part of a Microsoft intern hackathon and includes the hackathon-era Azure OpenAI endpoint references used during development.

## What it does

- Launches a desktop overlay app with a lightweight home screen
- Lets you configure quiz timing as either a fixed interval or a random interval
- Records microphone input and sends it to Azure Whisper for transcription
- Uses Azure OpenAI to generate context-specific quiz questions from meeting snippets
- Supports minimizing to a compact recording overlay while monitoring continues

## Tech stack

- Electron for the desktop UI
- Node.js and npm for runtime and packaging
- Azure Whisper for transcription
- Azure OpenAI for quiz generation

## Prerequisites

- Node.js 18 or newer
- npm
- Microphone access
- Access to Azure Whisper and Azure OpenAI services (or updated endpoints/credentials in the app)

## Getting started

Install dependencies:

```bash
npm install
```

Run the app locally:

```bash
npm start
```

Run in development mode with DevTools enabled:

```bash
npm run dev
```

## Build and package

Create a packaged build with Electron Builder:

```bash
npm run dist
```

## Project structure

- `src/main/main.js` - Electron main process and window setup
- `src/preload/preload.js` - IPC bridge for renderer communication
- `src/renderer/` - UI pages and frontend logic
  - `index.html` - home screen and settings modal
  - `monitor.html` - recording and transcription experience
  - `whisper.js` - audio capture, transcription, and quiz generation flow
  - `quizModal.js` - quiz prompt UI

## Configuration notes

The current implementation uses Azure endpoint and API values directly in `src/renderer/whisper.js`. Before using the app with real services, update those values with your own deployment endpoints, API keys, and model names.

## License

This project is licensed under the MIT License.
