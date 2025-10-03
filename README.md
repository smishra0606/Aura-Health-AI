# Aura Health AI

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Maintained](https://img.shields.io/badge/Maintained%3F-yes-green.svg)

*An intelligent, multilingual health triage assistant powered by AI and Web Speech technology.*

---

![Aura Health AI Demo](https://i.ibb.co/bJCZzX1/aura-health-ai-demo.png)

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [🚀 Core Functionalities (Step-by-Step)](#-core-functionalities-step-by-step)
  - [1. AI Symptom Analysis](#1-ai-symptom-analysis)
  - [2. Voice Input (Speech-to-Text)](#2-voice-input-speech-to-text)
  - [3. Voice Narration (Text-to-Speech)](#3-voice-narration-text-to-speech)
  - [4. Responsive & Informative UI](#4-responsive--informative-ui)
- [🛠️ Tech Stack](#️-tech-stack)
- [⚙️ Getting Started](#️-getting-started)
- [⚠️ Disclaimer](#️-disclaimer)
- [📄 License](#-license)

## 📖 About the Project

Aura Health AI is a web-based, multilingual health triage assistant designed to provide users with immediate, preliminary guidance on their health symptoms. In a world where access to quick medical advice can be challenging, this application serves as a responsible first step, helping users articulate their symptoms and understand potential next steps for seeking professional care.

Powered by a sophisticated large language model, Aura Health AI analyzes user input to generate structured, easy-to-understand advice while consistently emphasizing the importance of consulting a professional.

## 🚀 Core Functionalities (Step-by-Step)

This application integrates several modern web technologies to provide a seamless and accessible user experience.

### 1. AI Symptom Analysis

The primary feature is the AI-powered analysis, which is fully bilingual.

1.  **Enter Symptoms:** Users can type their health concerns into the main text area.
2.  **Select Output Language:** Using the **"AI Output Language"** dropdown, users choose whether they want the response in **English** or **Hindi**.
3.  **Analyze:** Upon clicking the "Analyze" button, a request is sent to the SambaNova AI API, including the user's symptoms and the chosen language instruction.
4.  **Receive Guidance:** The AI's structured response is displayed in the selected language.

### 2. Voice Input (Speech-to-Text)

For hands-free interaction, users can speak their symptoms directly into the application.

1.  **Select Input Language:** Users first choose their speaking language (English or Hindi) from the **"Voice Input Language"** dropdown.
2.  **Activate Microphone:** Clicking the microphone icon activates the browser's speech recognition.
3.  **Transcribe:** The user's speech is automatically transcribed and populated into the symptom text area, ready for analysis.

### 3. Voice Narration (Text-to-Speech)

To enhance accessibility, the AI's response can be read aloud.

1.  **Select a Voice:** After an AI response appears, a dropdown menu is dynamically populated with all voice options available in the user's browser.
2.  **Listen:** The user can select a preferred voice (e.g., a Hindi voice for a Hindi response) and click the "Listen" button.
3.  **Control Playback:** The button toggles between a "Play" and "Stop" state, allowing the user to start and stop the narration at any time.

### 4. Responsive & Informative UI

The user interface is designed to be both intuitive and responsible.

-   **Three-Column Layout:** On desktop screens, the application features a professional three-column layout. The central column houses the main tool, while the sidebars provide persistent, helpful information. On mobile devices, these columns stack vertically for a seamless experience.
-   **Usage Tips:** The left sidebar provides users with clear instructions on how to phrase their symptoms to get the most accurate AI-generated guidance.
-   **Emergency Warnings:** The right sidebar contains a crucial, highly visible list of symptoms that require immediate medical attention, ensuring user safety.

## 🛠️ Tech Stack

This project is a single-file web application built with client-side technologies:

-   **HTML5**
-   **Tailwind CSS** (via CDN)
-   **JavaScript (ES6+)**
-   **Web Speech API** (for Speech-to-Text and Text-to-Speech)
-   **SambaNova AI API**

## ⚙️ Getting Started

To get a local copy up and running, follow these simple steps.

1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/aura-health-ai.git](https://github.com/your-username/aura-health-ai.git)
    ```
2.  Navigate into the project directory:
    ```bash
    cd aura-health-ai
    ```
3.  **IMPORTANT: Add Your API Key**
    -   Open the `index.html` file in a text editor.
    -   Find the JavaScript section and replace the placeholder API key with your own SambaNova AI key:
        ```javascript
        const API_KEY = 'YOUR_SAMBANOVA_API_KEY_HERE';
        ```
4.  Open the `index.html` file in your browser to run the application.

## ⚠️ Disclaimer

> **Important Medical Disclaimer**
>
> Aura Health AI is an informational tool and is **not** a substitute for professional medical diagnosis, advice, or treatment. It is intended for preliminary guidance only. Always consult a qualified healthcare provider for any medical concerns or before making any decisions related to your health. Do not disregard professional medical advice or delay in seeking it because of something you have read or heard from this application.

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.
