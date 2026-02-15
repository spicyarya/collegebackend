<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Profile - College Portal</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.2);
        }
        .header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 3px solid #667eea;
        }
        .profile-banner {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 40px;
            border-radius: 15px;
            color: white;
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 30px;
        }
        .profile-pic {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            border: 5px solid rgba(255,255,255,0.3);
        }
        .profile-info {
            flex: 1;
        }
        .profile-name {
            font-size: 32px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        .profile-details {
            font-size: 16px;
            opacity: 0.9;
        }
        .section {
            margin-bottom: 30px;
        }
        .section-title {
            font-size: 22px;
            color: #667eea;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #e0e0e0;
        }
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        .info-box {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
        }
        .info-label {
            font-size: 12px;
            color: #666;
            text-transform: uppercase;
            margin-bottom: 8px;
            font-weight: bold;
        }
        .info-value {
            font-size: 16px;
            color: #333;
            font-weight: 500;
        }
        .back-btn {
            display: inline-block;
            padding: 12px 30px;
            background: #667eea;
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-weight: bold;
            margin-top: 20px;
            transition: all 0.3s;
        }
        .back-btn:hover {
            background: #764ba2;
            transform: translateY(-2px);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>👤 Student Profile</h1>
        </div>

        <div class="profile-banner">
            <div class="profile-pic">👨‍🎓</div>
            <div class="profile-info">
                <div class="profile-name">Rajesh Kumar</div>
                <div class="profile-details">CSE-2021-145 | Computer Science Engineering</div>
                <div class="profile-details">Batch: 2021-2025 | Current Semester: V</div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">📋 Personal Information</div>
            <div class="info-grid">
                <div class="info-box">
                    <div class="info-label">Full Name</div>
                    <div class="info-value">Rajesh Kumar Singh</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Date of Birth</div>
                    <div class="info-value">15th August 2003</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Gender</div>
                    <div class="info-value">Male</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Blood Group</div>
                    <div class="info-value">B+</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Email ID</div>
                    <div class="info-value">rajesh.kumar@college.edu.in</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Mobile Number</div>
                    <div class="info-value">+91 98765 43210</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Aadhar Number</div>
                    <div class="info-value">XXXX-XXXX-3456</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Category</div>
                    <div class="info-value">General</div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">🎓 Academic Details</div>
            <div class="info-grid">
                <div class="info-box">
                    <div class="info-label">Roll Number</div>
                    <div class="info-value">CSE-2021-145</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Registration Number</div>
                    <div class="info-value">202100145CS</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Branch</div>
                    <div class="info-value">Computer Science Engineering</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Section</div>
                    <div class="info-value">Section A</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Batch</div>
                    <div class="info-value">2021-2025</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Current Semester</div>
                    <div class="info-value">Semester V</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Current CGPA</div>
                    <div class="info-value">8.65 / 10.0</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Academic Status</div>
                    <div class="info-value">Regular</div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">📍 Address Details</div>
            <div class="info-grid">
                <div class="info-box">
                    <div class="info-label">Permanent Address</div>
                    <div class="info-value">House No. 234, Sector 12<br>Dwarka, New Delhi - 110075<br>India</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Current Address</div>
                    <div class="info-value">Room 305, Boys Hostel Block C<br>College Campus<br>Meerut, UP - 250001</div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">👨‍👩‍👦 Parent/Guardian Details</div>
            <div class="info-grid">
                <div class="info-box">
                    <div class="info-label">Father's Name</div>
                    <div class="info-value">Mr. Vijay Kumar Singh</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Father's Occupation</div>
                    <div class="info-value">Government Employee</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Father's Mobile</div>
                    <div class="info-value">+91 98765 12345</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Mother's Name</div>
                    <div class="info-value">Mrs. Sunita Singh</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Mother's Occupation</div>
                    <div class="info-value">Homemaker</div>
                </div>
                <div class="info-box">
                    <div class="info-label">Guardian Contact</div>
                    <div class="info-value">+91 98765 67890</div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">📚 Previous Education</div>
            <div class="info-grid">
                <div class="info-box">
                    <div class="info-label">12th (Senior Secondary)</div>
                    <div class="info-value">Delhi Public School<br>CBSE Board - 2021<br>Percentage: 92.5%</div>
                </div>
                <div class="info-box">
                    <div class="info-label">10th (Secondary)</div>
                    <div class="info-value">Delhi Public School<br>CBSE Board - 2019<br>CGPA: 9.4 / 10.0</div>
                </div>
            </div>
        </div>

        <div style="text-align: center;">
            <a href="javascript:window.close();" class="back-btn">← Back to Portal</a>
        </div>
    </div>
</body>
</html>
