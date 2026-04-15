# LudoPie – Multiplayer Ludo Game
### *Feature Introduction & Product Overview*
---

## Overview
LudoPie is a real-time multiplayer Ludo game built with Kotlin Multiplatform, targeting both Android and Desktop. It delivers a classic board game experience with modern online matchmaking, live gameplay synchronization, and a smooth cross-platform UI.

- Cross-platform Ludo game running natively on Android and Desktop  
- Real-time multiplayer with WebSocket-based game state sync  
- Scalable matchmaking and session management via Supabase  

---

## Core Features

### Matchmaking
- Auto-match with online players  
- Room creation and instant join  
- Race-condition-safe matchmaking via immediate session locking  

---

### Real-Time Gameplay
- Live dice rolls synced across all players  
- Turn-based flow enforced server-side  
- WebSocket connection for zero-lag state updates  

---

### 🎲 Game Board
- Full 4-player Ludo board rendering  
- Animated token movement  
- 3D dice roll animation  
- Piece capture and safe zone logic  

---

### Player Sessions
- Disconnect and reconnect handling  
- Leave-game flow with graceful session cleanup  
- Player turn timeout fallback  

---

### Result Screen
- Win/loss result display after game ends  
- Player rankings and final board state  
- Rematch or return to lobby option  

---

### Lobby & Rooms
- Active game room listing  
- Player ready state management  
- Real-time lobby updates via Supabase Realtime  

---

## Key Idea
- Seamless cross-platform experience (Android + Desktop from a single codebase)  
- Robust real-time sync with conflict-free state management  
- Lightweight architecture optimized for turn-based multiplayer  
- Scalable backend ready for concurrent game sessions  

---

## Tech Stack

### Client
- **Language:** Kotlin  
- **Framework:** Kotlin Multiplatform (KMP)  
- **UI:** Jetpack Compose (Android) · Compose Multiplatform (Desktop)  
- **Networking:** Ktor (WebSocket client)  
- **State Management:** ViewModel + StateFlow  
- **Targets:** Android · JVM Desktop  

### Backend
- **Runtime:** Node.js  
- **Protocol:** WebSocket (ws library)  
- **Database:** Supabase (PostgreSQL)  
- **Realtime:** Supabase Realtime (lobby & room sync)  
- **Hosting:** Render  

---

## Architecture Overview
- Shared business logic and game state in the `commonMain` source set  
- Platform-specific UI entry points for Android (`MainActivity`) and Desktop (`main()`)  
- ViewModel drives UI state; Repository layer abstracts WebSocket and Supabase calls  
- Server maintains authoritative game state; clients render from received snapshots  

---

## App Screens

<div align="center">

<table>
  <tr>
    <td align="center"><img width="1600" height="900" alt="Home" src="https://github.com/user-attachments/assets/aa2c209f-fe0d-4678-9f67-77c7dad90607" /><br/><sub><b>Home / Lobby</b></sub></td>
    <td align="center"><img src="https://your-image-url.com/screen2.png" width="200"/><br/><sub><b>Matchmaking</b></sub></td>
    <td align="center"><img src="https://your-image-url.com/screen3.png" width="200"/><br/><sub><b>Game Board</b></sub></td>
    <td align="center"><img src="https://your-image-url.com/screen4.png" width="200"/><br/><sub><b>Dice Roll</b></sub></td>
  </tr>
  <tr>
    <td align="center"><img src="https://your-image-url.com/screen5.png" width="200"/><br/><sub><b>Token Move</b></sub></td>
    <td align="center"><img src="https://your-image-url.com/screen6.png" width="200"/><br/><sub><b>4-Player View</b></sub></td>
    <td align="center"><img src="https://your-image-url.com/screen7.png" width="200"/><br/><sub><b>Result Screen</b></sub></td>
    <td align="center"><img src="https://your-image-url.com/screen8.png" width="200"/><br/><sub><b>Rematch / Exit</b></sub></td>
  </tr>
</table>

</div>
