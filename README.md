# Interview_prepration_app

A full-stack web application that helps job seekers prepare smarter using Google's Gemini. Users can analyze their resume against a specific job description, get an ATS compatibility resume score, receive interview questions,
follow a personalized skill-gap roadmap, and download an updated resume.

*************************** Features *******************************

### Authentication System

- Email and password based registration and login, with passwords securely hashed using bcrypt.
- Token-based session management using JWT stored in an http Only cookie.
- Token blacklisting on logout.

### AI Resume Analyzer

- Users submit their resume, a self-description, and the target job description.
- On clicking Generate Report, the application sends this data to the Google Gemini API for analysis.
- The system returns an ATS compatibility score on a 1–100 scale, reflecting how well the resume and self-description align with the given job description.
- Along with the score, the report includes 10–15 technical and behavioral interview questions according to the job description, each paired with a suggested answer and an explanation of the interviewer's intent behind asking it.
- A 7-day personalized roadmap is generated to help the user close identified skill gaps before their interview.

### Resume Builder

- Works as an extension of the analysis flow: after generating the report, users can download an updated version of their resume.
- The downloaded resume is tailored and restructured according to the specific job description provided.

### ATS Score

- Calculated as part of the same Generate Report flow using the Gemini API.
- Scored on a 1–100 scale based on how well the resume and self-description match the provided job description.
- Displayed alongside the generated interview questions and roadmap report.

******************** Tech Stack ****************************

**Frontend: React (Vite), SCSS  
**Backend: Node.js, Express  
**Database: MongoDB  
**AI Integration: Google Gemini API (Google AI Studio)  
**Authentication:  Email/Password (JWT + bcrypt) 

*************************** Working  ********************************

1. **Sign up or log in : using email/password or Google.
2. **Submit your details : paste your resume, write a short self-description, and paste the job description you're targeting.
3. **Click Generate Report :  the Gemini API analyzes all three inputs together.
4. **Review your results:
   i. ATS Score (1–100)
   ii. 10–15 tailored technical and behavioral interview questions with answers
   iii. A 7-day roadmap to close skill gaps
5. **Download your updated resume, rewritten to better match the job description.

## Getting Started

*************************** Prerequisites **********************************

- Node.js installed
- MongoDB instance (Atlas)
- Google Gemini API key (from Google AI Studio)

### Environment Variables

**Backend `.env`**
```
PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
```

**Frontend `.env`**
```
VITE_API_URL=http://localhost:3000
```

### Installation

```bash
# Clone the repository
git clone https://github.com/Saifulislam8412sv/Interview_Prepration_App.git

# Install backend dependencies
cd Backend
npm install

# Install frontend dependencies
cd ../Frontend
npm install
```

### Running Locally

```bash
# Start backend
cd Backend
npm run dev

# Start frontend (in a separate terminal)
cd Frontend
npm run dev
```
