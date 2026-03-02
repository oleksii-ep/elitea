# Quiz CLI

## High-Level Description
Quiz CLI is an interactive command-line quiz game built with modern Node.js (ES Modules). It lets users choose a category, select how many questions to answer, and play through a short quiz right in the terminal. The project demonstrates async/await, file I/O, simple input handling, and OOP concepts.

## Features
- Interactive terminal UI with prompt-based navigation
- Multiple categories loaded from a JSON file
- Option to choose number of questions (All / 3 / 5)
- Clear results and a play-again flow
- Built using ES Modules and modern Node APIs
- Demonstrates async/await, Promises, classes, array methods, destructuring, template literals, and error handling

## Project Structure
A high-level overview of the repository layout:

.
- index.js (or the main executable file)
- package.json
- README.md
- data/
  - questions.json       # Questions and categories
- src/
  - input.js              # CLI input helpers (select, confirm, pressEnter, createInterface)
  - quiz.js               # Quiz class and core quiz logic
  - colors.js             # Terminal color and formatting helpers

Notes:
- index.js contains the main program (the provided script with the shebang).
- The app loads categories and questions from data/questions.json.

## Getting Started

Prerequisites
- Node.js (recommended v16+)
- Git (optional, to clone the repo)

Installation
1. Clone the repository:
   git clone <repo-url>
   cd <repo-directory>

2. Ensure package.json has "type": "module" (required for ES Modules). If not present, add it:
   {
     "type": "module",
     ...
   }

3. Install dependencies (if any are added later):
   npm install

Run the app
- Run with Node:
  node index.js

- Or make the script executable (on Unix-like systems) and run directly:
  chmod +x index.js
  ./index.js

Basic usage
1. Choose a category from the list.
2. Choose how many questions to attempt (All / 3 / 5 when available).
3. Press Enter to start, then answer each question by entering the number of the chosen option.
4. View results and choose whether to play again.

Adding or editing questions
- Edit data/questions.json. The expected schema (example) is:

{
  "categories": {
    "js": {
      "name": "JavaScript",
      "questions": [
        {
          "question": "Which method creates a new array with all elements that pass the test?",
          "options": ["map", "filter", "reduce", "forEach"],
          "answer": 1
        },
        {
          "question": "Which keyword declares a block-scoped variable?",
          "options": ["var", "let", "const", "function"],
          "answer": 1
        }
      ]
    },
    "node": {
      "name": "Node.js",
      "questions": [
        ...
      ]
    }
  }
}

- Each question object should include:
  - question: string
  - options: array of strings
  - answer: index (0-based) of the correct option

Troubleshooting
- If you see module-related errors, ensure package.json contains "type": "module" and you are using a Node version that supports the Node namespace imports (v16+ recommended).
- If questions fail to load, check that data/questions.json exists and is valid JSON.

Contributing
- Add categories and questions by editing data/questions.json.
- Keep changes small and test the CLI after edits.
- If adding new utilities, put them under src/ and keep exported API consistent with ES Modules.

License
- Add your preferred license to package.json and a LICENSE file if desired.
