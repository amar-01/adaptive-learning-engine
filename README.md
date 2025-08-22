# Adaptive Learning Engine (Personalized Curriculum) — MERN

A minimal, end-to-end MERN app that tracks quiz performance and adapts difficulty (easy → medium → hard) per topic.

## Quick Start

### 1) Server
```bash
cd server
cp .env.sample .env      # set MONGODB_URI if needed
npm install
npm run seed             # seed sample topics/questions
npm run dev
```
Server runs at http://localhost:5000

### 2) Client
Open a new terminal:
```bash
cd client
npm install
npm run dev
```
Open the URL printed by Vite (default http://localhost:5173).

### Flow
1. Choose your name and topic on the Dashboard.
2. Start Quiz → answer questions.
3. The engine tracks your last attempts and nudges difficulty up/down using a simple accuracy rule:
   - Accuracy ≥ 80% → move harder
   - Accuracy ≤ 50% → move easier
   - Else, keep difficulty
4. Dashboard shows per-topic accuracy and attempts.

## Project Structure
```
adaptive-learning-engine/
  server/           # Node + Express + MongoDB
  client/           # React + Vite
```

## Notes
- No authentication for simplicity; users are created by name on first request.
- Extend by adding more topics/questions via `server/seed/seed.js`.
- Production build: serve `client/dist` from the Express server (commented code in `server.js`).

## License
MIT
