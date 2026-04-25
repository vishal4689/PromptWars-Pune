# LearnNova: Personalized AI Tutor

## Overview
LearnNova is an intelligent learning assistant designed to help users learn new concepts effectively. It personalizes educational content and adapts its pacing to match the individual user's level of understanding. 

## Chosen Vertical
**Education / Personalized Learning Assistant**
The project is focused on the Education vertical, solving the problem of one-size-fits-all learning by building a dynamic AI tutor that gauges understanding and adapts the curriculum contextually.

## Approach and Logic
The application is built using a modern, lightweight, vanilla tech stack (HTML, CSS, JavaScript) to ensure high performance and broad compatibility without complex build steps.

1. **Authentication & Progress Tracking (Firebase):** We use Firebase Authentication to uniquely identify users. Firestore is intended to persist user progress (number of topics completed and current proficiency level).
2. **Intelligent Tutoring (Google Gemini API):** The core intelligence is driven by Google's Gemini 2.5 Flash model. We construct a system prompt that gives Gemini the persona of a patient tutor. The prompt dynamically injects the user's chosen topic and their current understanding level (e.g., Beginner).
3. **Adaptive Conversation Flow:** As the user interacts with the tutor, the chat history is maintained. Gemini ends each response with a small quiz or check-for-understanding. Based on the user's answers, Gemini adapts the complexity of the next response.
4. **Rich Aesthetics:** The UI employs a glassmorphism design with CSS variables, smooth animations, and a modern color palette to create an engaging learning environment.

## How the Solution Works
1. **Login/Signup:** The user enters their email and password. If Firebase is configured, it authenticates them. If not, it falls back to a mock login so the app can still be demonstrated.
2. **Dashboard:** The user sees their progress and can input a topic they want to learn (e.g., "Quantum Physics").
3. **Learning Session:** 
   - A chat interface opens.
   - The app sends the topic and the user's level to the Gemini API.
   - Gemini responds with a personalized introduction to the topic.
   - The user can ask clarifying questions or answer the tutor's quizzes.
   - Markdown from the AI is parsed into readable HTML in real-time.

## Assumptions Made
- **Zero-Dependency Setup:** To make the application easy to run anywhere, we assumed a zero-dependency setup utilizing ES modules (`type="module"`) and CDN links for Firebase, rather than requiring Node.js/NPM.
- **API Keys:** It is assumed that the reviewer/evaluator will input their own Gemini API Key and Firebase configuration into the respective JavaScript files (`js/gemini-api.js` and `js/firebase-config.js`) to test the live backend integrations. If left empty, the application falls back to a simulated mock mode to prevent crashing.
- **Browser Compatibility:** The application relies on modern browser features (ES modules, CSS Variables, `backdrop-filter`).

## Setup Instructions
1. Clone the repository.
2. Open `index.html` in a modern web browser (or serve using a local server like Live Server).
3. Optional: Add your Gemini API key in `js/gemini-api.js` (`GEMINI_API_KEY`).
4. Optional: Add your Firebase configuration in `js/firebase-config.js`.
