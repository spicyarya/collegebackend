const express = require('express');
const cors = require('cors');
const path = require('path');
const app = express();

// --- MIDDLEWARE ---
app.use(cors());
app.use(express.json());
app.use(express.static(path.join(__dirname, 'public')));

// --- UPDATED DATA ---
const students = [
    { 
        username: "rajesh kumar_01", // Updated username
        password: "password123",
        name: "Rajesh Kumar Singh",
        branch: "Computer Science Engineering",
        cgpa: 8.65,
        email: "rajesh.kumar@college.edu.in"
    }
];

// --- LOGIN API ---
app.post('/api/login', (req, res) => {
    const { username, password } = req.body;
    const student = students.find(s => s.username === username && s.password === password);

    if (student) {
        res.json({ success: true, message: "Login successful!", studentName: student.name });
    } else {
        res.status(401).json({ success: false, message: "Invalid username or password" });
    }
});

const PORT = 3000;
app.listen(PORT, () => {
    console.log(`🚀 Server updated! Use username: rajesh kumar_01`);
});
