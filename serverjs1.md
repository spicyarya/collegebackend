const express = require('express');
const cors = require('cors');
const path = require('path');
const app = express();

// --- MIDDLEWARE ---
app.use(cors());
app.use(express.json());
// Serves all your team's HTML files from the 'public' folder
app.use(express.static(path.join(__dirname, 'public')));

// --- DATABASE (In-Memory for now) ---
// Matches the data seen in your student-profile and attendance files
const students = [
    { 
        username: "CSE-2021-145", 
        password: "password123", 
        name: "Rajesh Kumar Singh",
        branch: "Computer Science Engineering",
        cgpa: 8.65,
        email: "rajesh.kumar@college.edu.in"
    }
];

// --- API ENDPOINTS ---

// 1. Login Endpoint
app.post('/api/login', (req, res) => {
    const { username, password } = req.body;
    const student = students.find(s => s.username === username && s.password === password);

    if (student) {
        res.json({ success: true, message: "Login successful!", studentName: student.name });
    } else {
        res.status(401).json({ success: false, message: "Invalid Roll Number or Password" });
    }
});

// 2. Profile Data Endpoint
app.get('/api/profile/:id', (req, res) => {
    const student = students.find(s => s.username === req.params.id);
    if (student) {
        res.json(student);
    } else {
        res.status(404).json({ message: "Student not found" });
    }
});

// --- START SERVER ---
const PORT = 3000;
app.listen(PORT, () => {
    console.log(`
    🚀 Backend Compiled Successfully!
    ----------------------------------
    Local Link: http://localhost:${PORT}/login.html
    Credentials: CSE-2021-145 / password123
    ----------------------------------
    `);
});
