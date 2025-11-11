# 📊 User Dashboard

The User Dashboard transforms in-game data into interactive insights on player performance.
It combines server-side data aggregation with frontend visualization to help players understand their progress, strengths, and match history.

---
## 🎯 Overview
The dashboard retrieves player statistics via a RESTful endpoint and visualizes them with Plotly.js.
It dynamically adjusts based on user activity — displaying charts only when enough matches have been played.

This module demonstrates:
- Full-stack data aggregation and analytics rendering
- Integration between Fastify, Prisma ORM, and Plotly.js
- Clean UI design with modular components and dynamic styling

---
## ⚙️ Architecture
- **Data Source:** Match and player tables in SQLite, queried via Prisma.
- **Backend:** API endpoints aggregate data (win rate, total matches, streaks).
- **Frontend:** Visualized using Plotly.js 

---
## 🎥 Demo
<video width="720" controls>
  <source src="../media/user-dashboard.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
