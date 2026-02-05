# Design Document
## Multi-Language Code Translator with Learning Mode

## 1. System Architecture Overview
The system follows a **three-layer architecture**:
- Frontend Layer
- Backend Layer
- AI Processing Layer

The architecture is designed to support scalability, modularity, and clear separation of concerns.

---

## 2. High-Level Architecture

User → Frontend (UI) → Backend REST API → Amazon Bedrock → Backend → Frontend → User

---

## 3. Component Design

### 3.1 Frontend Layer
- Built using React.js.
- Includes a code editor (Monaco Editor).
- Handles user interactions such as language selection and code input.
- Displays translated code and explanations.

### 3.2 Backend Layer
- Implemented using Node.js with Express.js.
- Exposes REST APIs for handling translation requests.
- Communicates with Amazon Bedrock for AI processing.
- Formats AI responses before sending them to the frontend.

### 3.3 AI Processing Layer
- Powered by **Amazon Bedrock**.
- Uses foundation models for:
  - Code translation
  - Explanation generation
  - Conceptual comparison
- No model training is performed.

---

## 4. Process Flow

1. User selects source and target languages on the frontend.
2. User pastes source code into the editor.
3. Frontend sends request to backend REST API.
4. Backend forwards request to Amazon Bedrock.
5. Amazon Bedrock processes the request and generates:
   - Translated code
   - Line-by-line explanation
   - Conceptual differences
6. Backend sends structured response to frontend.
7. User reviews output and learns from explanations.

---

## 5. Technology Stack

### Frontend
- React.js
- Monaco Editor
- HTML, CSS, JavaScript

### Backend
- Node.js
- Express.js (REST API)

### AI Services
- Amazon Bedrock (Foundation Models)

### Hosting
- Frontend: Netlify / Vercel
- Backend: AWS Lambda or cloud server

---

## 6. Design Principles
- Simplicity and clarity for learners
- Modular and scalable architecture
- AI used as a learning assistant, not a replacement for understanding

---

## 7. Future Enhancements
- Personalized learning paths
- User progress tracking
- Support for additional programming languages
