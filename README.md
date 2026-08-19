# 🚗 AutoAid — Smart Vehicle Maintenance & Assistance Platform

> **AI-powered vehicle assistance platform that simplifies vehicle maintenance, damage assessment, and mechanic discovery.**

AutoAid is a **MERN-stack vehicle maintenance and assistance platform** designed to help vehicle owners manage their vehicles, access maintenance services, locate nearby mechanics, and receive AI-powered assistance for vehicle damage assessment.

The platform combines **full-stack development, geolocation, real-time communication, and AI-based image analysis** to create a smarter and more convenient vehicle service experience.

---

## ✨ Features

### 👤 User Management

* 🔐 Secure user authentication
* 👤 User and Mechanic role-based access
* 🚘 Vehicle registration and management
* 📊 Personalized user dashboard
* 📋 Vehicle service and maintenance information

### 🛡️ Vehicle Protection Plans

Users can choose a subscription based on their vehicle type.

#### 🏍️ Two-Wheeler Plans

| Plan     |      Price |
| -------- | ---------: |
| Basic    |  ₹99/month |
| Standard | ₹149/month |
| Premium  | ₹199/month |

#### 🚘 Four-Wheeler Plans

| Plan     |      Price |
| -------- | ---------: |
| Basic    | ₹299/month |
| Standard | ₹499/month |
| Premium  | ₹999/month |

---

## 🤖 AI-Powered Damage Assessment

AutoAid uses **Gemini-based image analysis** to evaluate vehicle damage submitted by users.

The AI analyzes:

* 🚗 Vehicle type
* 🎨 Vehicle color
* 🔍 Visible vehicle parts
* 💥 Detected damage
* 🧩 Damaged parts
* ⚠️ Damage severity
* 🖼️ Image consistency
* 📝 Observations

The system can also compare the **user-provided damage description with the uploaded image** to determine whether the claim is consistent.

### 🔎 Claim Verification

The AI evaluates factors such as:

```text
Image
  ↓
Vehicle Detection
  ↓
Damage Detection
  ↓
Damaged Part Identification
  ↓
Severity Assessment
  ↓
Description ↔ Image Comparison
  ↓
Consistency / Fraud Indicators
```

This provides an additional layer of verification before connecting the user with a mechanic.

---

## 📍 Nearby Mechanic Discovery

AutoAid helps users find nearby mechanics using **location-based services**.

Users can:

* 📍 Share their location
* 🔎 Find nearby mechanic hubs
* 🗺️ View mechanics on a map
* 🧑‍🔧 Select an appropriate mechanic
* 🚘 Get assistance for vehicle repairs

---

## 💬 User–Mechanic Communication

The platform provides communication between users and mechanics to simplify the repair process.

### User

```text
Report Vehicle Issue
        ↓
Upload Damage Image
        ↓
AI Assessment
        ↓
Find Nearby Mechanic
        ↓
Connect With Mechanic
```

### Mechanic

```text
Receive Request
      ↓
Review Vehicle Information
      ↓
Review Damage Details
      ↓
Communicate With User
      ↓
Provide Assistance
```

---

## 🏗️ System Architecture

```text
                    ┌─────────────────────┐
                    │      Frontend       │
                    │   React + Vite      │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      Backend        │
                    │ Node.js + Express   │
                    └──────┬───────┬──────┘
                           │       │
              ┌────────────┘       └─────────────┐
              ▼                                  ▼
     ┌─────────────────┐                ┌─────────────────┐
     │    MongoDB      │                │   Gemini API    │
     │  Application DB │                │ AI Assessment   │
     └─────────────────┘                └─────────────────┘
              │
              ▼
     ┌─────────────────┐
     │ Location / Maps │
     │    Services     │
     └─────────────────┘
```

---

## 🛠️ Tech Stack

### Frontend

* ⚛️ React.js
* ⚡ Vite
* 🎨 Tailwind CSS
* 🎞️ Framer Motion
* 🧩 Lucide React

### Backend

* 🟢 Node.js
* 🚂 Express.js
* 🍃 MongoDB
* 🔗 Mongoose

### AI

* 🤖 Google Gemini API
* 🖼️ AI-powered image analysis
* 🔍 Vehicle & damage detection
* 🧠 Description-image consistency analysis

