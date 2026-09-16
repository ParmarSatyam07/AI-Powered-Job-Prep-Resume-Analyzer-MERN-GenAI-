
# 🚀 Interview AI – Generative AI Full-Stack Preparation Platform

An intelligent, full-stack web application designed to help job seekers bridge skill gaps and crack technical interviews. Unlike traditional rule-based tools, this platform uses **Google Gemini AI** to analyze candidate resumes against targeted Job Descriptions (JD), evaluate skill gaps, generate tailored interview questions, provide a step-by-step preparation plan, and build ATS-friendly resumes.

---

## ✨ Key Features

- **🔒 Secure Authentication & Token Blacklisting**: JWT-based authentication stored in HTTP-only cookies with Bcrypt password hashing and custom MongoDB token blacklisting on logout for security.
- **📄 Resume & JD Parsing**: Extracts text from PDF resumes and processes target Job Descriptions alongside candidate self-descriptions.
- **🧠 AI-Powered Skill Gap Analysis**: Utilizes Google Gemini AI with structured Zod JSON schemas to output a match score (0-100%) and pinpoint critical skill gaps.
- **🎯 Tailored Technical & Behavioral Questions**: Generates targeted interview questions along with interviewer intentions and recommended answering strategies.
- **📅 Custom Preparation Roadmap**: Provides a day-wise roadmap detailing specific topics, focus areas, and tasks to prepare effectively.
- **📄 ATS Resume Builder & Export**: Dynamically generates tailored HTML resumes and converts them into downloadable PDFs using Puppeteer.
- **🎨 Modern React UI/UX**: Built with React, SCSS, React Router, and a layered state architecture (UI, Hooks, Context, Services) for performance.

---

## 🛠️ Tech Stack

### **Frontend**
- **Framework & Libraries**: React.js (Vite), React Router
- **Styling**: SCSS (Sass)
- **HTTP Client**: Axios with custom interceptors/instances
- **State Management**: React Context API & Custom Hooks

### **Backend**
- **Runtime & Server**: Node.js, Express.js
- **Database & ODM**: MongoDB Atlas, Mongoose ODM
- **Authentication**: JSON Web Tokens (JWT), Bcrypt.js, Cookie Parser
- **File & PDF Processing**: Multer, PDF-Parse, Puppeteer

### **AI Engineering**
- **AI Model**: Google Gemini AI (`@google/genai` - `gemini-2.5-flash`)
- **Schema Validation**: Zod & Zod-to-JSON-Schema for strict structured JSON outputs

---

## 📁 Project Architecture

The project follows a modular **4-Layer Frontend Architecture** and a clean **Controller-Service Backend Architecture**:

```
root/
├── backend/
│   ├── src/
│   │   ├── config/       # Database connections
│   │   ├── controllers/  # Route handlers (Auth, AI, Interview)
│   │   ├── middlewares/  # Auth protection & File uploaders
│   │   ├── models/       # Mongoose Schemas (User, Blacklist, Report)
│   │   ├── routes/       # Express route handlers
│   │   └── services/     # Gemini AI & Puppeteer services
│   └── server.js         # Entry point
│
└── frontend/
    ├── src/
    │   ├── assets/       # Styles & Static assets
    │   ├── features/     # Feature-based architecture (Auth, Interview)
    │   │   ├── components/
    │   │   ├── hooks/     # Custom hooks managing state & APIs
    │   │   ├── pages/     # Page views (Home, Login, Report)
    │   │   ├── services/  # API call layer
    │   │   └── context/   # React Context state layer
    │   └── app.routes.jsx # React Router configurations
```

---

## ⚙️ Installation & Setup Guide

### **Prerequisites**
- Node.js (v18 or higher)
- MongoDB Atlas Account
- Google AI Studio Gemini API Key

---

### **1. Clone the Repository**
```bash
git clone https://github.com/your-username/interview-ai.git
cd interview-ai
```

---

### **2. Backend Setup**
```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create .env file
touch .env
```

Add the following environment variables to `backend/.env`:
```env
PORT=3000
MONGO_URI=your_mongodb_atlas_connection_string
JWT_SECRET=your_jwt_secret_key
GOOGLE_GEMINI_API_KEY=your_gemini_api_key
```

Start the backend development server:
```bash
npm run dev
```

---

### **3. Frontend Setup**
Open a new terminal tab:
```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Start Vite dev server
npm run dev
```

The application will run at `http://localhost:5173`.

---

## 📸 Usage Flow

1. **Register/Login**: Create an account or sign in securely.
2. **Input Preparation Strategy**: Enter Target Job Description, Self Description, and Upload Resume (PDF).
3. **AI Strategy Generation**: Gemini AI processes input and constructs a customized candidate report.
4. **Review & Export**: View skill gap analysis, interview question guide, preparation roadmap, and download an ATS-friendly resume PDF.
```
