# Aura Health AI - Neural Triage

Aura Health AI is a single-page, front-end health assistant built in pure HTML, CSS, and JavaScript. It provides an interactive chat-style experience for symptom triage, optional image-based analysis, quick symptom prompts, body-map and pain-scale inputs, voice features, and PDF export.

The application uses the Gemini model API directly from the browser to generate responses.

## Table of Contents

- Overview
- Features
- Tech Stack
- Project Structure
- How the App Works
- Getting Started
- Gemini API Configuration
- Usage Guide
- Safety and Disclaimer
- Security Considerations
- Browser Support
- Troubleshooting
- Future Improvements

## Overview

This project is designed as an educational and demo healthcare assistant experience with a polished UI and rich interactions. It does not use a backend server and runs as a static page.

Core idea:
- User enters symptoms (text, voice, body map, pain scale, or image)
- App sends request to Gemini API
- AI returns structured guidance with follow-up suggestion chips
- User can continue the triage conversation

## Features

### 1. Conversational Symptom Triage
- Chat-based interface with user and assistant message bubbles
- Typing indicator while waiting for AI response
- Suggestions as clickable follow-up chips
- Structured assistant output sections (possible causes, actions, urgent care cues)

### 2. Image Attachment and Analysis
- Upload image files (PNG, JPG, WEBP)
- Preview before sending
- Remove image before submit
- Sends image as inline base64 data to Gemini for multimodal analysis

### 3. Guided Input Tools
- Quick action symptom presets from left sidebar
- Interactive body map modal (head, neck, chest, stomach, arms, legs)
- Pain intensity modal with 1-10 slider and emoji severity feedback

### 4. Voice Capabilities
- Speech-to-text input using Web Speech Recognition
- Text-to-speech playback of the latest AI reply
- Voice selection dropdown for TTS voice choice
- Language-aware speech recognition toggle (English/Hindi)

### 5. Session Controls
- Light/dark theme toggle
- Export chat session as PDF (html2pdf)
- Clear conversation session

### 6. Responsive UI
- Desktop: dual sidebars + center chat
- Mobile: collapsible left sidebar and optimized controls
- Animated backgrounds, rings, and status visuals

## Tech Stack

- HTML5
- CSS3 (custom properties, animations, responsive media queries)
- Vanilla JavaScript (no build system)
- External libraries/CDNs:
  - Font Awesome (icons)
  - Google Fonts (Syne, DM Sans)
  - html2pdf.js (PDF generation)
- Browser APIs:
  - Fetch API
  - Web Speech API (SpeechRecognition, SpeechSynthesis)
  - FileReader API

## Project Structure

This repository currently uses a single-file architecture:

- index.html: full application (markup, styles, and script)

Generated output at runtime:
- Aura-Health-AI-Session.pdf: downloaded chat transcript (on user action)

## How the App Works

### UI Layer
The page renders:
- Left sidebar: quick prompts and mock vitals cards
- Center area: chat header, message thread, attachment preview, chips, input controls
- Right sidebar: informational cards (monitoring, AI engine status, disclaimer)

### Interaction Layer
Event handlers are attached after DOMContentLoaded for:
- Sending messages
- Quick prompt clicks
- Sidebar open/close
- Modal open/close
- Voice input start/stop
- Theme toggle
- Session clear and PDF export

### AI Request Flow
1. Collect text input and optional image attachment
2. Build a prompt instructing structured medical-style output and chip format
3. Send request to Gemini endpoint
4. Parse response text
5. Extract [CHIP: ...] tags using regex
6. Render response and clickable suggestion chips

### Message Rendering
- User messages are rendered as text (and optional image)
- Bot messages are rendered as HTML to preserve semantic structure
- Markdown-style bold (**) is converted to strong tags

## Getting Started

### Option A: Run directly
1. Clone or download the repository
2. Open index.html in a modern browser

### Option B: Serve locally (recommended)
Using any static server helps avoid some browser constraints:

- Python:
  python -m http.server 5500

Then open:
- http://localhost:5500

## Gemini API Configuration

The app currently defines a Gemini API key directly in client-side JavaScript.

Location in code:
- index.html -> JavaScript section -> GEMINI_API_KEY constant

To configure:
1. Replace the placeholder/key string with your own valid Gemini API key
2. Reload the page

Important:
- Exposing API keys in frontend code is insecure for production
- For production, move API calls behind a backend proxy and store keys in server environment variables

## Usage Guide

1. Enter symptoms in the input box and click send
2. Optionally upload a report/image before sending
3. Use quick prompts for common symptom combinations
4. Use body map and pain scale for guided input
5. Use voice input for hands-free symptom entry
6. Use read-aloud for AI responses
7. Export conversation to PDF if needed

## Safety and Disclaimer

This project is educational and not a medical device.

- It does not provide professional diagnosis or treatment
- Users should consult qualified healthcare professionals
- In emergency situations, contact local emergency services immediately

## Security Considerations

Current implementation considerations:

- API key exposure risk: key is embedded in frontend JavaScript
- No authentication or usage quota control at app level
- Bot response HTML is inserted into the DOM (trusted API source assumed)

Recommended hardening:

- Move AI calls to backend API
- Keep API key in server-side secret store
- Add response sanitization/allowlist if rendering HTML
- Add rate limiting and abuse protection
- Add CSP and stricter security headers when deployed

## Browser Support

Best experience:
- Latest Chrome/Edge/Firefox

Notes:
- SpeechRecognition support is browser-dependent
- Microphone use requires user permission
- Some mobile browsers may limit speech features

## Troubleshooting

### No AI response
- Verify API key is valid
- Check network connectivity
- Confirm Gemini endpoint quota/limits are not exceeded

### Voice input does not work
- Ensure browser supports SpeechRecognition
- Grant microphone permissions
- Try HTTPS or localhost context when required

### PDF export fails
- Ensure html2pdf CDN is reachable
- Retry with fewer/shorter chat entries if memory constrained

### Empty or malformed AI output
- Temporary model/network issue
- Retry request
- Confirm API response schema still matches parser expectations

## Future Improvements

- Split code into modular files:
  - index.html
  - styles.css
  - app.js
- Add backend proxy for secure API usage
- Add persistent chat history storage
- Add multilingual UI labels (not only AI output language)
- Add real medical knowledge guardrails and risk scoring workflow
- Add test coverage and linting pipeline

---

If you are maintaining this project, first priority should be securing API access with a backend layer before any public deployment.
