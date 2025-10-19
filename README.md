<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>টাকা আয় করুন - বিজ্ঞাপন দেখুন</title>
    <script src='//libtl.com/sdk.js' data-zone='10060125' data-sdk='show_10060125'></script> 
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary-color: #4a6bff;
            --secondary-color: #ff7d4a;
            --success-color: #28a745;
            --danger-color: #dc3545;
            --warning-color: #ffc107;
            --dark-color: #1a1a2e;
            --light-color: #f8f9fa;
            --card-bg: #16213e;
            --text-color: #e6e6e6;
            --text-muted: #adb5bd;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: var(--text-color);
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            padding: 15px;
            padding-bottom: 70px; /* নেভিগেশন বারের জন্য স্থান */
            
            /* বাম দিকের প্যানেল সরাতে গুরুত্বপূর্ণ ফিক্স */
            overflow-x: hidden; 
            width: 100vw;
            position: relative; /* কয়েন অ্যানিমেশনকে কন্ট্রোল করতে */
        }
        
        .container {
            max-width: 500px;
            width: 100%;
            margin: 0 auto;
            background: rgba(22, 33, 62, 0.9);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            /* ওভারফ্লো সরানো হয়েছে যাতে কয়েন দেখা যায় */
            /* overflow: hidden; */ 
            padding-bottom: 20px;
            backdrop-filter: blur(10px);
            min-width: 100%; 
        }
        
        .header {
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
            border-bottom: 5px solid rgba(255, 255, 255, 0.1);
        }
        
        .header h1 {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .badge {
            display: inline-block;
            background-color: rgba(255, 255, 255, 0.2);
            padding: 5px 12px;
            border-radius: 50px;
            font-size: 12px;
            font-weight: 600;
            margin-top: 10px;
        }
        
        .user-card, .stat-card, .progress-container, .referral-section, .rate-info, .withdraw-section, .ad-status {
            background-color: var(--card-bg);
            margin: 15px;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }
        
        .user-card {
            display: flex;
            align-items: center;
        }
        
        .user-avatar {
            width: 50px;
            height: 50px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 20px;
            color: white;
            margin-right: 15px;
        }
        
        .stats-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }
        
        .stat-card {
            text-align: center;
            transition: transform 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
        }
        
        .stat-card h3 {
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 10px;
        }
        
        .stat-card p {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary-color);
        }
        
        .progress-container {
            background: linear-gradient(to right, #0f0c29, #302b63);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .progress-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
        }
        
        .progress-bar {
            height: 10px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            overflow: hidden;
            margin-bottom: 10px;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            border-radius: 5px;
            width: 0%;
            transition: width 0.5s ease;
        }
        
        .progress-text {
            display: flex;
            justify-content: space-between;
            font-size: 12px;
            color: var(--text-muted);
        }
        
        .action-buttons {
            display: grid;
            grid-template-columns: 1fr;
            gap: 10px;
            margin: 15px;
        }
        
        .btn {
            padding: 15px;
            border: none;
            border-radius: 10px;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .btn-primary { 
            background: linear-gradient(to right, var(--primary-color), #6a11cb);
            color: white; 
        }
        
        .btn-success { 
            background: linear-gradient(to right, var(--success-color), #11998e);
            color: white; 
        }
        
        .btn-danger { 
            background: linear-gradient(to right, var(--danger-color), #ff416c);
            color: white; 
        }
        
        .btn-warning { 
            background: linear-gradient(to right, var(--warning-color), #ff7e5f);
            color: white; 
        }
        
        .btn-secondary { 
            background: linear-gradient(to right, #2c3e50, #4ca1af);
            color: var(--text-color); 
            border: 1px solid rgba(255, 255, 255, 0.1); 
        }
        
        .btn:hover { 
            transform: translateY(-3px); 
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3); 
        }
        
        .btn:active { 
            transform: translateY(0); 
        }
        
        .btn:disabled { 
            opacity: 0.6; 
            cursor: not-allowed; 
            transform: none; 
            box-shadow: none; 
        }
        
        .btn i { 
            margin-right: 8px; 
            font-size: 18px; 
        }
        
        .section-title {
            font-size: 18px;
            margin-bottom: 15px;
            color: white;
            display: flex;
            align-items: center;
        }
        
        .section-title i {
            margin-right: 10px;
            color: var(--secondary-color);
        }
        
        .referral-stats {
            display: flex;
            justify-content: space-between;
            background-color: rgba(0, 0, 0, 0.2);
            padding: 10px 15px;
            border-radius: 8px;
            margin-bottom: 15px;
        }
        
        .referral-link-container {
            display: flex;
            margin-top: 15px;
        }
        
        #referral-link {
            flex: 1;
            padding: 12px;
            background-color: rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px 0 0 8px;
            color: var(--text-color);
            font-size: 14px;
            outline: none;
        }
        
        #copy-referral {
            padding: 0 15px;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            border: none;
            border-radius: 0 8px 8px 0;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        #copy-referral:hover {
            opacity: 0.9;
        }
        
        .withdraw-section { 
            display: none; 
        }
        
        .form-group { 
            margin-bottom: 15px; 
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-size: 14px;
            color: var(--text-muted);
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            background-color: rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            color: var(--text-color);
            font-size: 14px;
            outline: none;
            transition: all 0.3s ease;
        }
        
        .form-control:focus {
            border-color: var(--primary-color);
            box-shadow: 0 0 0 2px rgba(74, 107, 255, 0.3);
        }
        
        #withdraw-status {
            margin-top: 15px;
            font-size: 14px;
            text-align: center;
            padding: 10px;
            border-radius: 8px;
        }
        
        .success-message { 
            background-color: rgba(40, 167, 69, 0.2); 
            color: var(--success-color); 
        }
        
        .error-message { 
            background-color: rgba(220, 53, 69, 0.2); 
            color: var(--danger-color); 
        }
        
        .info-message { 
            background-color: rgba(74, 107, 255, 0.2); 
            color: var(--primary-color); 
        }
        
        .footer {
            text-align: center;
            margin-top: 20px;
            font-size: 12px;
            color: var(--text-muted);
        }
        
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px;
            border-radius: 8px;
            background: var(--card-bg);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            z-index: 1000;
            display: flex;
            align-items: center;
            transform: translateX(150%);
            transition: transform 0.5s ease;
        }
        
        .notification.show {
            transform: translateX(0);
        }
        
        .notification i {
            margin-right: 10px;
            font-size: 20px;
        }
        
        .notification.success {
            border-left: 4px solid var(--success-color);
        }
        
        .notification.error {
            border-left: 4px solid var(--danger-color);
        }
        
        .notification.info {
            border-left: 4px solid var(--primary-color);
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .pulse { 
            animation: pulse 1.5s infinite; 
        }
        
        /* কয়েন অ্যানিমেশন ফিক্সড */
        @keyframes coinAnimation {
            0% { transform: translateY(0) rotate(0); opacity: 1; }
            100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
        }
        
        .coin-animation {
            position: fixed; /* body এর উপরে ভেসে থাকার জন্য */
            font-size: 32px; /* একটু বড় করা হলো */
            color: gold;
            z-index: 9999; /* সবার উপরে থাকার জন্য */
            animation: coinAnimation 1.5s forwards ease-out; /* অ্যানিমেশন সময় বাড়ানো হলো */
            pointer-events: none; /* যাতে অন্য কিছুর উপর ক্লিক করা যায় */
        }
        
        /* নেভিগেশন বার স্টাইল */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: var(--card-bg);
            display: flex;
            justify-content: space-around;
            padding: 10px 0;
            box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.2);
            z-index: 1000;
        }
        
        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            color: var(--text-muted);
            text-decoration: none;
            font-size: 12px;
            transition: all 0.3s ease;
            padding: 5px 10px;
            border-radius: 10px;
            width: 25%;
        }
        
        .nav-item.active {
            color: var(--primary-color);
            background: rgba(74, 107, 255, 0.2);
        }
        
        .nav-item i {
            font-size: 20px;
            margin-bottom: 5px;
        }
        
        .nav-item:hover {
            color: var(--primary-color);
        }
        
        /* পেজ সেকশন স্টাইল */
        .page-section {
            display: none;
        }
        
        .page-section.active {
            display: block;
        }
        
        /* বিজ্ঞাপন কন্টেইনার স্টাইল */
        .ad-container {
            margin: 15px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 90px;
            background-color: rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            overflow: hidden;
        }
        
        @media (max-width: 400px) {
            .header h1 { font-size: 20px; }
            .stats-container { grid-template-columns: 1fr; }
            .btn { padding: 12px; font-size: 14px; }
            .nav-item { font-size: 10px; padding: 5px; }
            .nav-item i { font-size: 18px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>টাকা আয় করুন - বিজ্ঞাপন দেখুন</h1>
            <p>বিজ্ঞাপন দেখে আসল টাকা আয় করুন</p>
            <div class="badge">সক্রিয়</div>
        </div>
        
        <div class="ad-container">
            <center>
                <script type="text/javascript">
                    atOptions = {
                        'key' : '64e65edd2667cea18db20a1e18ad04fa',
                        'format' : 'iframe',
                        'height' : 50,
                        'width' : 320,
                        'params' : {}
                    };
                </script>
                <script type='text/javascript' src='//pl27867166.effectivegatecpm.com/64/e6/5e/64e65edd2667cea18db20a1e18ad04fa.js'></script>
            </center>
        </div>
        
        <div class="page-section active" id="home-page">
            <div class="user-card">
                <div class="user-avatar" id="user-avatar">U</div>
                <div class="user-info">
                    <h3 id="user-name">ব্যবহারকারী</h3>
                    <p>আইডি: <span id="user-id">12345</span></p>
                </div>
            </div>
            
            <div class="stats-container">
                <div class="stat-card">
                    <h3>দেখা বিজ্ঞাপন</h3>
                    <p id="watched-ads">0</p>
                </div>
                <div class="stat-card">
                    <h3>আয়কৃত টাকা</h3>
                    <p id="earned-money">0.00 <small>টাকা</small></p>
                </div>
            </div>
            
            <div class="progress-container">
                <div class="progress-header">
                    <h3>আজকের অগ্রগতি</h3>
                    <span id="ads-progress">0/10</span>
                </div>
                <div class="progress-bar">
                    <div class="progress-fill" id="progress-fill"></div>
                </div>
                <div class="progress-text">
                    <span>0 টাকা</span>
                    <span>20 টাকা</span>
                </div>
            </div>
            
            <div class="ad-status" id="ad-status">
                <i class="fas fa-check-circle"></i> বিজ্ঞাপন দেখতে প্রস্তুত
            </div>
            
            <div class="action-buttons">
                <button class="btn btn-primary" id="watch-ad-btn" onclick="watchAd()">
                    <i class="fas fa-play"></i> বিজ্ঞাপন দেখুন (২ টাকা)
                </button>
                <button class="btn btn-success" id="auto-ad-btn" onclick="startAutoAds()">
                    <i class="fas fa-robot"></i> স্বয়ংক্রিয় বিজ্ঞাপন
                </button>
                <button class="btn btn-danger" id="stop-auto-btn" onclick="stopAutoAds()" disabled>
                    <i class="fas fa-stop"></i> বন্ধ করুন
                </button>
                <button class="btn btn-secondary" onclick="showWithdrawForm()">
                    <i class="fas fa-wallet"></i> টাকা উত্তোলন
                </button>
            </div>
            
            <div class="ad-container">
                <center>
                    <script type="text/javascript">
                        atOptions = {
                            'key' : '2bbfffd68ddcb97dd76fea912b577da7',
                            'format' : 'iframe',
                            'height' : 50,
                            'width' : 320,
                            'params' : {}
                        };
                    </script>
                    <script type='text/javascript' src='//pl27867132.effectivegatecpm.com/2b/bf/ff/2bbfffd68ddcb97dd76fea912b577da7.js'></script>
                </center>
            </div>
            
            <div class="referral-section">
                <h3 class="section-title"><i class="fas fa-users"></i> বন্ধুকে আমন্ত্রণ করুন</h3>
                <div class="referral-stats">
                    <div>আমন্ত্রিত: <strong id="referral-count">0</strong></div>
                    <div>আয়: <strong id="referral-earnings">0.00</strong> টাকা</div>
                </div>
                <p style="font-size: 14px; margin-bottom: 10px;">আপনার রেফারেল লিঙ্ক শেয়ার করুন এবং প্রতিটি বন্ধুর জন্য ৫ টাকা বোনাস পান!</p>
                <div class="referral-link-container">
                    <input type="text" id="referral-link" readonly>
                    <button id="copy-referral" onclick="copyReferralLink()">কপি</button>
                </div>
            </div>
            
            <div class="rate-info">
                <p><i class="fas fa-ad"></i> প্রতি বিজ্ঞাপন = ২ টাকা</p>
                <p><i class="fas fa-money-bill-wave"></i> ন্যূনতম উত্তোলন: ২০ টাকা</p>
                <p><i class="fas fa-gift"></i> রেফারেল বোনাস: ৫ টাকা প্রতি ব্যবহারকারী</p>
            </div>
        </div>
        
        <div class="page-section" id="earn-page">
            <h3 class="section-title"><i class="fas fa-coins"></i> টাকা আয় করার উপায়</h3>
            
            <div class="action-buttons">
                <button class="btn btn-primary" id="watch-ad-btn-earn" onclick="watchAd()">
                    <i class="fas fa-play"></i> বিজ্ঞাপন দেখুন (২ টাকা)
                </button>
                <button class="btn btn-success" id="auto-ad-btn-earn" onclick="startAutoAds()">
                    <i class="fas fa-robot"></i> স্বয়ংক্রিয় বিজ্ঞাপন
                </button>
                <button class="btn btn-danger" id="stop-auto-btn-earn" onclick="stopAutoAds()" disabled>
                    <i class="fas fa-stop"></i> বন্ধ করুন
                </button>
            </div>
            
            <div class="referral-section">
                <h3 class="section-title"><i class="fas fa-users"></i> বন্ধুকে আমন্ত্রণ করুন</h3>
                <div class="referral-stats">
                    <div>আমন্ত্রিত: <strong id="referral-count-earn">0</strong></div>
                    <div>আয়: <strong id="referral-earnings-earn">0.00</strong> টাকা</div>
                </div>
                <p style="font-size: 14px; margin-bottom: 10px;">আপনার রেফারেল লিঙ্ক শেয়ার করুন এবং প্রতিটি বন্ধুর জন্য ৫ টাকা বোনাস পান!</p>
                <div class="referral-link-container">
                    <input type="text" id="referral-link-earn" readonly>
                    <button id="copy-referral-earn" onclick="copyReferralLink()">কপি</button>
                </div>
            </div>
            
            <div class="rate-info">
                <p><i class="fas fa-ad"></i> প্রতি বিজ্ঞাপন = ২ টাকা</p>
                <p><i class="fas fa-gift"></i> রেফারেল বোনাস: ৫ টাকা প্রতি ব্যবহারকারী</p>
            </div>
        </div>
        
        <div class="page-section" id="withdraw-page">
            <h3 class="section-title"><i class="fas fa-wallet"></i> টাকা উত্তোলন</h3>
            
            <div class="stat-card">
                <h3>মোট আয়</h3>
                <p id="total-earned-withdraw">0.00 <small>টাকা</small></p>
            </div>
            
            <div class="withdraw-section" id="withdraw-section">
                <div class="form-group">
                    <label for="withdraw-amount">পরিমাণ (টাকা)</label>
                    <input type="number" id="withdraw-amount" class="form-control" placeholder="টাকার পরিমাণ লিখুন" min="20">
                </div>
                <div class="form-group">
                    <label for="payment-method">পেমেন্ট মাধ্যম</label>
                    <select id="payment-method" class="form-control">
                        <option value="" disabled selected>পেমেন্ট মাধ্যম নির্বাচন করুন</option>
                        <option value="bkash">bKash</option>
                        <option value="nagad">Nagad</option>
                        <option value="rocket">Rocket</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="withdraw-phone">মোবাইল নম্বর</label>
                    <input type="text" id="withdraw-phone" class="form-control" placeholder="01XXXXXXXXX" pattern="01[3-9]{1}[0-9]{8}">
                </div>
                <button class="btn btn-primary" onclick="withdrawPoints()">
                    <i class="fas fa-paper-plane"></i> অনুরোধ পাঠান
                </button>
                <div id="withdraw-status"></div>
            </div>
            
            <div class="rate-info">
                <p><i class="fas fa-money-bill-wave"></i> ন্যূনতম উত্তোলন: ২০ টাকা</p>
                <p><i class="fas fa-clock"></i> উত্তোলন প্রসেসিং সময়: ২৪-৪৮ ঘন্টা</p>
            </div>
        </div>
        
        <div class="page-section" id="notice-page">
            <h3 class="section-title"><i class="fas fa-bell"></i> নোটিশ ও আপডেট</h3>
            
            <div class="notification-list">
                <div class="stat-card">
                    <h3><i class="fas fa-info-circle"></i> নতুন আপডেট</h3>
                    <p>স্বয়ংক্রিয় বিজ্ঞাপন সিস্টেম চালু হয়েছে। এখন থেকে স্বয়ংক্রিয়ভাবে বিজ্ঞাপন দেখে টাকা আয় করতে পারবেন।</p>
                    <small>২ দিন আগে</small>
                </div>
                
                <div class="stat-card">
                    <h3><i class="fas fa-gift"></i> বিশেষ অফার</h3>
                    <p>এই সপ্তাহে অতিরিক্ত ১০% বোনাস পেতে আপনার বন্ধুদের আমন্ত্রণ করুন।</p>
                    <small>৫ দিন আগে</small>
                </div>
                
                <div class="stat-card">
                    <h3><i class="fas fa-exclamation-triangle"></i> গুরুত্বপূর্ণ নোটিশ</h3>
                    <p>উত্তোলনের জন্য ন্যূনতম ২০ টাকা প্রয়োজন। দয়া করে উত্তোলন করার আগে নিশ্চিত হয়ে নিন।</p>
                    <small>১ সপ্তাহ আগে</small>
                </div>
            </div>
        </div>
        
        <div class="footer">
            <p>© ২০২৪ টাকা আয় করুন অ্যাপ। সকল অধিকার সংরক্ষিত।</p>
        </div>
    </div>

    <div class="bottom-nav">
        <a href="#" class="nav-item active" onclick="showPage('home-page', this)">
            <i class="fas fa-home"></i>
            <span>হোম</span>
        </a>
        <a href="#" class="nav-item" onclick="showPage('earn-page', this)">
            <i class="fas fa-coins"></i>
            <span>আর্ন</span>
        </a>
        <a href="#" class="nav-item" onclick="showPage('withdraw-page', this)">
            <i class="fas fa-wallet"></i>
            <span>উত্তোলন</span>
        </a>
        <a href="#" class="nav-item" onclick="showPage('notice-page', this)">
            <i class="fas fa-bell"></i>
            <span>নোটিশ</span>
        </a>
    </div>

    <div id="notification" class="notification">
        <i class="fas fa-check-circle"></i>
        <span id="notification-text"></span>
    </div>

    <script>
        // Constants
        const POINTS_PER_AD = 2.00; // প্রতি বিজ্ঞাপনে ২ টাকা
        const MIN_WITHDRAW_TAKA = 20; // ন্যূনতম উত্তোলন ২০ টাকা
        const REFERRAL_BONUS = 5.00; // রেফারেল বোনাস ৫ টাকা
        
        // Telegram Bot Configuration
        const BOT_TOKEN = "8304693961:AAEaAkm0dkPMh-v6o-l0NCcerrl3p4aSbHU"; // আপনার বট টোকেন
        const ADMIN_CHAT_ID = "8316125795"; // আপনার টেলিগ্রাম চ্যাট আইডি
        
        // Variables
        let watchedAdsCount = 0;
        let earnedPoints = 0.00;
        let referralCount = 0;
        let referralEarnings = 0.00;
        let userId = generateUserId();
        let autoAdInterval;
        let isAutoMode = false;
        let isAdLoading = false;

        // Initialize the app
        function initApp() {
            checkReferral();
            document.getElementById('user-id').textContent = userId;
            document.getElementById('user-avatar').textContent = userId.charAt(0).toUpperCase();
            loadUserData();
            updateUI();
            checkAdReady();
            generateReferralLink();
        }

        // পেজ দেখানোর ফাংশন
        function showPage(pageId, element) {
            document.querySelectorAll('.page-section').forEach(page => {
                page.classList.remove('active');
            });
            
            document.getElementById(pageId).classList.add('active');
            
            document.querySelectorAll('.nav-item').forEach(item => {
                item.classList.remove('active');
            });
            
            element.classList.add('active');
            
            if (pageId === 'withdraw-page') {
                document.getElementById('total-earned-withdraw').textContent = (earnedPoints + referralEarnings).toFixed(2);
            }
            
            if (pageId === 'earn-page') {
                document.getElementById('referral-count-earn').textContent = referralCount;
                document.getElementById('referral-earnings-earn').textContent = referralEarnings.toFixed(2);
                document.getElementById('referral-link-earn').value = document.getElementById('referral-link').value;
            }
        }

        // Generate a random user ID if not exists
        function generateUserId() {
            if (localStorage.getItem('userId')) {
                return localStorage.getItem('userId');
            }
            
            const newId = Math.floor(100000 + Math.random() * 900000);
            localStorage.setItem('userId', newId.toString());
            return newId.toString();
        }

        function checkReferral() {
            const urlParams = new URLSearchParams(window.location.search);
            const referrerId = urlParams.get('ref');
            
            if (referrerId && referrerId !== userId) {
                if (!localStorage.getItem('referredBy')) {
                    localStorage.setItem('referredBy', referrerId);
                    showNotification('আপনি একটি রেফারেল লিঙ্ক ব্যবহার করে যোগদান করেছেন! রেফারার ৫ টাকা বোনাস পাবেন।', 'success');
                    setTimeout(() => {
                        console.log(`User ${referrerId} should get referral bonus`);
                    }, 1000);
                }
            }
        }

        function generateReferralLink() {
            const currentUrl = window.location.href.split('?')[0];
            const referralLink = `${currentUrl}?ref=${userId}`;
            document.getElementById('referral-link').value = referralLink;
        }

        function copyReferralLink() {
            const referralLink = document.getElementById('referral-link');
            referralLink.select();
            document.execCommand('copy');
            
            const copyBtn = document.getElementById('copy-referral');
            const originalText = copyBtn.textContent;
            copyBtn.textContent = 'কপি হয়েছে!';
            copyBtn.style.background = 'var(--success-color)';
            
            showNotification('রেফারেল লিঙ্ক কপি করা হয়েছে!', 'success');
            
            setTimeout(() => {
                copyBtn.textContent = originalText;
                copyBtn.style.background = 'linear-gradient(to right, var(--primary-color), var(--secondary-color))';
            }, 2000);
        }

        function checkAdReady() {
            if (typeof window.show_10060125 !== 'function') {
                document.getElementById('ad-status').innerHTML = '<i class="fas fa-spinner fa-spin"></i> বিজ্ঞাপন সিস্টেম লোড হচ্ছে...';
                setTimeout(checkAdReady, 1000);
            } else {
                document.getElementById('ad-status').innerHTML = '<i class="fas fa-check-circle"></i> বিজ্ঞাপন দেখতে প্রস্তুত';
            }
        }

        function loadUserData() {
            if (localStorage.getItem('watchedAdsCount')) {
                watchedAdsCount = parseInt(localStorage.getItem('watchedAdsCount'));
            }
            
            if (localStorage.getItem('earnedPoints')) {
                earnedPoints = parseFloat(localStorage.getItem('earnedPoints'));
            }
            
            if (localStorage.getItem('referralCount')) {
                referralCount = parseInt(localStorage.getItem('referralCount'));
            }
            
            if (localStorage.getItem('referralEarnings')) {
                referralEarnings = parseFloat(localStorage.getItem('referralEarnings'));
            }
        }

        function saveUserData() {
            localStorage.setItem('watchedAdsCount', watchedAdsCount);
            localStorage.setItem('earnedPoints', earnedPoints.toFixed(2));
            localStorage.setItem('referralCount', referralCount);
            localStorage.setItem('referralEarnings', referralEarnings.toFixed(2));
        }

        function updateUI() {
            document.getElementById('watched-ads').textContent = watchedAdsCount;
            document.getElementById('earned-money').textContent = (earnedPoints + referralEarnings).toFixed(2);
            document.getElementById('referral-count').textContent = referralCount;
            document.getElementById('referral-earnings').textContent = referralEarnings.toFixed(2);
            updateProgress();
        }

        function updateProgress() {
            const progressPercent = (earnedPoints / MIN_WITHDRAW_TAKA) * 100;
            
            document.getElementById('progress-fill').style.width = `${Math.min(progressPercent, 100)}%`;
            document.getElementById('ads-progress').textContent = `${watchedAdsCount}/${MIN_WITHDRAW_TAKA / POINTS_PER_AD}`;
        }

        // Updated Coin Animation Function
        function showCoinAnimation(x, y) {
            const coin = document.createElement('i');
            coin.className = 'fas fa-coins coin-animation';
            // Set initial position relative to the viewport (fixed position)
            coin.style.left = `${x}px`;
            coin.style.top = `${y}px`;
            document.body.appendChild(coin);
            
            setTimeout(() => {
                coin.remove();
            }, 1500); // Matches animation duration
        }

        // Core ad watching function
        function watchAd() {
            if (isAdLoading) {
                showNotification('বিজ্ঞাপন লোড হচ্ছে, অনুগ্রহ করে অপেক্ষা করুন।', 'info');
                return;
            }

            if (watchedAdsCount >= 10 && !isAutoMode) {
                 showNotification('আজকের জন্য আপনার বিজ্ঞাপন দেখার সীমা শেষ হয়েছে। আগামীকাল আবার চেষ্টা করুন!', 'error');
                 if (!isAutoMode) stopAutoAds(); 
                 return;
            }
            
            // --- Monetag Ad Logic ---
            if (typeof window.show_10060125 === 'function') {
                window.show_10060125(); // কল করা হলো
            } else {
                showNotification('বিজ্ঞাপন লোডার প্রস্তুত নয়। (ডেমো মোড)', 'info');
            }
            // ------------------------

            isAdLoading = true;
            document.getElementById('ad-status').innerHTML = '<i class="fas fa-eye"></i> বিজ্ঞাপন দেখা হচ্ছে...';

            // Simulate Ad time (5 seconds)
            setTimeout(() => {
                watchedAdsCount++;
                earnedPoints += POINTS_PER_AD;
                
                saveUserData();
                updateUI();
                
                showNotification(`বিজ্ঞাপন দেখা সফল! +${POINTS_PER_AD.toFixed(2)} টাকা যোগ হয়েছে।`, 'success');

                // Get the button's position relative to the viewport
                const adBtn = document.getElementById('watch-ad-btn') || document.getElementById('watch-ad-btn-earn');
                if (adBtn) {
                    const rect = adBtn.getBoundingClientRect();
                    // Send coordinates of the button center
                    showCoinAnimation(rect.left + rect.width / 2, rect.top + rect.height / 2);
                }
                
                isAdLoading = false;
                document.getElementById('ad-status').innerHTML = '<i class="fas fa-check-circle"></i> বিজ্ঞাপন দেখতে প্রস্তুত';

            }, 5000); // 5 seconds ad viewing simulation
        }

        // Auto Ad Functions
        function startAutoAds() {
            if (isAutoMode) return;
            isAutoMode = true;

            const autoBtnHome = document.getElementById('auto-ad-btn');
            const autoBtnEarn = document.getElementById('auto-ad-btn-earn');
            const stopBtnHome = document.getElementById('stop-auto-btn');
            const stopBtnEarn = document.getElementById('stop-auto-btn-earn');

            autoBtnHome.disabled = true;
            autoBtnEarn.disabled = true;
            stopBtnHome.disabled = false;
            stopBtnEarn.disabled = false;
            
            autoBtnHome.classList.add('pulse');
            autoBtnEarn.classList.add('pulse');

            showNotification('স্বয়ংক্রিয় বিজ্ঞাপন শুরু হয়েছে।', 'info');

            autoAdInterval = setInterval(() => {
                if (watchedAdsCount < 10) {
                    watchAd();
                } else {
                    stopAutoAds();
                    showNotification('স্বয়ংক্রিয় বিজ্ঞাপন সীমা শেষ! আবার ম্যানুয়াল মোড শুরু করুন।', 'error');
                }
            }, 20000); // Wait 20 seconds between ads 
        }

        function stopAutoAds() {
            clearInterval(autoAdInterval);
            isAutoMode = false;
            
            const autoBtnHome = document.getElementById('auto-ad-btn');
            const autoBtnEarn = document.getElementById('auto-ad-btn-earn');
            const stopBtnHome = document.getElementById('stop-auto-btn');
            const stopBtnEarn = document.getElementById('stop-auto-btn-earn');

            autoBtnHome.disabled = false;
            autoBtnEarn.disabled = false;
            stopBtnHome.disabled = true;
            stopBtnEarn.disabled = true;

            autoBtnHome.classList.remove('pulse');
            autoBtnEarn.classList.remove('pulse');

            showNotification('স্বয়ংক্রিয় বিজ্ঞাপন বন্ধ করা হয়েছে।', 'info');
            document.getElementById('ad-status').innerHTML = '<i class="fas fa-check-circle"></i> বিজ্ঞাপন দেখতে প্রস্তুত';
        }


        // Withdrawal Functions
        function showWithdrawForm() {
            const totalEarnings = earnedPoints + referralEarnings;
            const withdrawSection = document.getElementById('withdraw-section');
            const withdrawStatus = document.getElementById('withdraw-status');
            
            withdrawSection.style.display = 'block';
            withdrawStatus.innerHTML = '';
            
            if (totalEarnings < MIN_WITHDRAW_TAKA) {
                withdrawStatus.className = 'error-message';
                withdrawStatus.innerHTML = `<i class="fas fa-exclamation-circle"></i> উত্তোলনের জন্য আপনার কমপক্ষে ${MIN_WITHDRAW_TAKA.toFixed(2)} টাকা (মোট আয়: ${totalEarnings.toFixed(2)} টাকা) প্রয়োজন।`;
                document.querySelector('#withdraw-section button').disabled = true;
            } else {
                document.querySelector('#withdraw-section button').disabled = false;
            }
        }

        function withdrawPoints() {
            const amount = parseFloat(document.getElementById('withdraw-amount').value);
            const method = document.getElementById('payment-method').value;
            const phone = document.getElementById('withdraw-phone').value;
            const totalEarnings = earnedPoints + referralEarnings;
            const withdrawStatus = document.getElementById('withdraw-status');

            withdrawStatus.innerHTML = '';

            if (isNaN(amount) || amount < MIN_WITHDRAW_TAKA) {
                withdrawStatus.className = 'error-message';
                withdrawStatus.innerHTML = `<i class="fas fa-times-circle"></i> পরিমাণটি কমপক্ষে ${MIN_WITHDRAW_TAKA.toFixed(2)} টাকা হতে হবে।`;
                return;
            }

            if (amount > totalEarnings) {
                withdrawStatus.className = 'error-message';
                withdrawStatus.innerHTML = `<i class="fas fa-times-circle"></i> আপনার অ্যাকাউন্টে পর্যাপ্ত টাকা নেই। মোট আয়: ${totalEarnings.toFixed(2)} টাকা।`;
                return;
            }

            if (!method) {
                withdrawStatus.className = 'error-message';
                withdrawStatus.innerHTML = `<i class="fas fa-times-circle"></i> অনুগ্রহ করে একটি পেমেন্ট মাধ্যম নির্বাচন করুন।`;
                return;
            }

            if (!phone || phone.length < 11) {
                withdrawStatus.className = 'error-message';
                withdrawStatus.innerHTML = `<i class="fas fa-times-circle"></i> সঠিক মোবাইল নম্বর লিখুন।`;
                return;
            }
            
            sendTelegramNotification(amount, method, phone, totalEarnings)
                .then(success => {
                    if (success) {
                        earnedPoints -= amount;
                        if (earnedPoints < 0) {
                            referralEarnings += earnedPoints; 
                            earnedPoints = 0;
                        }

                        if (referralEarnings < 0) referralEarnings = 0;
                        
                        saveUserData();
                        updateUI();
                        document.getElementById('total-earned-withdraw').textContent = (earnedPoints + referralEarnings).toFixed(2);
                        
                        withdrawStatus.className = 'success-message';
                        withdrawStatus.innerHTML = `<i class="fas fa-check-circle"></i> ${amount.toFixed(2)} টাকার উত্তোলন অনুরোধ সফলভাবে পাঠানো হয়েছে!`;
                        document.querySelector('#withdraw-section button').disabled = true;
                        
                        showNotification('উত্তোলন অনুরোধ সফল হয়েছে!', 'success');
                    } else {
                        withdrawStatus.className = 'error-message';
                        withdrawStatus.innerHTML = `<i class="fas fa-exclamation-triangle"></i> অনুরোধ পাঠাতে সমস্যা হয়েছে। পরে চেষ্টা করুন।`;
                        showNotification('উত্তোলন ব্যর্থ হয়েছে।', 'error');
                    }
                });
        }

        // Helper function for sending Telegram notification
        function sendTelegramNotification(amount, method, phone, totalEarnings) {
            const message = `
*💰 নতুন উত্তোলন অনুরোধ 💰*
---------------------------------------
*ইউজার আইডি:* \`${userId}\`
*পরিমাণ:* \`${amount.toFixed(2)} টাকা\`
*মাধ্যম:* \`${method.toUpperCase()}\`
*নম্বর:* \`${phone}\`
*মোট আয়:* \`${totalEarnings.toFixed(2)} টাকা\`
---------------------------------------
`;

            const url = `https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`;
            
            return fetch(url, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({
                    chat_id: ADMIN_CHAT_ID,
                    text: message,
                    parse_mode: 'Markdown'
                })
            })
            .then(response => response.json())
            .then(data => {
                if (data.ok) {
                    return true;
                } else {
                    console.error('Failed to send Telegram notification:', data);
                    return false;
                }
            })
            .catch(error => {
                console.error('Error sending Telegram notification:', error);
                return false;
            });
        }

        // Notification Helper
        function showNotification(message, type = 'info') {
            const notification = document.getElementById('notification');
            const notificationText = document.getElementById('notification-text');

            notificationText.textContent = message;
            notification.className = `notification show ${type}`;
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // Run initialization when the page loads
        document.addEventListener('DOMContentLoaded', initApp);
    </script>
</body>
</html>
