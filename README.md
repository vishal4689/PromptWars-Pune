# CivicVote: Election Process Education

## Overview
CivicVote is an intelligent assistant designed to help users understand the election process, timelines, and steps in an interactive and easy-to-follow way. It provides personalized, non-partisan guidance on voter registration, polling locations, and electoral mechanics.

## Chosen Vertical
**Election Process Education**
This project focuses on the Election Process Education vertical. It aims to demystify complex voting procedures and encourage civic engagement by providing clear, accessible information tailored to the user's current understanding and verification status.

## Approach and Logic
The application is built using a modern, lightweight tech stack (HTML, CSS, JavaScript) to ensure high performance and accessibility.

1. **Authentication & Profile Management (Firebase):** Uses Firebase Authentication for secure user sign-in. Firestore is used to track the user's progress and verification level.
2. **Document Verification (Firebase Storage):** Integrates Firebase Storage to allow users to securely upload identification documents for profile verification.
3. **Intelligent Non-Partisan Guidance (Google Gemini API):** Powered by Google's Gemini 2.5 Flash model. The system prompt enforces a strictly non-partisan persona that adapts its language based on whether the user is a "Beginner Voter" or a "Verified Voter".
4. **Interactive Learning Flow:** Users select specific election topics (e.g., Electoral College, Mail-in Voting) and engage in a conversational interface where the AI breaks down information and checks for understanding.
5. **Accessible Design:** Uses semantic HTML, ARIA labels, and a high-contrast UI to ensure usability for all citizens.

## How the Solution Works
1. **Login/Signup:** Users authenticate securely. (Mock fallback is provided if keys are not set).
2. **Dashboard:** Users view their current voter level and select an election topic to learn about.
3. **Document Upload:** Users can upload a sample ID. This simulates a verification process using Firebase Storage.
4. **Learning Session:** 
   - A chat interface opens tailored to the selected topic.
   - The Gemini AI provides structured, step-by-step guidance.
   - The AI ensures understanding before moving to the next step.

## Assumptions Made
- **API Keys:** Evaluators must input their own Gemini API Key and Firebase configuration (`js/gemini-api.js` and `js/firebase-config.js`) to test live integrations. A simulated mock mode is active by default to prevent crashing during initial review.
- **Mock Environments:** The Firebase Storage implementation is mocked to simulate the upload delay if actual Firebase credentials are not provided.
- **Browser Compatibility:** Relies on modern browser features (ES modules).

## Setup Instructions
1. Clone the repository.
2. Open `index.html` in a modern web browser.
3. Add your Gemini API key in `js/gemini-api.js` (`GEMINI_API_KEY`).
4. Add your Firebase configuration in `js/firebase-config.js` to enable real Authentication, Firestore, and Storage.
