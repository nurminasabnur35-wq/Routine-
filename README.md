# Routine-
Routine apps
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>শিক্ষা প্রতিষ্ঠান রুটিন ব্যবস্থাপনা - ইউজার প্যানেল</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: linear-gradient(135deg, #1e88e5, #0d47a1);
            color: white;
            padding: 20px 0;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 20px;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            padding: 8px 16px;
            border-radius: 4px;
            transition: background 0.3s;
        }
        
        nav ul li a:hover, nav ul li a.active {
            background: rgba(255, 255, 255, 0.2);
        }
        
        .auth-buttons button {
            background: white;
            color: #1e88e5;
            border: none;
            padding: 8px 16px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            margin-left: 10px;
            transition: all 0.3s;
        }
        
        .auth-buttons button:hover {
            background: #e3f2fd;
            transform: translateY(-2px);
        }
        
        .card {
            background: white;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .card-title {
            font-size: 18px;
            font-weight: bold;
            color: #1e88e5;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        table th, table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        
        table th {
            background-color: #e3f2fd;
            color: #1e88e5;
        }
        
        table tr:hover {
            background-color: #f9f9f9;
        }
        
        .btn {
            padding: 8px 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
        }
        
        .btn i {
            margin-right: 5px;
        }
        
        .btn-primary {
            background: #1e88e5;
            color: white;
        }
        
        .btn-primary:hover {
            background: #1565c0;
            transform: translateY(-2px);
        }
        
        .routine-grid {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 10px;
            margin-top: 20px;
        }
        
        .time-slot {
            background: #e3f2fd;
            padding: 10px;
            text-align: center;
            font-weight: bold;
            border-radius: 4px;
        }
        
        .day-header {
            background: #1e88e5;
            color: white;
            padding: 10px;
            text-align: center;
            font-weight: bold;
            border-radius: 4px;
        }
        
        .routine-item {
            background: #f5f5f5;
            padding: 10px;
            border-radius: 4px;
            min-height: 100px;
        }
        
        .routine-item h4 {
            margin-bottom: 5px;
            color: #1e88e5;
        }
        
        .routine-item p {
            margin: 2px 0;
            font-size: 14px;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            padding: 15px;
            background: #e3f2fd;
            border-radius: 8px;
        }
        
        .user-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: #1e88e5;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            margin-right: 20px;
        }
        
        .user-details h3 {
            color: #1e88e5;
            margin-bottom: 5px;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        
        .modal-content {
            background: white;
            padding: 20px;
            border-radius: 8px;
            width: 500px;
            max-width: 90%;
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .close {
            font-size: 24px;
            cursor: pointer;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 15px;
                justify-content: center;
                flex-wrap: wrap;
            }
            
            nav ul li {
                margin: 5px;
            }
            
            .auth-buttons {
                margin-top: 15px;
            }
            
            .routine-grid {
                grid-template-columns: repeat(2, 1fr);
                overflow-x: auto;
            }
            
            .user-info {
                flex-direction: column;
                text-align: center;
            }
            
            .user-avatar {
                margin-right: 0;
                margin-bottom: 15px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-calendar-alt"></i> শিক্ষা প্রতিষ্ঠান রুটিন ব্যবস্থাপনা
            </div>
            <nav>
                <ul>
                    <li><a href="#" class="active">হোম</a></li>
                    <li><a href="#">রুটিন</a></li>
                    <li><a href="#">শিক্ষক</a></li>
                    <li><a href="#">ক্লাস</a></li>
                    <li><a href="#">সেটিংস</a></li>
                </ul>
            </nav>
            <div class="auth-buttons">
                <button id="loginBtn"><i class="fas fa-sign-in-alt"></i> লগইন</button>
                <button id="registerBtn"><i class="fas fa-user-plus"></i> রেজিস্টার</button>
            </div>
        </div>
    </header>

    <div class="container">
        <!-- ইউজার প্যানেল -->
        <div class="user-panel">
            <div class="user-info">
                <div class="user-avatar">
                    <i class="fas fa-user-graduate"></i>
                </div>
                <div class="user-details">
                    <h3>আহমেদ রফিক</h3>
                    <p>ক্লাস: একাদশ-ক (বিজ্ঞান বিভাগ)</p>
                    <p>রোল: ১২৩৪৫৬</p>
                </div>
            </div>
            
            <div class="card">
                <div class="card-header">
                    <div class="card-title">আমার সাপ্তাহিক রুটিন</div>
                    <div>
                        <button class="btn btn-primary"><i class="fas fa-print"></i> প্রিন্ট</button>
                        <button class="btn btn-primary"><i class="fas fa-download"></i> ডাউনলোড</button>
                    </div>
                </div>
                
                <div class="routine-grid">
                    <div class="time-slot">সময়</div>
                    <div class="day-header">শনিবার</div>
                    <div class="day-header">রবিবার</div>
                    <div class="day-header">সোমবার</div>
                    <div class="day-header">মঙ্গলবার</div>
                    <div class="day-header">বুধবার</div>
                    
                    <div class="time-slot">৮:০০ - ৮:৫০</div>
                    <div class="routine-item">
                        <h4>পদার্থবিজ্ঞান</h4>
                        <p>ড. রহিম</p>
                        <p>কক্ষ ৩০১</p>
                    </div>
                    <div class="routine-item">
                        <h4>রসায়ন</h4>
                        <p>প্রফেসর করিম</p>
                        <p>কক্ষ ৪০২</p>
                    </div>
                    <div class="routine-item">
                        <h4>গণিত</h4>
                        <p>ড. সুলতানা</p>
                        <p>কক্ষ ৫০১</p>
                    </div>
                    <div class="routine-item">
                        <h4>জীববিজ্ঞান</h4>
                        <p>প্রফেসর জাহান</p>
                        <p>কক্ষ ৬০৩</p>
                    </div>
                    <div class="routine-item">
                        <h4>পদার্থবিজ্ঞান</h4>
                        <p>ড. রহিম</p>
                        <p>কক্ষ ३०১</p>
                    </div>
                    
                    <div class="time-slot">৯:০০ - ৯:৫০</div>
                    <div class="routine-item">
                        <h4>গণিত</h4>
                        <p>ড. সুলতানা</p>
                        <p>কক্ষ ৫০১</p>
                    </div>
                    <div class="routine-item">
                        <h4>পদার্থবিজ্ঞান</h4>
                        <p>ড. রহিম</p>
                        <p>কক্ষ ৩০১</p>
                    </div>
                    <div class="routine-item">
                        <h4>জীববিজ্ঞান</h4>
                        <p>প্রফেসর জাহান</p>
                        <p>কক্ষ ৬০৩</p>
                    </div>
                    <div class="routine-item">
                        <h4>রসায়ন</h4>
                        <p>প্রফেসর করিম</p>
                        <p>কক্ষ ৪০২</p>
                    </div>
                    <div class="routine-item">
                        <h4>গণিত</h4>
                        <p>ড. সুলতানা</p>
                        <p>কক্ষ ৫০১</p>
                    </div>
                    
                    <div class="time-slot">১০:১৫ - ১১:০৫</div>
                    <div class="routine-item">
                        <h4>রসায়ন</h4>
                        <p>প্রফেসর করিম</p>
                        <p>কক্ষ ৪০২</p>
                    </div>
                    <div class="routine-item">
                        <h4>জীববিজ্ঞান</h4>
                        <p>প্রফেসর জাহান</p>
                        <p>কক্ষ ৬০৩</p>
                    </div>
                    <div class="routine-item">
                        <h4>পদার্থবিজ্ঞান</h4>
                        <p>ড. রহিম</p>
                        <p>কক্ষ ৩০১</p>
                    </div>
                    <div class="routine-item">
                        <h4>গণিত</h4>
                        <p>ড. সুলতানা</p>
                        <p>কক্ষ ৫০১</p>
                    </div>
                    <div class="routine-item">
                        <h4>রসায়ন</h4>
                        <p>প্রফেসর করিম</p>
                        <p>কক্ষ ৪০২</p>
                    </div>
                </div>
            </div>
            
            <div class="card">
                <div class="card-header">
                    <div class="card-title">আজকের ক্লাস Schedule</div>
                </div>
                <table>
                    <thead>
                        <tr>
                            <th>বিষয়</th>
                            <th>সময়</th>
                            <th>শিক্ষক</th>
                            <th>কক্ষ</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>পদার্থবিজ্ঞান</td>
                            <td>৮:০০ - ৮:৫০</td>
                            <td>ড. রহিম</td>
                            <td>৩০১</td>
                        </tr>
                        <tr>
                            <td>গণিত</td>
                            <td>৯:০০ - ৯:৫০</td>
                            <td>ড. সুলতানা</td>
                            <td>৫০১</td>
                        </tr>
                        <tr>
                            <td>রসায়ন</td>
                            <td>১০:১৫ - ১১:০৫</td>
                            <td>প্রফেসর করিম</td>
                            <td>৪০২</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- লগইন মোডাল -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>লগইন</h2>
                <span class="close">&times;</span>
            </div>
            <form>
                <div class="form-group">
                    <label for="email">ইমেইল</label>
                    <input type="email" id="email" placeholder="আপনার ইমেইল দিন">
                </div>
                <div class="form-group">
                    <label for="password">পাসওয়ার্ড</label>
                    <input type="password" id="password" placeholder="আপনার পাসওয়ার্ড দিন">
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">লগইন</button>
            </form>
        </div>
    </div>

    <script>
        // লগইন মোডাল ফাংশনালিটি
        const loginBtn = document.getElementById('loginBtn');
        const registerBtn = document.getElementById('registerBtn');
        const loginModal = document.getElementById('loginModal');
        const closeBtn = document.querySelector('.close');

        loginBtn.addEventListener('click', () => {
            loginModal.style.display = 'flex';
        });

        registerBtn.addEventListener('click', () => {
            loginModal.style.display = 'flex';
        });

        closeBtn.addEventListener('click', () => {
            loginModal.style.display = 'none';
        });

        window.addEventListener('click', (e) => {
            if (e.target === loginModal) {
                loginModal.style.display = 'none';
            }
        });
    </script>
</body>
</html>
