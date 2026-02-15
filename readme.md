<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fee Details - College Portal</title>
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
        .status-banner {
            background: linear-gradient(135deg, #4CAF50 0%, #45a049 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            margin-bottom: 30px;
        }
        .status-banner.pending {
            background: linear-gradient(135deg, #FFC107 0%, #FFB300 100%);
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
        .fee-section {
            display: none;
        }
        .fee-section.active {
            display: block;
        }
        .fee-summary {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        .summary-card {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            border-left: 4px solid #667eea;
        }
        .summary-label {
            font-size: 14px;
            color: #666;
            margin-bottom: 10px;
        }
        .summary-value {
            font-size: 24px;
            font-weight: bold;
            color: #667eea;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
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
        .amount {
            font-weight: bold;
            color: #667eea;
        }
        .status-paid {
            background: #4CAF50;
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
        }
        .status-pending {
            background: #FFC107;
            color: #333;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
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
        .payment-btn {
            background: #4CAF50;
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            margin: 10px 5px;
        }
        .payment-btn:hover {
            background: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>💰 Fee Payment Portal</h1>
            <p>Rajesh Kumar (CSE-2021-145) | B.Tech Computer Science</p>
        </div>

        <div class="status-banner">
            <div style="font-size: 24px; margin-bottom: 10px;">✓ All Fees Paid</div>
            <div style="font-size: 18px; opacity: 0.9;">Your fee status is up to date for Academic Year 2024-25</div>
        </div>

        <div class="semester-tabs">
            <button class="tab-btn active" onclick="showFee(1)">Semester I</button>
            <button class="tab-btn" onclick="showFee(2)">Semester II</button>
            <button class="tab-btn" onclick="showFee(3)">Semester III</button>
            <button class="tab-btn" onclick="showFee(4)">Semester IV</button>
            <button class="tab-btn" onclick="showFee(5)">Semester V</button>
        </div>

        <!-- Semester 1 Fee -->
        <div id="fee1" class="fee-section active">
            <h2 style="color: #667eea; margin-bottom: 20px;">Semester I - Fee Details</h2>
            <div class="fee-summary">
                <div class="summary-card">
                    <div class="summary-label">Total Fee</div>
                    <div class="summary-value">₹85,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Amount Paid</div>
                    <div class="summary-value">₹85,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Balance</div>
                    <div class="summary-value" style="color: #4CAF50;">₹0</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Payment Date</div>
                    <div class="summary-value" style="font-size: 16px;">15 Aug 2021</div>
                </div>
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Fee Type</th>
                        <th>Amount (₹)</th>
                        <th>Status</th>
                        <th>Payment Date</th>
                        <th>Receipt No.</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tuition Fee</td>
                        <td class="amount">₹60,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Aug 2021</td>
                        <td>RCP2021001</td>
                    </tr>
                    <tr>
                        <td>Development Fee</td>
                        <td class="amount">₹10,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Aug 2021</td>
                        <td>RCP2021001</td>
                    </tr>
                    <tr>
                        <td>Library Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Aug 2021</td>
                        <td>RCP2021001</td>
                    </tr>
                    <tr>
                        <td>Lab Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Aug 2021</td>
                        <td>RCP2021001</td>
                    </tr>
                    <tr>
                        <td>Sports Fee</td>
                        <td class="amount">₹2,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Aug 2021</td>
                        <td>RCP2021001</td>
                    </tr>
                    <tr>
                        <td>Caution Money (Refundable)</td>
                        <td class="amount">₹3,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Aug 2021</td>
                        <td>RCP2021001</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 2 Fee -->
        <div id="fee2" class="fee-section">
            <h2 style="color: #667eea; margin-bottom: 20px;">Semester II - Fee Details</h2>
            <div class="fee-summary">
                <div class="summary-card">
                    <div class="summary-label">Total Fee</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Amount Paid</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Balance</div>
                    <div class="summary-value" style="color: #4CAF50;">₹0</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Payment Date</div>
                    <div class="summary-value" style="font-size: 16px;">10 Jan 2022</div>
                </div>
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Fee Type</th>
                        <th>Amount (₹)</th>
                        <th>Status</th>
                        <th>Payment Date</th>
                        <th>Receipt No.</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tuition Fee</td>
                        <td class="amount">₹60,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>10 Jan 2022</td>
                        <td>RCP2022045</td>
                    </tr>
                    <tr>
                        <td>Development Fee</td>
                        <td class="amount">₹10,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>10 Jan 2022</td>
                        <td>RCP2022045</td>
                    </tr>
                    <tr>
                        <td>Library Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>10 Jan 2022</td>
                        <td>RCP2022045</td>
                    </tr>
                    <tr>
                        <td>Lab Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>10 Jan 2022</td>
                        <td>RCP2022045</td>
                    </tr>
                    <tr>
                        <td>Sports Fee</td>
                        <td class="amount">₹2,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>10 Jan 2022</td>
                        <td>RCP2022045</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 3 Fee -->
        <div id="fee3" class="fee-section">
            <h2 style="color: #667eea; margin-bottom: 20px;">Semester III - Fee Details</h2>
            <div class="fee-summary">
                <div class="summary-card">
                    <div class="summary-label">Total Fee</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Amount Paid</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Balance</div>
                    <div class="summary-value" style="color: #4CAF50;">₹0</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Payment Date</div>
                    <div class="summary-value" style="font-size: 16px;">20 Aug 2022</div>
                </div>
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Fee Type</th>
                        <th>Amount (₹)</th>
                        <th>Status</th>
                        <th>Payment Date</th>
                        <th>Receipt No.</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tuition Fee</td>
                        <td class="amount">₹60,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>20 Aug 2022</td>
                        <td>RCP2022543</td>
                    </tr>
                    <tr>
                        <td>Development Fee</td>
                        <td class="amount">₹10,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>20 Aug 2022</td>
                        <td>RCP2022543</td>
                    </tr>
                    <tr>
                        <td>Library Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>20 Aug 2022</td>
                        <td>RCP2022543</td>
                    </tr>
                    <tr>
                        <td>Lab Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>20 Aug 2022</td>
                        <td>RCP2022543</td>
                    </tr>
                    <tr>
                        <td>Sports Fee</td>
                        <td class="amount">₹2,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>20 Aug 2022</td>
                        <td>RCP2022543</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 4 Fee -->
        <div id="fee4" class="fee-section">
            <h2 style="color: #667eea; margin-bottom: 20px;">Semester IV - Fee Details</h2>
            <div class="fee-summary">
                <div class="summary-card">
                    <div class="summary-label">Total Fee</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Amount Paid</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Balance</div>
                    <div class="summary-value" style="color: #4CAF50;">₹0</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Payment Date</div>
                    <div class="summary-value" style="font-size: 16px;">15 Jan 2023</div>
                </div>
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Fee Type</th>
                        <th>Amount (₹)</th>
                        <th>Status</th>
                        <th>Payment Date</th>
                        <th>Receipt No.</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tuition Fee</td>
                        <td class="amount">₹60,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Jan 2023</td>
                        <td>RCP2023189</td>
                    </tr>
                    <tr>
                        <td>Development Fee</td>
                        <td class="amount">₹10,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Jan 2023</td>
                        <td>RCP2023189</td>
                    </tr>
                    <tr>
                        <td>Library Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Jan 2023</td>
                        <td>RCP2023189</td>
                    </tr>
                    <tr>
                        <td>Lab Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Jan 2023</td>
                        <td>RCP2023189</td>
                    </tr>
                    <tr>
                        <td>Sports Fee</td>
                        <td class="amount">₹2,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>15 Jan 2023</td>
                        <td>RCP2023189</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Semester 5 Fee -->
        <div id="fee5" class="fee-section">
            <h2 style="color: #667eea; margin-bottom: 20px;">Semester V - Fee Details (Current)</h2>
            <div class="fee-summary">
                <div class="summary-card">
                    <div class="summary-label">Total Fee</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Amount Paid</div>
                    <div class="summary-value">₹82,000</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Balance</div>
                    <div class="summary-value" style="color: #4CAF50;">₹0</div>
                </div>
                <div class="summary-card">
                    <div class="summary-label">Payment Date</div>
                    <div class="summary-value" style="font-size: 16px;">25 Aug 2024</div>
                </div>
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Fee Type</th>
                        <th>Amount (₹)</th>
                        <th>Status</th>
                        <th>Payment Date</th>
                        <th>Receipt No.</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tuition Fee</td>
                        <td class="amount">₹60,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>25 Aug 2024</td>
                        <td>RCP2024876</td>
                    </tr>
                    <tr>
                        <td>Development Fee</td>
                        <td class="amount">₹10,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>25 Aug 2024</td>
                        <td>RCP2024876</td>
                    </tr>
                    <tr>
                        <td>Library Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>25 Aug 2024</td>
                        <td>RCP2024876</td>
                    </tr>
                    <tr>
                        <td>Lab Fee</td>
                        <td class="amount">₹5,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>25 Aug 2024</td>
                        <td>RCP2024876</td>
                    </tr>
                    <tr>
                        <td>Sports Fee</td>
                        <td class="amount">₹2,000</td>
                        <td><span class="status-paid">PAID</span></td>
                        <td>25 Aug 2024</td>
                        <td>RCP2024876</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin-top: 30px;">
            <h3 style="color: #667eea; margin-bottom: 15px;">📝 Payment Information:</h3>
            <ul style="color: #666; line-height: 2;">
                <li><strong>Total Fee Paid:</strong> ₹4,13,000 (All Semesters)</li>
                <li><strong>Payment Mode:</strong> Online Transfer / Demand Draft</li>
                <li><strong>Bank Details:</strong> State Bank of India, College Branch</li>
                <li><strong>Late Fee:</strong> ₹500 per week after due date</li>
                <li><strong>Refund Policy:</strong> Caution money refundable after course completion</li>
            </ul>
        </div>

        <div style="text-align: center;">
            <a href="javascript:window.close();" class="back-btn">← Back to Portal</a>
        </div>
    </div>

    <script>
        function showFee(semNum) {
            // Hide all sections
            for(let i = 1; i <= 5; i++) {
                document.getElementById('fee' + i).classList.remove('active');
            }
            // Remove active class from all buttons
            let buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            
            // Show selected section
            document.getElementById('fee' + semNum).classList.add('active');
            buttons[semNum - 1].classList.add('active');
        }
    </script>
</body>
</html>
