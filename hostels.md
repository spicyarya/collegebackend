<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hostel Information - College Portal</title>
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
        .allocation-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 30px;
        }
        .room-details {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        .detail-box {
            background: rgba(255,255,255,0.2);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
        }
        .detail-label {
            font-size: 14px;
            opacity: 0.9;
            margin-bottom: 8px;
        }
        .detail-value {
            font-size: 20px;
            font-weight: bold;
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
        .facilities-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        .facility-card {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
            transition: all 0.3s;
        }
        .facility-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .facility-icon {
            font-size: 32px;
            margin-bottom: 10px;
        }
        .facility-name {
            font-weight: bold;
            color: #333;
            margin-bottom: 8px;
        }
        .facility-desc {
            font-size: 14px;
            color: #666;
        }
        .roommates-section {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
        }
        .roommate-card {
            background: white;
            padding: 20px;
            border-radius: 10px;
            margin: 10px 0;
            display: flex;
            align-items: center;
            gap: 20px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        .roommate-icon {
            width: 60px;
            height: 60px;
            background: #667eea;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            color: white;
        }
        .roommate-info {
            flex: 1;
        }
        .roommate-name {
            font-size: 18px;
            font-weight: bold;
            color: #333;
            margin-bottom: 5px;
        }
        .roommate-details {
            font-size: 14px;
            color: #666;
        }
        .rules-list {
            background: #fff3cd;
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #FFC107;
        }
        .rules-list ul {
            margin-left: 20px;
            color: #666;
            line-height: 2;
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
            <h1>🏠 Hostel Information</h1>
            <p>Student Accommodation Details</p>
        </div>

        <div class="allocation-card">
            <h2 style="margin-bottom: 10px;">Your Room Allocation</h2>
            <p style="opacity: 0.9; margin-bottom: 20px;">Academic Year 2024-25</p>
            <div class="room-details">
                <div class="detail-box">
                    <div class="detail-label">Hostel Block</div>
                    <div class="detail-value">Block C</div>
                </div>
                <div class="detail-box">
                    <div class="detail-label">Room Number</div>
                    <div class="detail-value">305</div>
                </div>
                <div class="detail-box">
                    <div class="detail-label">Floor</div>
                    <div class="detail-value">3rd Floor</div>
                </div>
                <div class="detail-box">
                    <div class="detail-label">Room Type</div>
                    <div class="detail-value">Triple Sharing</div>
                </div>
                <div class="detail-box">
                    <div class="detail-label">Warden</div>
                    <div class="detail-value">Dr. P.K. Mehta</div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">👥 Roommates</div>
            <div class="roommates-section">
                <div class="roommate-card">
                    <div class="roommate-icon">👨‍🎓</div>
                    <div class="roommate-info">
                        <div class="roommate-name">Amit Sharma</div>
                        <div class="roommate-details">Roll No: CSE-2021-142 | Branch: Computer Science</div>
                        <div class="roommate-details">Contact: +91 98765 11111</div>
                    </div>
                </div>
                <div class="roommate-card">
                    <div class="roommate-icon">👨‍🎓</div>
                    <div class="roommate-info">
                        <div class="roommate-name">Rahul Verma</div>
                        <div class="roommate-details">Roll No: CSE-2021-148 | Branch: Computer Science</div>
                        <div class="roommate-details">Contact: +91 98765 22222</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">🏢 Hostel Facilities</div>
            <div class="facilities-grid">
                <div class="facility-card">
                    <div class="facility-icon">🛏️</div>
                    <div class="facility-name">Furnished Rooms</div>
                    <div class="facility-desc">Bed, study table, chair, wardrobe, and mattress provided</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">🍽️</div>
                    <div class="facility-name">Mess Facility</div>
                    <div class="facility-desc">4 meals daily - Breakfast, Lunch, Evening Snacks, Dinner</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">📶</div>
                    <div class="facility-name">WiFi Internet</div>
                    <div class="facility-desc">24x7 high-speed internet connectivity in all rooms</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">🔒</div>
                    <div class="facility-name">24/7 Security</div>
                    <div class="facility-desc">CCTV surveillance and security guards on duty</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">🧺</div>
                    <div class="facility-name">Laundry Service</div>
                    <div class="facility-desc">Washing machines and drying area available</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">📚</div>
                    <div class="facility-name">Reading Room</div>
                    <div class="facility-desc">Quiet study space with AC and comfortable seating</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">🏋️</div>
                    <div class="facility-name">Gym</div>
                    <div class="facility-desc">Well-equipped fitness center with modern equipment</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">🎮</div>
                    <div class="facility-name">Recreation Room</div>
                    <div class="facility-desc">Table tennis, carrom, chess, and indoor games</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">☕</div>
                    <div class="facility-name">Cafeteria</div>
                    <div class="facility-desc">Snacks, beverages, and light meals available</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">🏥</div>
                    <div class="facility-name">Medical Room</div>
                    <div class="facility-desc">First aid and basic medical facilities with nurse on duty</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">🚿</div>
                    <div class="facility-name">Hot Water</div>
                    <div class="facility-desc">24x7 hot water supply in all bathrooms</div>
                </div>
                <div class="facility-card">
                    <div class="facility-icon">⚡</div>
                    <div class="facility-name">Power Backup</div>
                    <div class="facility-desc">Generator backup for uninterrupted power supply</div>
                </div>
            </div>
        </div>

        <div class="section">
            <div class="section-title">💰 Hostel Fee Structure</div>
            <table style="width: 100%; border-collapse: collapse;">
                <thead>
                    <tr>
                        <th style="background: #667eea; color: white; padding: 15px; text-align: left;">Fee Type</th>
                        <th style="background: #667eea; color: white; padding: 15px; text-align: right;">Amount (Per Semester)</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0;">Room Rent</td>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0; text-align: right; font-weight: bold;">₹25,000</td>
                    </tr>
                    <tr>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0;">Mess Charges</td>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0; text-align: right; font-weight: bold;">₹20,000</td>
                    </tr>
                    <tr>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0;">Electricity & Water</td>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0; text-align: right; font-weight: bold;">₹3,000</td>
                    </tr>
                    <tr>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0;">Maintenance</td>
                        <td style="padding: 15px; border-bottom: 1px solid #e0e0e0; text-align: right; font-weight: bold;">₹2,000</td>
                    </tr>
                    <tr>
                        <td style="padding: 15px; font-weight: bold; background: #f8f9fa;">Total</td>
                        <td style="padding: 15px; text-align: right; font-weight: bold; background: #f8f9fa; color: #667eea; font-size: 18px;">₹50,000</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div class="section">
            <div class="section-title">⚠️ Hostel Rules & Regulations</div>
            <div class="rules-list">
                <ul>
                    <li><strong>In-Time:</strong> 9:00 PM on weekdays, 10:00 PM on weekends</li>
                    <li><strong>Out-Pass:</strong> Required for staying out overnight</li>
                    <li><strong>Visitors:</strong> Allowed in common areas only, not in rooms</li>
                    <li><strong>Cleanliness:</strong> Keep rooms and common areas clean</li>
                    <li><strong>Noise Levels:</strong> Maintain silence after 10:00 PM</li>
                    <li><strong>Alcohol/Drugs:</strong> Strictly prohibited in hostel premises</li>
                    <li><strong>Ragging:</strong> Zero tolerance policy, strict action will be taken</li>
                    <li><strong>Damage:</strong> Any damage to hostel property will be charged</li>
                    <li><strong>ID Card:</strong> Must carry college ID at all times</li>
                    <li><strong>Leave:</strong> Inform warden before leaving hostel for home</li>
                </ul>
            </div>
        </div>

        <div class="section">
            <div class="section-title">📞 Contact Information</div>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px;">
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px;">
                    <strong style="color: #667eea;">Chief Warden</strong><br>
                    <span style="color: #666;">Dr. R.K. Patel</span><br>
                    <span style="color: #666;">📞 +91 98765 00001</span><br>
                    <span style="color: #666;">✉️ warden@college.edu.in</span>
                </div>
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px;">
                    <strong style="color: #667eea;">Block C Warden</strong><br>
                    <span style="color: #666;">Dr. P.K. Mehta</span><br>
                    <span style="color: #666;">📞 +91 98765 00002</span><br>
                    <span style="color: #666;">✉️ blockc@college.edu.in</span>
                </div>
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px;">
                    <strong style="color: #667eea;">Hostel Office</strong><br>
                    <span style="color: #666;">Timings: 9 AM - 5 PM</span><br>
                    <span style="color: #666;">📞 +91 98765 00003</span><br>
                    <span style="color: #666;">✉️ hostel@college.edu.in</span>
                </div>
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px;">
                    <strong style="color: #667eea;">Emergency</strong><br>
                    <span style="color: #666;">Security: +91 98765 00911</span><br>
                    <span style="color: #666;">Medical: +91 98765 00108</span><br>
                    <span style="color: #666;">Available 24x7</span>
                </div>
            </div>
        </div>

        <div style="text-align: center;">
            <a href="javascript:window.close();" class="back-btn">← Back to Portal</a>
        </div>
    </div>
</body>
</html>
