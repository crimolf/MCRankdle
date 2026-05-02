# MCRankdle

**Rank-guessing game for MCSR.**  

🔗 **Live at [mcrankdle.com](https://mcrankdle.com)**

---

## 📸 Screenshots

<!-- Replace with your actual screenshots -->
![MCRankdle Demo](./screenshots/demo.gif)

<img width="1817" height="944" alt="image" src="https://github.com/user-attachments/assets/44052a55-1f15-4103-9847-e05ee48138b4" />


---

## ✨ Features

- **Daily challenge** — a new player clip to guess every day
- **Rank guessing** — pick the rank you think matches the gameplay
- **OAuth login** — sign in with Google or Twitch

---

## 🔧 Tech Stack

| Tech | Role |
|---|---|
| Java 17 | Language |
| Spring Boot | Application framework |
| Spring Security | Authentication (JWT + OAuth2) |
| OAuth2 | Google & Twitch login |
| PostgreSQL | Database |
| Vaadin / Hilla | Full-stack framework |
| React | UI components |
| Docker | Containerization |
| Google Cloud Run | Hosting (frontend + backend) |
| Cloudflare | DNS & security |

---

## 🏗️ Architecture

Unlike RankedRecords, this project is built as a **monolith** using Vaadin/Hilla — the frontend and backend are deployed together as a single unit on Google Cloud Run.

```
┌──────────────────────────────────────┐
│         Google Cloud Run             │
│                                      │
│  ┌────────────┐   ┌────────────────┐ │
│  │   React    │   │  Spring Boot   │ │
│  │  (Hilla)   │◄─►│   Backend      │ │
│  └────────────┘   └───────┬────────┘ │
│                           │          │
│                   ┌───────▼────────┐ │
│                   │  PostgreSQL    │ │
│                   └────────────────┘ │
└──────────────────────────────────────┘
         │
    Cloudflare
    (DNS & CDN)
```

Choosing a monolithic approach for this project kept infrastructure simple and deployment fast — the right trade-off for a smaller, focused application.

---

## 📁 Related

> The source code for this project is kept private.  
> Feel free to reach out on [LinkedIn](https://linkedin.com/in/alessandro-lupo) if you want to know more.