### APIs & Services

* 🗺️ Maps / Geolocation APIs
* 🔐 Authentication
* 💬 User–Mechanic communication

### Development & Deployment

* 🐙 Git & GitHub
* ☁️ Render
* 🌐 Netlify
* 📦 npm

---

## 📂 Project Structure

```text
AutoAid/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   └── ...
│   ├── public/
│   └── package.json
│
├── backend/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── services/
│   ├── utils/
│   └── server.js
│
├── .gitignore
├── README.md
└── package.json
```

> Update the structure above if your current repository uses different folder names.

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd AutoAid
```

### 2. Install dependencies

For the backend:

```bash
cd backend
npm install
```

For the frontend:

```bash
cd ../frontend
npm install
```

### 3. Configure environment variables

Create a `.env` file inside the backend directory:

```env
PORT=5000

MONGO_URI=your_mongodb_connection_string

GEMINI_API_KEY=your_gemini_api_key

JWT_SECRET=your_jwt_secret

MAPS_API_KEY=your_maps_api_key
```

> Never commit `.env` files or API keys to GitHub.

### 4. Start the backend

```bash
cd backend
npm run dev
```

### 5. Start the frontend

Open another terminal:

```bash
cd frontend
npm run dev
```

The application will then be available at the local Vite development URL.

---

## 🔄 Core Workflow

```text
                 ┌───────────────┐
                 │     User      │
                 └───────┬───────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Register/Login  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Register Vehicle│
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Select Plan     │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Report Damage   │
                └────────┬────────┘
                         │
                    Upload Image
                         │
                         ▼
                ┌─────────────────┐
                │   Gemini AI     │
                │ Damage Analysis │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Find Mechanics  │
                │    Nearby       │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Connect & Get   │
                │    Assistance   │
                └─────────────────┘
```

---

## 🔐 Security Considerations

AutoAid incorporates several security practices:

* 🔑 Environment-based API key management
* 🔐 Authentication and authorization
* 👥 Role-based access control
* 🛡️ Protected backend routes
* 🚫 Sensitive credentials excluded from version control
* 🔒 Server-side validation of user requests

---

## 🎯 Why AutoAid?

Traditional vehicle repair workflows can involve:

* Difficulty finding reliable nearby mechanics
* Lack of structured vehicle maintenance information
* Unclear damage assessment
* Time-consuming communication
* Potential inconsistencies in reported damage

AutoAid brings these processes together into a **single digital platform** with AI-assisted assessment and location-aware mechanic discovery.

---

## 🚀 Future Enhancements

* 💳 Integrated online subscription payments
* 📅 Mechanic appointment scheduling
* ⭐ Mechanic ratings and reviews
* 🔔 Automated maintenance reminders
* 📱 Progressive Web App / mobile application
* 🧾 Digital repair invoices
* 📊 Vehicle maintenance analytics
* 🤖 Improved AI-based repair cost estimation
* 🛠️ Predictive maintenance recommendations
* 🔔 Real-time notifications
* 🗺️ Route navigation to selected mechanics

---

## 👩‍💻 Project Highlights

**AutoAid demonstrates practical experience with:**

* Full-stack MERN development
* REST API development
* MongoDB data modeling
* Authentication & authorization
* AI API integration
* Multimodal AI / image analysis
* Geolocation-based services
* Role-based application architecture
* Responsive UI development
* Cloud deployment

---

## 📸 Screenshots

Add screenshots of the major interfaces here:

```text
Landing Page
Dashboard
Vehicle Registration
Subscription Plans
Damage Assessment
Mechanic Map
User–Mechanic Chat
```

Example:

```markdown
![AutoAid Dashboard](./screenshots/dashboard.png)
```

---

## 👥 Team

**AutoAid** was developed as a collaborative full-stack project.

### Contributors

* **Suhana Syed & Neha Sumaya** — Backend Development,AI Integration
* **Priya Mythili & Gowtham Parise** - Frontend Development
* 

---

## 📜 License

This project is developed for educational, demonstration, and portfolio purposes.

---

## ⭐ Support

If you find this project interesting, consider giving the repository a ⭐!

