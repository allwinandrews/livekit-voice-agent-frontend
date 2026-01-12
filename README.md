Live demo: https://livekit-voice-agent-frontend.vercel.app/  
Backend repo: https://github.com/allwinandrews/livekit-python-voice-agent/

# LiveKit Voice Agent – React Frontend

This is a React + Next.js frontend for a Python-based **LiveKit voice agent**, built using the official [LiveKit JavaScript SDK](https://github.com/livekit/client-sdk-js).

The frontend provides a real-time voice interface that connects to a deployed LiveKit Agent backend and supports:

- Voice input/output
- Live transcriptions
- Optional chat input
- Camera and screen sharing (optional)

This project is based on the official **agent-starter-react** template and adapted to work with a custom Python agent implementation.

---

## Features

- Real-time voice interaction with LiveKit Agents
- Microphone capture and audio playback
- Live transcript view
- Camera video streaming support
- Screen sharing capabilities
- Audio level visualization
- Light/dark theme with system preference detection
- Configurable branding, UI text, and feature flags

This frontend is production-ready and deployed on **Vercel**.

---

## Project structure

```

livekit-voice-agent-frontend/
├── app/
│   ├── (app)/
│   ├── api/
│   ├── components/
│   ├── fonts/
│   ├── globals.css
│   └── layout.tsx
├── components/
│   ├── livekit/
│   ├── app/
│   └── ui/
├── hooks/
├── lib/
├── public/
└── package.json

````

---

## Getting started (local development)

Clone the repository and install dependencies:

```bash
pnpm install
````

Run the development server:

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

> You must have a running LiveKit Agent backend for the frontend to connect to.

---

## Backend dependency

This frontend is designed to work with a **Python LiveKit Agent backend**.

Backend repository:
[https://github.com/allwinandrews/livekit-python-voice-agent/](https://github.com/allwinandrews/livekit-python-voice-agent/)

The backend handles:

* Speech-to-text
* LLM inference
* Text-to-speech
* Conversation logic

No frontend changes are required for backend **Stage 2 (state-based conversation flow)** updates.

---

## Configuration

The frontend is highly configurable via `app-config.ts`.

### Example (`app-config.ts`)

```ts
export const APP_CONFIG_DEFAULTS: AppConfig = {
  companyName: 'LiveKit',
  pageTitle: 'LiveKit Voice Agent',
  pageDescription: 'A voice agent built with LiveKit',

  supportsChatInput: true,
  supportsVideoInput: true,
  supportsScreenShare: true,
  isPreConnectBufferEnabled: true,

  logo: '/lk-logo.svg',
  accent: '#002cf2',
  logoDark: '/lk-logo-dark.svg',
  accentDark: '#1fd5f9',
  startButtonText: 'Start call',

  // agent dispatch configuration
  agentName: undefined,
  sandboxId: undefined,
};
```

---

## Environment variables

Create `.env.local` from `.env.example` and set:

```env
LIVEKIT_API_KEY=your_livekit_api_key
LIVEKIT_API_SECRET=your_livekit_api_secret
LIVEKIT_URL=https://your-livekit-server-url

# Leave blank for automatic agent dispatch
AGENT_NAME=
```

These values must match the LiveKit project where the backend agent is deployed.

---

## Deployment

* **Frontend**: Deployed on Vercel
* **Backend**: Deployed on LiveKit Cloud

Once deployed, users can talk to the agent directly from the browser via the live demo link.

---

## Contributing

This project is based on LiveKit’s open-source starter template. Contributions are welcome via pull requests or issues.

Join the LiveKit Community Slack for support and discussion:
[https://livekit.io/join-slack](https://livekit.io/join-slack)
