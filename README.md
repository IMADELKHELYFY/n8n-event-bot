# 🚀 Intelligent Event Invitation Bot
> *Automate your event marketing with the power of AI and Data* ✨

![n8n](https://img.shields.io/badge/n8n-Workflow-ff6d5a?style=for-the-badge&logo=n8n&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-AI-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Gmail](https://img.shields.io/badge/Gmail-Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)

## 🌟 Overview

Welcome to the **Event Invitation Bot**! This project creates a seamless, automated pipeline that detects new events, generates personalized, catchy marketing copy using AI, and dispatches invitations to your subscriber list instantly. 

Say goodbye to manual email drafting and hello to **smart automation**. 🤖💌

---

## 🎨 How It Works

The workflow is orchestrated by **n8n** and follows these magical steps:

1.  **👂 Listen (Postgres Trigger)**: 
    -   The system watches your `events` database table.
    -   As soon as a new event is added... ⚡ **ACTION!**

2.  **🧠 Think (Google Gemini AI)**:
    -   The event details (Name, Place) are sent to **Google Gemini**.
    -   The AI acts as a world-class Marketing Assistant to craft a short, engaging paragraph inviting people to the event. ✍️✨

3.  **👥 Gather (Postgres Query)**:
    -   Simultaneously, the workflow retrieves your active audience from the `subscribers` table.
    -   It targets only those with `is_active = TRUE` to ensure high engagement. 🎯

4.  **🔗 Merge & Personalize**:
    -   The AI-generated content is combined with your subscriber list.
    -   Each email is personalized with the subscriber's first name. 🎩

5.  **🚀 Launch (Gmail)**:
    -   Finally, the emails are fired off via **Gmail**.
    -   Subscribers receive a warm, AI-crafted invitation in their inbox! 📬

---

## 🛠️ Tech Stack

*   **[n8n](https://n8n.io/)**: The workflow automation engine.
*   **[PostgreSQL](https://www.postgresql.org/)**: Stores event and subscriber data.
*   **[Google Gemini](https://deepmind.google/technologies/gemini/)**: The creative brain writing the emails.
*   **[Gmail](https://gmail.com/)**: The delivery service.

---

## 📋 Prerequisites

Before you lift off, make sure you have:

-   [ ] An active **n8n** instance (Self-hosted or Cloud).
-   [ ] A **PostgreSQL** database with `events` and `subscribers` tables.
-   [ ] A **Google Cloud** project with Gemini (PaLM) API enabled.
-   [ ] A **Gmail** account/Project with OAuth2 credentials.

---

## 🚀 Deployment

1.  **Import**: Import the `EventWorkFlow.json` into your n8n dashboard.
2.  **Credentials**: Setup your credentials in n8n for:
    -   Postgres
    -   Google Gemini (PaLM) API
    -   Gmail OAuth2
3.  **Activate**: Toggle the switch to **Active**. 🟢
4.  **Test**: Insert a row into your `events` table and watch the magic happen! ✨

---

## 🔮 Database Schema (Snippet)

To make this work precisely, ensure your tables look something like this:

**Events Table**
```sql
CREATE TABLE events (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255),
    place VARCHAR(255),
    -- other fields...
);
```

**Subscribers Table**
```sql
CREATE TABLE subscribers (
    id SERIAL PRIMARY KEY,
    email VARCHAR(255),
    first_name VARCHAR(255),
    is_active BOOLEAN DEFAULT TRUE
);
```

---

<div align="center">

Made with ❤️ and ☕ by **imad EL KHELYFY**

</div>
