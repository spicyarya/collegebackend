<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Raise Ticket - College Portal</title>
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
        .tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
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
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
        }
        .form-section {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 10px;
            margin-bottom: 30px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            font-weight: bold;
            color: #333;
            margin-bottom: 8px;
        }
        input[type="text"],
        input[type="email"],
        select,
        textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 14px;
            transition: all 0.3s;
        }
        input:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: #667eea;
        }
        textarea {
            resize: vertical;
            min-height: 120px;
        }
        .submit-btn {
            background: #667eea;
            color: white;
            padding: 15px 40px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }
        .submit-btn:hover {
            background: #764ba2;
            transform: translateY(-2px);
        }
        .ticket-card {
            background: white;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 15px;
            transition: all 0.3s;
        }
        .ticket-card:hover {
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .ticket-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            flex-wrap: wrap;
            gap: 10px;
        }
        .ticket-id {
            font-weight: bold;
            color: #667eea;
            font-size: 18px;
        }
        .status-badge {
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
        }
        .status-open {
            background: #FFC107;
            color: #333;
        }
        .status-progress {
            background: #2196F3;
            color: white;
        }
        .status-resolved {
            background: #4CAF50;
            color: white;
        }
        .status-closed {
            background: #9E9E9E;
            color: white;
        }
        .ticket-content {
            margin-top: 10px;
        }
        .ticket-info {
            color: #666;
            font-size: 14px;
            margin: 5px 0;
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
            <h1>🎫 Raise Support Ticket</h1>
            <p>Submit your queries, complaints, and requests</p>
        </div>

        <div class="tabs">
            <button class="tab-btn active" onclick="showTab('new')">➕ New Ticket</button>
            <button class="tab-btn" onclick="showTab('my')">📋 My Tickets</button>
        </div>

        <!-- New Ticket Tab -->
        <div id="new-tab" class="tab-content active">
            <div class="form-section">
                <h2 style="color: #667eea; margin-bottom: 20px;">Create New Ticket</h2>
                <form id="ticketForm">
                    <div class="form-group">
                        <label for="category">Category *</label>
                        <select id="category" required>
                            <option value="">-- Select Category --</option>
                            <option value="academic">Academic Issue</option>
                            <option value="hostel">Hostel Related</option>
                            <option value="transport">Transport & Travel</option>
                            <option value="fee">Fee & Payment</option>
                            <option value="library">Library Services</option>
                            <option value="it">IT & Technical Support</option>
                            <option value="medical">Medical Emergency</option>
                            <option value="placement">Placement & Internship</option>
                            <option value="infrastructure">Infrastructure Issue</option>
                            <option value="other">Other</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="priority">Priority *</label>
                        <select id="priority" required>
                            <option value="">-- Select Priority --</option>
                            <option value="low">Low - Can wait a few days</option>
                            <option value="medium">Medium - Should be resolved soon</option>
                            <option value="high">High - Needs immediate attention</option>
                            <option value="urgent">Urgent - Critical issue</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="subject">Subject *</label>
                        <input type="text" id="subject" placeholder="Brief description of your issue" required>
                    </div>

                    <div class="form-group">
                        <label for="description">Detailed Description *</label>
                        <textarea id="description" placeholder="Please provide detailed information about your issue or request..." required></textarea>
                    </div>

                    <div class="form-group">
                        <label for="email">Contact Email *</label>
                        <input type="email" id="email" value="rajesh.kumar@college.edu.in" required>
                    </div>

                    <div class="form-group">
                        <label for="phone">Contact Phone *</label>
                        <input type="text" id="phone" value="+91 98765 43210" required>
                    </div>

                    <button type="submit" class="submit-btn">🚀 Submit Ticket</button>
                </form>
            </div>

            <div style="background: #e3f2fd; padding: 20px; border-radius: 10px; border-left: 4px solid #2196F3;">
                <h3 style="color: #1976D2; margin-bottom: 10px;">📝 Important Guidelines:</h3>
                <ul style="color: #666; line-height: 2; margin-left: 20px;">
                    <li>Provide accurate and complete information</li>
                    <li>For urgent issues, also contact relevant department directly</li>
                    <li>Track your ticket status in "My Tickets" section</li>
                    <li>You will receive email updates on your ticket</li>
                    <li>Average response time: 24-48 hours</li>
                </ul>
            </div>
        </div>

        <!-- My Tickets Tab -->
        <div id="my-tab" class="tab-content">
            <h2 style="color: #667eea; margin-bottom: 20px;">Your Support Tickets</h2>

            <div class="ticket-card">
                <div class="ticket-header">
                    <div>
                        <div class="ticket-id">#TKT-2024-1245</div>
                        <div style="color: #666; font-size: 14px; margin-top: 5px;">Submitted on: Dec 10, 2024</div>
                    </div>
                    <span class="status-badge status-resolved">✓ RESOLVED</span>
                </div>
                <div class="ticket-content">
                    <div style="font-weight: bold; color: #333; margin-bottom: 10px;">WiFi connectivity issues in hostel room</div>
                    <div class="ticket-info"><strong>Category:</strong> IT & Technical Support</div>
                    <div class="ticket-info"><strong>Priority:</strong> Medium</div>
                    <div class="ticket-info"><strong>Description:</strong> WiFi signal is very weak in room 305, unable to attend online classes properly.</div>
                    <div class="ticket-info" style="color: #4CAF50; margin-top: 10px;"><strong>Resolution:</strong> WiFi router has been upgraded. Issue has been fixed. Please check and confirm.</div>
                    <div class="ticket-info"><strong>Resolved on:</strong> Dec 12, 2024</div>
                </div>
            </div>

            <div class="ticket-card">
                <div class="ticket-header">
                    <div>
                        <div class="ticket-id">#TKT-2024-1189</div>
                        <div style="color: #666; font-size: 14px; margin-top: 5px;">Submitted on: Nov 28, 2024</div>
                    </div>
                    <span class="status-badge status-closed">CLOSED</span>
                </div>
                <div class="ticket-content">
                    <div style="font-weight: bold; color: #333; margin-bottom: 10px;">Grade correction request for CS302</div>
                    <div class="ticket-info"><strong>Category:</strong> Academic Issue</div>
                    <div class="ticket-info"><strong>Priority:</strong> High</div>
                    <div class="ticket-info"><strong>Description:</strong> I believe there was an error in my mid-term grading for Machine Learning subject. Request revaluation.</div>
                    <div class="ticket-info" style="color: #4CAF50; margin-top: 10px;"><strong>Resolution:</strong> Your answer sheet has been re-evaluated. Grade has been updated in the system. Please check.</div>
                    <div class="ticket-info"><strong>Closed on:</strong> Dec 3, 2024</div>
                </div>
            </div>

            <div class="ticket-card">
                <div class="ticket-header">
                    <div>
                        <div class="ticket-id">#TKT-2024-1056</div>
                        <div style="color: #666; font-size: 14px; margin-top: 5px;">Submitted on: Nov 15, 2024</div>
                    </div>
                    <span class="status-badge status-closed">CLOSED</span>
                </div>
                <div class="ticket-content">
                    <div style="font-weight: bold; color: #333; margin-bottom: 10px;">Library book lost - Need guidance</div>
                    <div class="ticket-info"><strong>Category:</strong> Library Services</div>
                    <div class="ticket-info"><strong>Priority:</strong> Medium</div>
                    <div class="ticket-info"><strong>Description:</strong> I lost the book "Design Patterns" issued from library. What should I do?</div>
                    <div class="ticket-info" style="color: #4CAF50; margin-top: 10px;"><strong>Resolution:</strong> Please visit the library and pay the book cost (₹850). Fine has been waived off.</div>
                    <div class="ticket-info"><strong>Closed on:</strong> Nov 18, 2024</div>
                </div>
            </div>

            <div class="ticket-card">
                <div class="ticket-header">
                    <div>
                        <div class="ticket-id">#TKT-2024-0923</div>
                        <div style="color: #666; font-size: 14px; margin-top: 5px;">Submitted on: Oct 22, 2024</div>
                    </div>
                    <span class="status-badge status-closed">CLOSED</span>
                </div>
                <div class="ticket-content">
                    <div style="font-weight: bold; color: #333; margin-bottom: 10px;">Mess food quality complaint</div>
                    <div class="ticket-info"><strong>Category:</strong> Hostel Related</div>
                    <div class="ticket-info"><strong>Priority:</strong> Medium</div>
                    <div class="ticket-info"><strong>Description:</strong> Food quality in hostel mess has deteriorated. Items are often undercooked or stale.</div>
                    <div class="ticket-info" style="color: #4CAF50; margin-top: 10px;"><strong>Resolution:</strong> Mess vendor has been warned. Quality checks have been increased. New menu has been introduced.</div>
                    <div class="ticket-info"><strong>Closed on:</strong> Oct 28, 2024</div>
                </div>
            </div>

            <div class="ticket-card">
                <div class="ticket-header">
                    <div>
                        <div class="ticket-id">#TKT-2024-0784</div>
                        <div style="color: #666; font-size: 14px; margin-top: 5px;">Submitted on: Sep 30, 2024</div>
                    </div>
                    <span class="status-badge status-closed">CLOSED</span>
                </div>
                <div class="ticket-content">
                    <div style="font-weight: bold; color: #333; margin-bottom: 10px;">ID card replacement request</div>
                    <div class="ticket-info"><strong>Category:</strong> Other</div>
                    <div class="ticket-info"><strong>Priority:</strong> High</div>
                    <div class="ticket-info"><strong>Description:</strong> Lost my college ID card. Need duplicate card urgently for exam hall entry.</div>
                    <div class="ticket-info" style="color: #4CAF50; margin-top: 10px;"><strong>Resolution:</strong> Duplicate ID card has been issued. Please collect from admin office with fee receipt.</div>
                    <div class="ticket-info"><strong>Closed on:</strong> Oct 2, 2024</div>
                </div>
            </div>

            <div style="text-align: center; margin-top: 30px; padding: 20px; background: #f8f9fa; border-radius: 10px;">
                <p style="color: #666;">Showing 5 most recent tickets</p>
                <p style="color: #666; margin-top: 10px;">Total Tickets: 12 | Open: 0 | In Progress: 0 | Resolved: 2 | Closed: 10</p>
            </div>
        </div>

        <div style="text-align: center;">
            <a href="javascript:window.close();" class="back-btn">← Back to Portal</a>
        </div>
    </div>

    <script>
        function showTab(tab) {
            // Hide all tabs
            document.getElementById('new-tab').classList.remove('active');
            document.getElementById('my-tab').classList.remove('active');
            
            // Remove active class from buttons
            let buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            
            // Show selected tab
            if(tab === 'new') {
                document.getElementById('new-tab').classList.add('active');
                buttons[0].classList.add('active');
            } else {
                document.getElementById('my-tab').classList.add('active');
                buttons[1].classList.add('active');
            }
        }

        document.getElementById('ticketForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('✓ Ticket submitted successfully!\n\nYour ticket ID: #TKT-2024-' + Math.floor(Math.random() * 9000 + 1000) + '\n\nYou will receive an email confirmation shortly.\nExpected response time: 24-48 hours');
            this.reset();
        });
    </script>
</body>
</html>
