MoodWYR 🧠

MoodWYR is an interactive Would You Rather web app that turns a
player's choices into a friendly, non-clinical mood snapshot using AI.

Don't just choose. Let your choices tell a story.

✨ Features

🎮 12 interactive Would You Rather questions

🖱️ Simple one-click answer selection

📊 Live question progress indicator

🤖 AI-powered mood analysis

💬 Friendly mood insight based on the player's choices

🌱 Personalized positive activity suggestion

📱 Responsive design for desktop and mobile

🛡️ Server-side OpenAI API key handling

🔄 Play Again functionality

⚠️ User-friendly error handling when AI analysis is unavailable

🛠️ Tech Stack

Frontend: HTML, CSS, JavaScript

Backend: Node.js + Express

AI: OpenAI API

Environment variables: dotenv

Package manager: npm

📁 Project Structure

MoodWYR/
├── public/
│   └── index.html       # Frontend UI and game logic
├── server.js            # Express server and AI analysis endpoint
├── package.json         # Project metadata and dependencies
├── .env.example         # Environment variable template
└── README.md            # Project documentation

🚀 Getting Started

1. Install Node.js

Install a recent LTS version of Node.js if it is not already installed.

2. Open the project

cd MoodWYR

3. Install dependencies

npm install

4. Create your environment file

Copy .env.example to .env.

On Windows PowerShell:

Copy-Item .env.example .env

On macOS/Linux:

cp .env.example .env

Then open .env and add your OpenAI API key:

OPENAI_API_KEY=your_api_key_here
OPENAI_MODEL=gpt-4o-mini

OPENAI_MODEL is configurable. The project template uses gpt-4o-mini
by default.

Never commit your real API key to GitHub or share it publicly.

5. Start the app

npm start

The server runs on:

http://localhost:3000

Open that address in your browser.

🧩 How It Works

The player starts the game.

MoodWYR displays 12 Would You Rather questions.

The player selects one of two options for each question.

The selected answers and their associated signals are sent to the
backend.

The backend sends the choices to the OpenAI API.

The AI returns structured JSON containing:

Mood

Emoji

Confidence level

Mood insight

Positive activity suggestion

The result is displayed as the player's Mood Snapshot.

🔌 API Endpoint

POST /api/analyze

Request:

{
  "answers": [
    {
      "question": "Would you rather...",
      "selected": "Option A",
      "signal": "calm"
    }
  ]
}

Response:

{
  "mood": "Calm & Content",
  "emoji": "😊",
  "confidence": "medium",
  "insight": "A friendly interpretation of the player's choices.",
  "activity": "A small positive activity suggestion."
}

The backend validates the submitted answer structure before sending it
for analysis.

🔐 Privacy & Safety

MoodWYR is intended as an entertainment experience, not a medical or
psychological diagnostic tool.

The AI prompt specifically asks for: - Broad, non-clinical emotional
observations - Supportive and age-appropriate language - No diagnosis of
mental-health conditions - No claims of certainty from game answers

Your OpenAI API key is kept on the server through the .env file and is
not placed in the browser code.

🐛 Troubleshooting

AI is not configured

Make sure .env exists and contains a valid:

OPENAI_API_KEY=your_api_key_here

Then restart the server.

Invalid OpenAI API key

Check that the API key is correct and active.

AI rate limit reached

Wait and try the analysis again. This can happen when the API account
reaches a rate or usage limit.

Port already in use

Start the server on another port:

$env:PORT=3001
npm start

Then open:

http://localhost:3001

🎨 Design

MoodWYR uses a dark, colorful glassmorphism interface with: -
Gradient backgrounds - Rounded cards - Animated hover/selection states -
Large emoji-based choices - Responsive layouts

The interface is designed to feel lightweight, playful, and modern.

🔮 Possible Future Improvements

Save previous mood snapshots

Add multiple question packs

Add user-created questions

Add animations and transitions between questions

Add optional theme customization

Add local result history

Add authentication for persistent profiles

📜 License

This project is currently provided as a personal/academic project. Add
an appropriate open-source license if you plan to publish it publicly.

MoodWYR --- Choose. Discover. Reflect. 🧠✨
