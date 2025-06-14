## Introduction

In this blog, I walk you through how I built a Chess AI opponent using the Stockfish engine, integrated with a Java Spring Boot backend. You'll also learn how I structured the move evaluation system and used Gemini for strategic analysis.

## Why I Chose This Project

As someone passionate about backend development and artificial intelligence, building a chess engine integration was a great challenge. I also wanted to combine:

- **Spring Boot** for server-side processing
- **Stockfish** as the powerful UCI-based chess engine
- **Gemini AI** for deep strategic suggestions (experimental)

## Architecture Overview

Here's a breakdown of the core structure:

- `Frontend (HTML/CSS/JS)` — For user interactions
- `Spring Boot Backend` — Handles game state, move validation
- `Stockfish Engine` — Processes and evaluates positions
- `Gemini API` — Offers extra move suggestions (for learning/analysis)

## Core Features

- Human vs AI gameplay
- Real-time board updates
- Evaluation bar powered by Stockfish
- Gemini insights on request

## Code Snippet: Launching Stockfish

```java
ProcessBuilder pb = new ProcessBuilder("stockfish");
Process engine = pb.start();
BufferedWriter writer = new BufferedWriter(new OutputStreamWriter(engine.getOutputStream()));
BufferedReader reader = new BufferedReader(new InputStreamReader(engine.getInputStream()));
