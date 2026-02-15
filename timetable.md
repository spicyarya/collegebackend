<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Timetable - College Portal</title>
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
            max-width: 1400px;
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
        .header h1 {
            color: #333;
            font-size: 32px;
            margin-bottom: 10px;
        }
        .info-bar {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 30px;
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        .timetable-wrapper {
            overflow-x: auto;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 900px;
        }
        th {
            background: #667eea;
            color: white;
            padding: 15px 10px;
            text-align: center;
            font-weight: bold;
            position: sticky;
            top: 0;
        }
        td {
            padding: 15px 10px;
            border: 2px solid #e0e0e0;
            text-align: center;
            vertical-align: top;
        }
        .time-slot {
            font-weight: bold;
            background: #f8f9fa;
            color: #667eea;
        }
        .class-cell {
            background: white;
            transition: all 0.3s;
            cursor: pointer;
        }
        .class-cell:hover {
            transform: scale(1.02);
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
        }
        .subject-name {
            font-weight: bold;
            color: #333;
            margin-bottom: 5px;
            font-size: 14px;
        }
        .subject-code {
            color: #666;
            font-size: 12px;
            margin-bottom: 5px;
        }
        .teacher-name {
            color: #667eea;
            font-size: 12px;
            margin-bottom: 3px;
        }
        .room-number {
            background: #667eea;
            color: white;
            padding: 3px 8px;
            border-radius: 5px;
            font-size: 11px;
            display: inline-block;
            margin-top: 5px;
        }
        .break-cell {
            background: linear-gradient(135deg, #FFD700, #FFA500);
            color: white;
            font-weight: bold;
            font-size: 16px;
        }
        .lunch-cell {
            background: linear-gradient(135deg, #4CAF50, #45a049);
            color: white;
            font-weight: bold;
            font-size: 16px;
        }
        .lab-cell {
            background: linear-gradient(135deg, #FF6B6B, #FF5252);
        }
        .lecture-cell {
            background: linear-gradient(135deg, #4ECDC4, #44A08D);
        }
        .tutorial-cell {
            background: linear-gradient(135deg, #FFE66D, #FFCA28);
        }
        .legend {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        .legend-item {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .legend-color {
            width: 30px;
            height: 20px;
            border-radius: 5px;
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
            <h1>📅 Class Timetable</h1>
            <p>Semester V | Section A | Academic Year 2024-25</p>
        </div>

        <div class="info-bar">
            <div>
                <strong style="color: #667eea;">Student:</strong> Rajesh Kumar
            </div>
            <div>
                <strong style="color: #667eea;">Roll No:</strong> CSE-2021-145
            </div>
            <div>
                <strong style="color: #667eea;">Branch:</strong> Computer Science Engineering
            </div>
        </div>

        <div class="legend">
            <div class="legend-item">
                <div class="legend-color lecture-cell"></div>
                <span>Lecture</span>
            </div>
            <div class="legend-item">
                <div class="legend-color lab-cell"></div>
                <span>Lab</span>
            </div>
            <div class="legend-item">
                <div class="legend-color tutorial-cell"></div>
                <span>Tutorial</span>
            </div>
            <div class="legend-item">
                <div class="legend-color" style="background: linear-gradient(135deg, #FFD700, #FFA500);"></div>
                <span>Break</span>
            </div>
            <div class="legend-item">
                <div class="legend-color" style="background: linear-gradient(135deg, #4CAF50, #45a049);"></div>
                <span>Lunch</span>
            </div>
        </div>

        <div class="timetable-wrapper">
            <table>
                <thead>
                    <tr>
                        <th style="width: 120px;">Time</th>
                        <th>Monday</th>
                        <th>Tuesday</th>
                        <th>Wednesday</th>
                        <th>Thursday</th>
                        <th>Friday</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- 9:00 - 9:50 -->
                    <tr>
                        <td class="time-slot">9:00 AM<br>9:50 AM</td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Artificial Intelligence</div>
                            <div class="subject-code">CS301</div>
                            <div class="teacher-name">Dr. R.K. Sharma</div>
                            <div class="room-number">Room 301</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Machine Learning</div>
                            <div class="subject-code">CS302</div>
                            <div class="teacher-name">Prof. A. Gupta</div>
                            <div class="room-number">Room 302</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Cloud Computing</div>
                            <div class="subject-code">CS303</div>
                            <div class="teacher-name">Dr. S. Verma</div>
                            <div class="room-number">Room 303</div>
                        </td>
                        <td class="class-cell tutorial-cell">
                            <div class="subject-name">AI Tutorial</div>
                            <div class="subject-code">CS301-T</div>
                            <div class="teacher-name">Dr. R.K. Sharma</div>
                            <div class="room-number">Room 205</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Compiler Design</div>
                            <div class="subject-code">CS304</div>
                            <div class="teacher-name">Prof. M. Patel</div>
                            <div class="room-number">Room 304</div>
                        </td>
                    </tr>

                    <!-- 10:00 - 10:50 -->
                    <tr>
                        <td class="time-slot">10:00 AM<br>10:50 AM</td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Machine Learning</div>
                            <div class="subject-code">CS302</div>
                            <div class="teacher-name">Prof. A. Gupta</div>
                            <div class="room-number">Room 302</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Information Security</div>
                            <div class="subject-code">CS305</div>
                            <div class="teacher-name">Dr. K. Malhotra</div>
                            <div class="room-number">Room 305</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Artificial Intelligence</div>
                            <div class="subject-code">CS301</div>
                            <div class="teacher-name">Dr. R.K. Sharma</div>
                            <div class="room-number">Room 301</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Cloud Computing</div>
                            <div class="subject-code">CS303</div>
                            <div class="teacher-name">Dr. S. Verma</div>
                            <div class="room-number">Room 303</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Information Security</div>
                            <div class="subject-code">CS305</div>
                            <div class="teacher-name">Dr. K. Malhotra</div>
                            <div class="room-number">Room 305</div>
                        </td>
                    </tr>

                    <!-- 11:00 - 11:20 BREAK -->
                    <tr>
                        <td class="time-slot">11:00 AM<br>11:20 AM</td>
                        <td colspan="5" class="break-cell">☕ SHORT BREAK</td>
                    </tr>

                    <!-- 11:20 - 12:10 -->
                    <tr>
                        <td class="time-slot">11:20 AM<br>12:10 PM</td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Compiler Design</div>
                            <div class="subject-code">CS304</div>
                            <div class="teacher-name">Prof. M. Patel</div>
                            <div class="room-number">Room 304</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Artificial Intelligence</div>
                            <div class="subject-code">CS301</div>
                            <div class="teacher-name">Dr. R.K. Sharma</div>
                            <div class="room-number">Room 301</div>
                        </td>
                        <td class="class-cell tutorial-cell">
                            <div class="subject-name">ML Tutorial</div>
                            <div class="subject-code">CS302-T</div>
                            <div class="teacher-name">Prof. A. Gupta</div>
                            <div class="room-number">Room 206</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Machine Learning</div>
                            <div class="subject-code">CS302</div>
                            <div class="teacher-name">Prof. A. Gupta</div>
                            <div class="room-number">Room 302</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Entrepreneurship</div>
                            <div class="subject-code">HS301</div>
                            <div class="teacher-name">Prof. N. Singh</div>
                            <div class="room-number">Room 401</div>
                        </td>
                    </tr>

                    <!-- 12:20 - 1:10 -->
                    <tr>
                        <td class="time-slot">12:20 PM<br>1:10 PM</td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Information Security</div>
                            <div class="subject-code">CS305</div>
                            <div class="teacher-name">Dr. K. Malhotra</div>
                            <div class="room-number">Room 305</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Cloud Computing</div>
                            <div class="subject-code">CS303</div>
                            <div class="teacher-name">Dr. S. Verma</div>
                            <div class="room-number">Room 303</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Compiler Design</div>
                            <div class="subject-code">CS304</div>
                            <div class="teacher-name">Prof. M. Patel</div>
                            <div class="room-number">Room 304</div>
                        </td>
                        <td class="class-cell lecture-cell">
                            <div class="subject-name">Information Security</div>
                            <div class="subject-code">CS305</div>
                            <div class="teacher-name">Dr. K. Malhotra</div>
                            <div class="room-number">Room 305</div>
                        </td>
                        <td class="class-cell tutorial-cell">
                            <div class="subject-name">Cloud Tutorial</div>
                            <div class="subject-code">CS303-T</div>
                            <div class="teacher-name">Dr. S. Verma</div>
                            <div class="room-number">Room 207</div>
                        </td>
                    </tr>

                    <!-- 1:10 - 2:00 LUNCH -->
                    <tr>
                        <td class="time-slot">1:10 PM<br>2:00 PM</td>
                        <td colspan="5" class="lunch-cell">🍽️ LUNCH BREAK</td>
                    </tr>

                    <!-- 2:00 - 4:50 -->
                    <tr>
                        <td class="time-slot">2:00 PM<br>4:50 PM</td>
                        <td class="class-cell lab-cell">
                            <div class="subject-name" style="color: white;">AI Lab</div>
                            <div class="subject-code" style="color: white;">CS301-L</div>
                            <div class="teacher-name" style="color: white;">Dr. R.K. Sharma</div>
                            <div class="room-number" style="background: white; color: #FF5252;">Lab 1</div>
                        </td>
                        <td class="class-cell lab-cell">
                            <div class="subject-name" style="color: white;">ML Lab</div>
                            <div class="subject-code" style="color: white;">CS302-L</div>
                            <div class="teacher-name" style="color: white;">Prof. A. Gupta</div>
                            <div class="room-number" style="background: white; color: #FF5252;">Lab 2</div>
                        </td>
                        <td class="class-cell lab-cell">
                            <div class="subject-name" style="color: white;">Cloud Lab</div>
                            <div class="subject-code" style="color: white;">CS303-L</div>
                            <div class="teacher-name" style="color: white;">Dr. S. Verma</div>
                            <div class="room-number" style="background: white; color: #FF5252;">Lab 3</div>
                        </td>
                        <td class="class-cell lab-cell">
                            <div class="subject-name" style="color: white;">Compiler Lab</div>
                            <div class="subject-code" style="color: white;">CS304-L</div>
                            <div class="teacher-name" style="color: white;">Prof. M. Patel</div>
                            <div class="room-number" style="background: white; color: #FF5252;">Lab 4</div>
                        </td>
                        <td class="class-cell lab-cell">
                            <div class="subject-name" style="color: white;">Security Lab</div>
                            <div class="subject-code" style="color: white;">CS305-L</div>
                            <div class="teacher-name" style="color: white;">Dr. K. Malhotra</div>
                            <div class="room-number" style="background: white; color: #FF5252;">Lab 5</div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin-top: 30px;">
            <h3 style="color: #667eea; margin-bottom: 15px;">📝 Important Notes:</h3>
            <ul style="color: #666; line-height: 2;">
                <li>Students must attend all scheduled classes</li>
                <li>Lab sessions are of 3 hours duration (2:00 PM - 4:50 PM)</li>
                <li>Tutorial sessions are for doubt clearing and problem solving</li>
                <li>Minimum 75% attendance is mandatory</li>
                <li>Contact faculty in case of emergency leave</li>
            </ul>
        </div>

        <div style="text-align: center;">
            <a href="javascript:window.close();" class="back-btn">← Back to Portal</a>
        </div>
    </div>
</body>
</html>
