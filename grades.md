<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grades - College Portal</title>
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
        .cgpa-banner {
            background: linear-gradient(135deg, #4CAF50 0%, #45a049 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            margin-bottom: 30px;
        }
        .cgpa-value {
            font-size: 64px;
            font-weight: bold;
            margin: 10px 0;
        }
        .semester-tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }
        .tab-btn {
            padding: 12px 25px;
            background: #f0f0f0;
            border: 2px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
        }
        .tab-btn:hover {
            background: #e0e0e0;
        }
        .tab-btn.active {
            background: #667eea;
            color: white;
            border-color: #667eea;
        }
        .semester-content {
            display: none;
        }
        .semester-content.active {
            display: block;
        }
        .semester-header {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        .sem-stats {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
        }
        .stat-item {
            text-align: center;
        }
        .stat-value {
            font-size: 28px;
            font-weight: bold;
            color: #667eea;
        }
        .stat-label {
            font-size: 14px;
            color: #666;
            margin-top: 5px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        th {
            background: #667eea;
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: bold;
        }
        td {
            padding: 15px;
            border-bottom: 1px solid #e0e0e0;
        }
        tr:hover {
            background: #f8f9fa;
        }
        .grade-A { color: #4CAF50; font-weight: bold; }
        .grade-B { color: #8BC34A; font-weight: bold; }
        .grade-C { color: #FFC107; font-weight: bold; }
        .grade-D { color: #FF9800; font-weight: bold; }
        .grade-F { color: #F44336; font-weight: bold; }
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
            <h1>🎓 Academic Grades</h1>
            <p>Rajesh Kumar (CSE-2021-145) | B.Tech Computer Science</p>
        </div>

        <div class="cgpa-banner">
            <div style="font-size: 24px; opacity: 0.9;">Cumulative Grade Point Average</div>
            <div class="cgpa-value">8.65</div>
            <div style="font-size: 18px;">Out of 10.0 | Percentile: 85th</div>
        </div>

        <div class="semester-tabs">
            <button class="tab-btn active" onclick="showSemester(1)">Semester I</button>
            <button class="tab-btn" onclick="showSemester(2)">Semester II</button>
            <button class="tab-btn" onclick="showSemester(3)">Semester III</button>
            <button class="tab-btn" onclick="showSemester(4)">Semester IV</button>
            <button class="tab-btn" onclick="showSemester(5)">Semester V (Current)</button>
        </div>

        <!-- Semester 1 -->
        <div id="sem1" class="semester-content active">
            <div class="semester-header">
                <h2 style="color: #667eea; margin-bottom: 15px;">Semester I - Results</h2>
                <div class="sem-stats">
                    <div class="stat-item">
                        <div class="stat-value">8.4</div>
                        <div class="stat-label">SGPA</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">22</div>
                        <div class="stat-label">Credits Earned</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">Pass</div>
                        <div class="stat-label">Result Status</div>
                    </div>
                </div>
            </div>
            <table>
                <thead>
                    <tr>
                        <th>Subject Code</th>
                        <th>Subject Name</th>
                        <th>Credits</th>
                        <th>Internal</th>
                        <th>External</th>
                        <th>Total</th>
                        <th>Grade</th>
                        <th>Grade Points</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>MA101</td>
                        <td>Engineering Mathematics-I</td>
                        <td>4</td>
                        <td>28/30</td>
                        <td>63/70</td>
                        <td>91/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                    <tr>
                        <td>PH101</td>
                        <td>Engineering Physics</td>
                        <td>4</td>
                        <td>25/30</td>
                        <td>58/70</td>
                        <td>83/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>CH101</td>
                        <td>Engineering Chemistry</td>
                        <td>4</td>
                        <td>26/30</td>
                        <td>60/70</td>
                        <td>86/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>CS101</td>
                        <td>Programming in C</td>
                        <td>4</td>
                        <td>29/30</td>
                        <td>65/70</td>
                        <td>94/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                    <tr>
                        <td>EE101</td>
                        <td>Basic Electrical Engineering</td>
                        <td>3</td>
                        <td>24/30</td>
                        <td>56/70</td>
                        <td>80/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>HS101</td>
                        <td>Communication Skills</td>
                        <td>3</td>
                        <td>27/30</td>
                        <td>62/70</td>
                        <td>89/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 2 -->
        <div id="sem2" class="semester-content">
            <div class="semester-header">
                <h2 style="color: #667eea; margin-bottom: 15px;">Semester II - Results</h2>
                <div class="sem-stats">
                    <div class="stat-item">
                        <div class="stat-value">8.6</div>
                        <div class="stat-label">SGPA</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">22</div>
                        <div class="stat-label">Credits Earned</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">Pass</div>
                        <div class="stat-label">Result Status</div>
                    </div>
                </div>
            </div>
            <table>
                <thead>
                    <tr>
                        <th>Subject Code</th>
                        <th>Subject Name</th>
                        <th>Credits</th>
                        <th>Internal</th>
                        <th>External</th>
                        <th>Total</th>
                        <th>Grade</th>
                        <th>Grade Points</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>MA102</td>
                        <td>Engineering Mathematics-II</td>
                        <td>4</td>
                        <td>27/30</td>
                        <td>61/70</td>
                        <td>88/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>CS102</td>
                        <td>Data Structures</td>
                        <td>4</td>
                        <td>29/30</td>
                        <td>67/70</td>
                        <td>96/100</td>
                        <td class="grade-A">A+</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>CS103</td>
                        <td>Object Oriented Programming</td>
                        <td>4</td>
                        <td>28/30</td>
                        <td>64/70</td>
                        <td>92/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                    <tr>
                        <td>EC101</td>
                        <td>Digital Electronics</td>
                        <td>3</td>
                        <td>25/30</td>
                        <td>59/70</td>
                        <td>84/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>ME101</td>
                        <td>Engineering Graphics</td>
                        <td>4</td>
                        <td>26/30</td>
                        <td>60/70</td>
                        <td>86/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>HS102</td>
                        <td>Professional Ethics</td>
                        <td>3</td>
                        <td>28/30</td>
                        <td>65/70</td>
                        <td>93/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 3 -->
        <div id="sem3" class="semester-content">
            <div class="semester-header">
                <h2 style="color: #667eea; margin-bottom: 15px;">Semester III - Results</h2>
                <div class="sem-stats">
                    <div class="stat-item">
                        <div class="stat-value">8.8</div>
                        <div class="stat-label">SGPA</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">24</div>
                        <div class="stat-label">Credits Earned</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">Pass</div>
                        <div class="stat-label">Result Status</div>
                    </div>
                </div>
            </div>
            <table>
                <thead>
                    <tr>
                        <th>Subject Code</th>
                        <th>Subject Name</th>
                        <th>Credits</th>
                        <th>Internal</th>
                        <th>External</th>
                        <th>Total</th>
                        <th>Grade</th>
                        <th>Grade Points</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>CS201</td>
                        <td>Computer Organization</td>
                        <td>4</td>
                        <td>28/30</td>
                        <td>64/70</td>
                        <td>92/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                    <tr>
                        <td>CS202</td>
                        <td>Discrete Mathematics</td>
                        <td>4</td>
                        <td>27/30</td>
                        <td>62/70</td>
                        <td>89/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>CS203</td>
                        <td>Design & Analysis of Algorithms</td>
                        <td>4</td>
                        <td>29/30</td>
                        <td>66/70</td>
                        <td>95/100</td>
                        <td class="grade-A">A+</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>CS204</td>
                        <td>Database Management Systems</td>
                        <td>4</td>
                        <td>28/30</td>
                        <td>65/70</td>
                        <td>93/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                    <tr>
                        <td>CS205</td>
                        <td>Computer Networks</td>
                        <td>4</td>
                        <td>26/30</td>
                        <td>61/70</td>
                        <td>87/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>MA201</td>
                        <td>Probability & Statistics</td>
                        <td>4</td>
                        <td>27/30</td>
                        <td>63/70</td>
                        <td>90/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 4 -->
        <div id="sem4" class="semester-content">
            <div class="semester-header">
                <h2 style="color: #667eea; margin-bottom: 15px;">Semester IV - Results</h2>
                <div class="sem-stats">
                    <div class="stat-item">
                        <div class="stat-value">8.7</div>
                        <div class="stat-label">SGPA</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">24</div>
                        <div class="stat-label">Credits Earned</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">Pass</div>
                        <div class="stat-label">Result Status</div>
                    </div>
                </div>
            </div>
            <table>
                <thead>
                    <tr>
                        <th>Subject Code</th>
                        <th>Subject Name</th>
                        <th>Credits</th>
                        <th>Internal</th>
                        <th>External</th>
                        <th>Total</th>
                        <th>Grade</th>
                        <th>Grade Points</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>CS206</td>
                        <td>Operating Systems</td>
                        <td>4</td>
                        <td>29/30</td>
                        <td>65/70</td>
                        <td>94/100</td>
                        <td class="grade-A">A+</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>CS207</td>
                        <td>Software Engineering</td>
                        <td>4</td>
                        <td>27/30</td>
                        <td>62/70</td>
                        <td>89/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>CS208</td>
                        <td>Theory of Computation</td>
                        <td>4</td>
                        <td>26/30</td>
                        <td>60/70</td>
                        <td>86/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>CS209</td>
                        <td>Web Technologies</td>
                        <td>4</td>
                        <td>28/30</td>
                        <td>64/70</td>
                        <td>92/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                    <tr>
                        <td>CS210</td>
                        <td>Computer Graphics</td>
                        <td>4</td>
                        <td>25/30</td>
                        <td>59/70</td>
                        <td>84/100</td>
                        <td class="grade-A">A</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>HS201</td>
                        <td>Organizational Behavior</td>
                        <td>4</td>
                        <td>28/30</td>
                        <td>65/70</td>
                        <td>93/100</td>
                        <td class="grade-A">A+</td>
                        <td>9</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 5 -->
        <div id="sem5" class="semester-content">
            <div class="semester-header">
                <h2 style="color: #667eea; margin-bottom: 15px;">Semester V - Current (Mid-Term Marks)</h2>
                <div class="sem-stats">
                    <div class="stat-item">
                        <div class="stat-value">Ongoing</div>
                        <div class="stat-label">SGPA</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">24</div>
                        <div class="stat-label">Total Credits</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">In Progress</div>
                        <div class="stat-label">Result Status</div>
                    </div>
                </div>
            </div>
            <table>
                <thead>
                    <tr>
                        <th>Subject Code</th>
                        <th>Subject Name</th>
                        <th>Credits</th>
                        <th>Mid-Term 1</th>
                        <th>Mid-Term 2</th>
                        <th>Assignments</th>
                        <th>Total (30)</th>
                        <th>Status</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>CS301</td>
                        <td>Artificial Intelligence</td>
                        <td>4</td>
                        <td>18/20</td>
                        <td>19/20</td>
                        <td>9/10</td>
                        <td>28/30</td>
                        <td class="grade-A">Excellent</td>
                    </tr>
                    <tr>
                        <td>CS302</td>
                        <td>Machine Learning</td>
                        <td>4</td>
                        <td>17/20</td>
                        <td>18/20</td>
                        <td>8/10</td>
                        <td>27/30</td>
                        <td class="grade-A">Excellent</td>
                    </tr>
                    <tr>
                        <td>CS303</td>
                        <td>Cloud Computing</td>
                        <td>4</td>
                        <td>16/20</td>
                        <td>17/20</td>
                        <td>8/10</td>
                        <td>26/30</td>
                        <td class="grade-A">Very Good</td>
                    </tr>
                    <tr>
                        <td>CS304</td>
                        <td>Compiler Design</td>
                        <td>4</td>
                        <td>17/20</td>
                        <td>18/20</td>
                        <td>9/10</td>
                        <td>27/30</td>
                        <td class="grade-A">Excellent</td>
                    </tr>
                    <tr>
                        <td>CS305</td>
                        <td>Information Security</td>
                        <td>4</td>
                        <td>18/20</td>
                        <td>19/20</td>
                        <td>9/10</td>
                        <td>28/30</td>
                        <td class="grade-A">Excellent</td>
                    </tr>
                    <tr>
                        <td>HS301</td>
                        <td>Entrepreneurship Development</td>
                        <td>4</td>
                        <td>19/20</td>
                        <td>18/20</td>
                        <td>10/10</td>
                        <td>29/30</td>
                        <td class="grade-A">Outstanding</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div style="text-align: center;">
            <a href="javascript:window.close();" class="back-btn">← Back to Portal</a>
        </div>
    </div>

    <script>
        function showSemester(semNum) {
            // Hide all semesters
            for(let i = 1; i <= 5; i++) {
                document.getElementById('sem' + i).classList.remove('active');
            }
            // Remove active class from all buttons
            let buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            
            // Show selected semester
            document.getElementById('sem' + semNum).classList.add('active');
            buttons[semNum - 1].classList.add('active');
        }
    </script>
</body>
</html>
