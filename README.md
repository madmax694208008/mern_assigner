# MERN Assigner — README

Requirements: Node.js 16+, MongoDB

Backend setup:
1. cd backend
2. cp .env.example .env and fill MONGO_URI and JWT_SECRET
3. npm install
4. npm run dev
Backend runs on PORT (default 5000)

Create initial admin:
Use a short script or create user directly in Mongo shell:
Example script:
  node -e "require('dotenv').config(); const mongoose=require('mongoose'); const User=require('./src/models/User'); mongoose.connect(process.env.MONGO_URI).then(async ()=>{ const u= new User({email:'admin@example.com', password:'AdminPass123'}); await u.save(); console.log('Admin created'); process.exit();})"

Frontend setup:
1. cd frontend
2. npm install
3. set REACT_APP_API_URL=http://localhost:5000/api in .env or run dev server
4. npm start

How to use:
1. Login as admin (created earlier)
2. Add 5 agents using Add Agent form
3. Upload CSV file (must contain FirstName and Phone columns)
4. After upload, assignments are created and viewable on dashboard under each agent

Notes:
CSV support: example code parses only CSV. For XLSX/XLS add xlsx parsing.
Video: record a demo showing login, add agents, upload CSV, and viewing assigned lists.
