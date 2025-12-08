# Model-View-Controller App

![Python](https://img.shields.io/badge/Python-3.12%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-Framework-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-ORM-CA3C32?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![psycopg2](https://img.shields.io/badge/psycopg2-PostgreSQL_Driver-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Passlib](https://img.shields.io/badge/Passlib-Bcrypt-yellow?style=for-the-badge)
![python-jose](https://img.shields.io/badge/python--jose-JWT-orange?style=for-the-badge)
![Pydantic Settings](https://img.shields.io/badge/Pydantic-Settings-3776AB?style=for-the-badge&logo=pydantic&logoColor=white)
![Jinja2](https://img.shields.io/badge/Jinja2-Templating-EE4C2C?style=for-the-badge&logo=jinja&logoColor=white)
![MVC](https://img.shields.io/badge/Architecture-MVC-7952B3?style=for-the-badge)
![Strategizer](https://img.shields.io/badge/Pattern-Strategizer-4CAF50?style=for-the-badge)

One of the things that held me back for a long time in software development was the gap between academic content and real-world tutorials. Academic material was too abstract, and tutorials were often too specific. That combination left me confused for far too long. So I decided to break down the Model–View–Controller pattern into a more practical, “fabric-style” step-by-step **way of thinking**.

To me, MVC is still a great way to validate ideas. It's simple, easy to understand, and effective. You don't need 500+ meetings to discuss every detail, sometimes proving the concept quickly is far more valuable. Move fast, make mistakes faster, understand the real problems, think bigger, and redesign when needed.

Someone once told me: “Your code is not your relative. Don't get too attached to it, let it go when you need to.”

I separate my process on:

1. [Preparation](#preparation)
2. [Coding](#coding)
3. [Delivery](#delivery)
4. [Value Confirmation](#value-confirmation)
5. [Extra](#extra)

## Preparation

Here's my checklist of **practical, clarifying questions** you can ask yourself during the preparation phase of an MVC project, right when you are sketching the problem/solution and setting up `requirements.txt` and `.env`.
These questions help you define **Model**, **View**, **Controller**, plus operational and architectural boundaries.

---

### General Problem-Shaping Questions

1. **What problem am I solving in one sentence?**
2. **Who is the primary user?**
3. **What is the minimum version of the solution that actually delivers value?**
4. **What assumptions am I making that I should validate early?**

---

### Model (Data + Business Logic) Questions

1. **What are the core entities in this domain?**
2. **What data do I need to store, retrieve, or transform?**
3. **Where will the data come from?** (DB, API, file, user input)
4. **What validations are essential from day one?**
5. **What business rules must be enforced consistently?**
6. **What is the simplest schema that works for V1?**
7. **Do I need migrations from Day 1?**
8. **Which parts of the model must be independent from the UI?**

---

### View (Interaction + Presentation) Questions

1. **How does the user interact with the system in V1?**
   (CLI, REST API, UI, mobile, webhook, etc.)
2. **What is the minimum set of screens or endpoints I need to expose?**
3. **What information must each view display or capture?**
4. **What errors or edge cases must the view handle gracefully?**
5. **What's the fastest way to prototype the view?**
6. **Is the view disposable?** (In early MVC, it often should be.)

---

### Controller (Flow + Coordination) Questions

1. **What is the main workflow from the user's perspective?**
2. **What triggers each action?**
3. **Which responsibilities belong to the controller vs. model?**
4. **How does the controller translate user requests into model operations?**
5. **What side effects do I need to manage?** (I/O, API calls, logging)
6. **What async tasks or background jobs might appear later?**

---

### Operational Setup Questions (requirements.txt / .env)

#### `requirements.txt`

1. **Which frameworks/libraries do I truly need for V1?**
2. **Am I choosing a lightweight stack, or do I need a full framework?**
3. **Which dependencies are essential vs. optional?**
4. **Do I need version pinning for stability?**
5. **Any dev-only libs I should separate?**

#### `.env`

1. **Which configuration must be environment-specific?**

   * DB URLs
   * API keys
   * Secrets
   * Feature flags
2. **What defaults can I safely hardcode for dev only?**
3. **Is anything leaking into the repo that shouldn't?**
4. **Do I need a template file (`.env.example`)?**

---

### Validation / Risk Questions

1. **What part of the system is most uncertain or risky?**
2. **What can I prototype in under 60 minutes to de-risk it?**
3. **What can fail?** (network, user input, data model, third-party services)
4. **What metrics or logs do I need to collect early?**

---

### Final “Go / No-Go” Questions Before Coding

1. **Can I sketch the entire workflow on one page?**
2. **Does every component (M, V, C) have a clear responsibility?**
3. **Is V1 small enough to finish quickly?**
4. **Is the project folder structure decided?**
5. **Is my environment ready to run the first request end-to-end?**

## Extra

### Tech Stack & Architecture

#### Languages & Runtime
![Python](https://img.shields.io/badge/Python-3.12%2B-blue?style=for-the-badge&logo=python&logoColor=white)

#### Backend Framework
![FastAPI](https://img.shields.io/badge/FastAPI-Framework-009688?style=for-the-badge&logo=fastapi&logoColor=white)

#### Core Dependencies
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-ORM-CA3C32?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![psycopg2](https://img.shields.io/badge/psycopg2-PostgreSQL_Driver-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Passlib](https://img.shields.io/badge/Passlib-Bcrypt-yellow?style=for-the-badge)
![python-jose](https://img.shields.io/badge/python--jose-JWT-orange?style=for-the-badge)
![Pydantic Settings](https://img.shields.io/badge/Pydantic-Settings-3776AB?style=for-the-badge&logo=pydantic&logoColor=white)
![Jinja2](https://img.shields.io/badge/Jinja2-Templating-EE4C2C?style=for-the-badge&logo=jinja&logoColor=white)

### Architecture Topics
![MVC](https://img.shields.io/badge/Architecture-MVC-7952B3?style=for-the-badge)
![Strategizer](https://img.shields.io/badge/Pattern-Strategizer-4CAF50?style=for-the-badge)

## Preparation
