# ✨ Email Reply Generator Using AI 

A complete AI-powered email reply generator with **Spring Boot Backend**, **React Frontend**, and a **Chrome Extension** that integrates directly into Gmail.

This project allows users to paste or select email text, choose a tone, and generate a professional AI reply using Google **Gemini API**.

---

# 📌 Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [System Architecture](#system-architecture)
4. [Project Structure](#project-structure)
5. [Tech Stack](#tech-stack)
6. [Backend Setup (Spring Boot)](#backend-setup-spring-boot)
7. [Frontend Setup (React)](#frontend-setup-react)
8. [Chrome Extension Setup](#chrome-extension-setup)
9. [API Details](#api-details)
10. [Environment Variables](#environment-variables)
11. [Running the Entire System](#running-the-entire-system)
12. [Screenshots (Optional)](#screenshots-optional)
13. [Future Enhancements](#future-enhancements)
14. [License](#license)

---

# 📌 Overview

The **Email Writer Application** is a full-stack AI-powered solution that helps users quickly generate professional email replies.
It consists of:

* **Backend (Spring Boot Java)** → Sends prompts to Gemini AI and generates the reply
* **Frontend (React + Material UI)** → User interface to input email text and generate replies
* **Chrome Extension (Manifest v3)** → Adds an “AI Reply” button inside Gmail and auto-inserts AI reply

This project is ideal for productivity tools, corporate email assistants, customer support automation, and AI-integrated communication systems.

---

# 🚀 Features

### ✅ Backend (Spring Boot)

* REST API endpoint for generating email replies
* Uses **WebClient** to call Gemini API
* Custom prompt generation
* Handles tone (professional, casual, friendly)
* Configurable via `application.properties` and environment variables

### ✅ Frontend (React)

* Responsive UI
* Input for email content
* Tone selection dropdown
* Loading indicator
* Auto-copy functionality
* Connects directly to backend API

### ✅ Chrome Extension (Gmail Integration)

* Adds **AI Reply** button inside Gmail
* Detects compose window
* Reads email content automatically
* Sends request to backend
* Inserts generated reply in Gmail editor

---

# 🏗️ System Architecture

```
+-------------------+        +--------------------+        +---------------------------+
|  React Frontend   | -----> | Spring Boot API    | -----> | Google Gemini AI Service  |
+-------------------+        +--------------------+        +---------------------------+

                     +---------------------------------------------------------------+
                     |               Chrome Extension (Gmail Integration)            |
                     +---------------------------------------------------------------+
```

---

# 📁 Project Structure

```
Email-Writer-Application/
│
├── email-writer-lb/                # Spring Boot Backend
│   ├── src/main/java/com/email/... # Controllers, Services, Models
│   ├── application.properties
│   └── pom.xml
│
├── email-writer-frontend/          # React UI
│   ├── src/App.jsx
│   ├── package.json
│   └── public/
│
└── email-writer-extension/         # Chrome Extension
    ├── manifest.json
    ├── content.js
    ├── popup.html
    ├── icons/
    └── content.css
```

---

# 🛠️ Tech Stack

### **Backend**

* Java 17
* Spring Boot 3.3.x
* WebFlux (WebClient)
* Lombok
* Maven

### **Frontend**

* React
* Material UI
* Axios

### **Chrome Extension**

* Manifest v3
* JavaScript
* CSS
* Gmail DOM Integration

---

# 🧩 Backend Setup (Spring Boot)

## 1️⃣ Navigate to backend folder

```bash
cd email-writer-lb
```

## 2️⃣ Add environment variables

Create a file:

### **application.properties**

```
spring.application.name=email-writer-lb
gemini.api.url=${GEMINI_API_URL}
gemini.api.key=${GEMINI_API_KEY}
```

## 3️⃣ Set Environment Variables

### Windows CMD:

```bash
set GEMINI_API_URL=https://generativelanguage.googleapis.com
set GEMINI_API_KEY=YOUR_API_KEY
```

### PowerShell:

```bash
$env:GEMINI_API_URL="https://generativelanguage.googleapis.com"
$env:GEMINI_API_KEY="YOUR_API_KEY"
```

## 4️⃣ Run the backend

```bash
mvn spring-boot:run
```

Backend runs at:

```
http://localhost:8080
```

---

# 🖥️ Frontend Setup (React)

## 1️⃣ Navigate

```bash
cd email-writer-frontend
```

## 2️⃣ Install dependencies

```bash
npm install
```

## 3️⃣ Start React app

```bash
npm start
```

Frontend URL:

```
http://localhost:3000
```

---

# 🧩 Chrome Extension Setup

## 1️⃣ Go to Chrome

Open:

```
chrome://extensions/
```

## 2️⃣ Enable **Developer Mode**

## 3️⃣ Click **Load Unpacked**

## 4️⃣ Select folder:

```
email-writer-extension/
```

## 5️⃣ Open Gmail → Compose Message

A button **“AI Reply”** will appear in the toolbar.

---

# 🔌 API Details

### **POST /api/email/generate**

Generate AI email reply.

#### 📤 Request Body

```json
{
  "emailContent": "Original email content here...",
  "tone": "professional"
}
```

#### 📥 Response

```
"Generated AI reply text..."
```

---

# 🌍 Environment Variables

| Name             | Description         |
| ---------------- | ------------------- |
| `GEMINI_API_URL` | Gemini API Base URL |
| `GEMINI_API_KEY` | Your API Key        |

Example:

```
GEMINI_API_URL=https://generativelanguage.googleapis.com
GEMINI_API_KEY=ABCD12345...
```

---

# ▶️ Running the Entire System

## Step 1 — Start backend

```bash
cd email-writer-lb
mvn spring-boot:run
```

## Step 2 — Start frontend

```bash
cd email-writer-frontend
npm start
```

## Step 3 — Load Chrome extension

Go to Chrome → `chrome://extensions/` → Load Unpacked

## Step 4 — Use the system

* Use frontend UI (localhost:3000)
* Or use Gmail extension button

---

# 📸 Screenshots (Optional)

Add screenshots here after deployment:

```
/screenshots
├── frontend-ui.png
├── gmail-extension.png
└── backend-response.png
```

---

# 🚀 Future Enhancements

* Add user authentication
* Save email history
* Deploy backend + frontend on cloud
* Add support for multiple languages
* Add customizable writing styles

---

# 📄 License

This project is licensed under the **MIT License**.

---
