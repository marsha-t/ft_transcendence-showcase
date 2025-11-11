# 🏆 Tournament System

The Tournament System manages registration, player validation, matchmaking, and round progression in real time. It is designed to support both registered users and guest players, enabling flexible gameplay and automated bracket generation. Results are synchronized through RESTful APIs and persistent database states.

---

## 🎯 Overview

The tournament flow is divided into three main stages:

1. **Draft Creation** — The user initiates a tournament, specifies the number of players, and enters details for each.
2. **Match Progression** — The backend orchestrates the sequence of matches, updating results and broadcasting the next game to start.
3. **Results Display** — When all rounds conclude, the final results and statistics are shown with an option to restart a new tournament.

For a full step-by-step visualization of how the user, frontend and backend interact, see the Tournament Sequence Flow.


---
## 🧩 Key Design Features

### 1. Flexible Player Support
- Accepts both **registered users** and **guest players**
- Enforces unique display names within each tournament

### 2. Handling Non-Power-of-2 Players
- When player count is not a power of two, the system auto-seeds byes into the first round:
  - Unpaired players are advanced automatically.
  - Each “bye” is represented as a tournament match with only one player slot filled.
  - The backend creates the next-round tournament match once both parent winners exist.

### 3. REST-Based Real-Time Flow
- The client polls or re-fetches state on key events: Match completion, Tournament start or finish
- Each update writes to the database and returns the authoritative state to all clients.

--- 
## 📸 Screenshots
<div align="center">

  <table>
    <tr>
      <td><img src="../media/tournament-setup.png" width="450"/><br><b>1️⃣ Tournament Setup</b><br><sub>User defines number of players and begins setup.</sub></td>
      <td><img src="../media/tournament-add-user.png" width="450"/><br><b>2️⃣ Add Registered Player</b><br><sub>Select existing users from the database.</sub></td>
    </tr>
    <tr>
      <td><img src="../media/tournament-add-guest.png" width="450"/><br><b>3️⃣ Add Guest Player</b><br><sub>Join via guest alias for non-registered players.</sub></td>
      <td><img src="../media/tournament-confirm.png" width="450"/><br><b>4️⃣ Confirm Draft</b><br><sub>Validate all participants before tournament start.</sub></td>
    </tr>
    <tr>
      <td><img src="../media/tournament-match.png" width="450"/><br><b>5️⃣ Match In Progress</b><br><sub>Game session created and tracked by backend logic.</sub></td>
      <td><img src="../media/tournament-game-results.png" width="450"/><br><b>6️⃣ Game Results</b><br><sub>Scores updated and next match seeded automatically.</sub></td>
    </tr>
    <tr>
      <td colspan="2" align="center">
        <img src="../media/tournament-results.png" width="750"/><br>
        <b>7️⃣ Final Results</b><br>
        <sub>Displays full bracket, match outcomes, and winner statistics.</sub>
      </td>
    </tr>
  </table>

</div>
