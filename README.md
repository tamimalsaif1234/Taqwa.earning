# Taqwa.earning
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>তাকওয়া আরন্স ডট কম - মাইক্রো জব সাইট</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', Arial, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }
        
        header {
            background-color: #4285F4;
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 100%;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .logo {
            font-size: 1.2rem;
            font-weight: bold;
        }
        
        .menu-btn {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .menu-overlay {
            position: fixed;
            top: 0;
            right: -300px;
            width: 300px;
            height: 100%;
            background-color: white;
            box-shadow: -2px 0 5px rgba(0,0,0,0.2);
            transition: right 0.3s ease;
            z-index: 1001;
            padding-top: 60px;
        }
        
        .menu-overlay.active {
            right: 0;
        }
        
        .menu-links {
            list-style: none;
        }
        
        .menu-links li {
            padding: 15px 20px;
            border-bottom: 1px solid #eee;
        }
        
        .menu-links a {
            color: #333;
            text-decoration: none;
            display: block;
        }
        
        .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .container {
            max-width: 100%;
            margin: 70px auto 20px;
            padding: 15px;
        }
        
        .card {
            background: white;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            padding: 15px;
            margin-bottom: 15px;
        }
        
        .btn {
            display: inline-block;
            background: #4285F4;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            text-decoration: none;
            margin-top: 10px;
            font-size: 0.9rem;
        }
        
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
            z-index: 1000;
            display: none;
        }
        
        .overlay.active {
            display: block;
        }
        
        .section-title {
            margin-bottom: 15px;
            color: #4285F4;
        }
        
        .hidden {
            display: none;
        }
        
        /* ফর্ম স্টাইল */
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        .form-group input, 
        .form-group select, 
        .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        /* টাস্ক লিস্ট স্টাইল */
        .task-item {
            border-bottom: 1px solid #eee;
            padding: 15px 0;
        }
        
        .task-item:last-child {
            border-bottom: none;
        }
        
        /* প্রোফাইল স্টাইল */
        .profile-header {
            text-align: center;
            margin-bottom: 20px;
        }
        
        .profile-pic {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            margin: 0 auto 10px;
            background-color: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: #666;
        }
        
        /* এডমিন ড্যাশবোর্ড স্টাইল */
        .stats-card {
            text-align: center;
            padding: 20px;
            background-color: #f9f9f9;
            border-radius: 5px;
            margin-bottom: 15px;
        }
        
        .stats-number {
            font-size: 2rem;
            font-weight: bold;
            color: #4285F4;
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content">
            <div class="logo">তাকওয়া আরন্স ডট কম</div>
            <button class="menu-btn" onclick="toggleMenu()">☰</button>
        </div>
    </header>

    <!-- মেনু ওভারলে -->
    <div class="overlay" id="overlay" onclick="toggleMenu()"></div>
    
    <div class="menu-overlay" id="menuOverlay">
        <button class="close-btn" onclick="toggleMenu()">×</button>
        <ul class="menu-links">
            <li><a href="#" onclick="showPage('home')">হোম</a></li>
            <li><a href="#" onclick="showPage('login')">লগইন</a></li>
            <li><a href="#" onclick="showPage('register')">রেজিস্টার</a></li>
            <li><a href="#" onclick="showPage('deposit')">ডিপোজিট</a></li>
            <li><a href="#" onclick="showPage('payout')">পেআউট</a></li>
            <li><a href="#" onclick="showPage('job')">জব সাবমিশন</a></li>
            <li><a href="#" onclick="showPage('tasks')">টাস্ক লিস্ট</a></li>
            <li><a href="#" onclick="showPage('profile')">ইউজার প্রোফাইল</a></li>
            <li><a href="#" onclick="showPage('admin')">এডমিন প্যানেল</a></li>
        </ul>
    </div>

    <!-- হোম পেজ -->
    <div id="home" class="page container">
        <div class="card">
            <h2 class="section-title">ফ্রিল্যান্সিং কি?</h2>
            <p>ফ্রিল্যান্সিং হলো স্বাধীনভাবে কাজ করার একটি পদ্ধতি যেখানে একজন ব্যক্তি বিভিন্ন ক্লায়েন্টের জন্য প্রকল্পভিত্তিক কাজ করে থাকেন। ফ্রিল্যান্সাররা সাধারণত স্বনিযুক্ত হন এবং একসাথে একাধিক ক্লায়েন্টের জন্য কাজ করতে পারেন।</p>
        </div>

        <div class="card">
            <h2 class="section-title">ফ্রিল্যান্সিং এর সুবিধা</h2>
            <ul>
                <li>নমনীয় কাজের সময়সূচী</li>
                <li>ঘরে বসে আয়ের সুযোগ</li>
                <li>বিভিন্ন ধরনের প্রকল্পে কাজের অভিজ্ঞতা</li>
                <li>আন্তর্জাতিক ক্লায়েন্টের সাথে কাজ করার সুযোগ</li>
                <li>স্বাধীনভাবে কাজ করার স্বাধীনতা</li>
            </ul>
        </div>

        <div class="card">
            <h2 class="section-title">চলতি কাজগুলি</h2>
            
            <div class="task-item">
                <h3>লোগো ডিজাইন প্রয়োজন</h3>
                <p>আমাদের কোম্পানির জন্য একটি মডার্ন লোগো ডিজাইন প্রয়োজন।</p>
                <p class="job-price">৳1,500</p>
            </div>
            
            <div class="task-item">
                <h3>ব্লগ পোস্ট লেখা</h3>
                <p>প্রযুক্তি বিষয়ক ৫০০ শব্দের একটি ব্লগ পোস্ট প্রয়োজন।</p>
                <p class="job-price">৳800</p>
            </div>
        </div>

        <div class="card" style="text-align: center;">
            <h2>আপনি কি কাজ করতে আগ্রহী?</h2>
            <p>তাহলে এখনই রেজিস্টার করুন এবং ফ্রিল্যান্সিং জগতে আপনার যাত্রা শুরু করুন</p>
            <a href="#" onclick="showPage('login')" class="btn">লগইন</a>
            <a href="#" onclick="showPage('register')" class="btn">রেজিস্টার</a>
        </div>
    </div>

    <!-- লগইন পেজ -->
    <div id="login" class="page container hidden">
        <div class="card">
            <h2 class="section-title">লগইন</h2>
            <form>
                <div class="form-group">
                    <label for="login-email">ইমেইল</label>
                    <input type="email" id="login-email" placeholder="আপনার ইমেইল ঠিকানা লিখুন">
                </div>
                <div class="form-group">
                    <label for="login-password">পাসওয়ার্ড</label>
                    <input type="password" id="login-password" placeholder="আপনার পাসওয়ার্ড লিখুন">
                </div>
                <button type="submit" class="btn">লগইন</button>
            </form>
            <p style="text-align: center; margin-top: 15px;">
                অ্যাকাউন্ট নেই? <a href="#" onclick="showPage('register')">রেজিস্টার করুন</a>
            </p>
        </div>
    </div>

    <!-- রেজিস্টার পেজ -->
    <div id="register" class="page container hidden">
        <div class="card">
            <h2 class="section-title">রেজিস্টার</h2>
            <form>
                <div class="form-group">
                    <label for="reg-name">পূর্ণ নাম</label>
                    <input type="text" id="reg-name" placeholder="আপনার পূর্ণ নাম লিখুন">
                </div>
                <div class="form-group">
                    <label for="reg-email">ইমেইল</label>
                    <input type="email" id="reg-email" placeholder="আপনার ইমেইল ঠিকানা লিখুন">
                </div>
                <div class="form-group">
                    <label for="reg-password">পাসওয়ার্ড</label>
                    <input type="password" id="reg-password" placeholder="একটি শক্তিশালী পাসওয়ার্ড তৈরি করুন">
                </div>
                <div class="form-group">
                    <label for="reg-confirm-password">পাসওয়ার্ড নিশ্চিত করুন</label>
                    <input type="password" id="reg-confirm-password" placeholder="পাসওয়ার্ডটি আবার লিখুন">
                </div>
                <button type="submit" class="btn">রেজিস্টার করুন</button>
            </form>
            <p style="text-align: center; margin-top: 15px;">
                ইতিমধ্যে অ্যাকাউন্ট আছে? <a href="#" onclick="showPage('login')">লগইন করুন</a>
            </p>
        </div>
    </div>

    <!-- ডিপোজিট পেজ -->
    <div id="deposit" class="page container hidden">
        <div class="card">
            <h2 class="section-title">ডিপোজিট ফান্ড</h2>
            <p>আপনার অ্যাকাউন্টে ফান্ড ডিপোজিট করুন এবং কাজ শুরু করুন</p>
            
            <div class="form-group">
                <label for="deposit-amount">ডিপোজিট অ্যামাউন্ট</label>
                <input type="number" id="deposit-amount" placeholder="টাকার পরিমাণ লিখুন">
            </div>
            <div class="form-group">
                <label for="payment-method">পেমেন্ট মেথড</label>
                <select id="payment-method">
                    <option value="">পেমেন্ট মেথড নির্বাচন করুন</option>
                    <option value="bkash">bKash</option>
                    <option value="nagad">Nagad</option>
                    <option value="rocket">Rocket</option>
                    <option value="bank">ব্যাংক ট্রান্সফার</option>
                </select>
            </div>
            <button type="submit" class="btn">ডিপোজিট করুন</button>
        </div>
    </div>

    <!-- পেআউট পেজ -->
    <div id="payout" class="page container hidden">
        <div class="card">
            <h2 class="section-title">পেআউট রিকুয়েস্ট</h2>
            <p>আপনার আয়ের টাকা উত্তোলন করুন</p>
            
            <div class="form-group">
                <label for="payout-amount">উত্তোলন অ্যামাউন্ট</label>
                <input type="number" id="payout-amount" placeholder="উত্তোলন করতে চান এমন অ্যামাউন্ট লিখুন">
            </div>
            <div class="form-group">
                <label for="payout-method">পেমেন্ট মেথড</label>
                <select id="payout-method">
                    <option value="">পেমেন্ট মেথড নির্বাচন করুন</option>
                    <option value="bkash">bKash</option>
                    <option value="nagad">Nagad</option>
                    <option value="rocket">Rocket</option>
                    <option value="bank">ব্যাংক ট্রান্সফার</option>
                </select>
            </div>
            <div class="form-group">
                <label for="account-details">অ্যাকাউন্ট ডিটেইলস</label>
                <input type="text" id="account-details" placeholder="আপনার পেমেন্ট অ্যাকাউন্ট নম্বর লিখুন">
            </div>
            <button type="submit" class="btn">পেআউট রিকুয়েস্ট করুন</button>
        </div>
    </div>

    <!-- জব সাবমিশন পেজ -->
    <div id="job" class="page container hidden">
        <div class="card">
            <h2 class="section-title">জব সাবমিশন</h2>
            <p>আপনার সম্পন্ন কাজ জমা দিন এবং পেমেন্ট গ্রহণ করুন</p>
            
            <form>
                <div class="form-group">
                    <label for="job-title">জব টাইটেল</label>
                    <input type="text" id="job-title" placeholder="কাজের শিরোনাম লিখুন">
                </div>
                <div class="form-group">
                    <label for="job-description">কাজের বিবরণ</label>
                    <textarea id="job-description" rows="5" placeholder="কাজের বিস্তারিত বিবরণ লিখুন"></textarea>
                </div>
                <div class="form-group">
                    <label for="job-attachment">ফাইল সংযুক্ত করুন</label>
                    <input type="file" id="job-attachment">
                </div>
                <button type="submit" class="btn">জমা দিন</button>
            </form>
        </div>
    </div>

    <!-- টাস্ক লিস্ট পেজ -->
    <div id="tasks" class="page container hidden">
        <div class="card">
            <h2 class="section-title">টাস্ক লিস্ট</h2>
            <p>আপনার বর্তমান টাস্কগুলির তালিকা</p>
            
            <div class="task-item">
                <h3>ওয়েবসাইট ডিজাইন</h3>
                <p>ক্লায়েন্ট: জন ডো</p>
                <p>স্ট্যাটাস: প্রগ্রেস</p>
                <p>ডেডলাইন: ৩০ নভেম্বর, ২০২৩</p>
                <a href="#" class="btn">ডিটেইলস</a>
            </div>
            
            <div class="task-item">
                <h3>লোগো ডিজাইন</h3>
                <p>ক্লায়েন্ট: স্মিথ কর্পোরেশন</p>
                <p>স্ট্যাটাস: পেন্ডিং</p>
                <p>ডেডলাইন: ১৫ ডিসেম্বর, ২০২৩</p>
                <a href="#" class="btn">ডিটেইলস</a>
            </div>
        </div>
    </div>

    <!-- ইউজার প্রোফাইল পেজ -->
    <div id="profile" class="page container hidden">
        <div class="card">
            <div class="profile-header">
                <div class="profile-pic">AR</div>
                <h2>আহমেদ রহমান</h2>
                <p>ওয়েব ডেভেলপার</p>
            </div>
            
            <div class="form-group">
                <label>ইমেইল</label>
                <p>ahmed@example.com</p>
            </div>
            
            <div class="form-group">
                <label>ফোন</label>
                <p>+8801XXXXXXXXX</p>
            </div>
            
            <div class="form-group">
                <label>ঠিকানা</label>
                <p>ঢাকা, বাংলাদেশ</p>
            </div>
            
            <div class="form-group">
                <label>দক্ষতা</label>
                <p>HTML, CSS, JavaScript, PHP, MySQL</p>
            </div>
            
            <a href="#" class="btn">প্রোফাইল এডিট করুন</a>
        </div>
    </div>

    <!-- এডমিন প্যানেল পেজ -->
    <div id="admin" class="page container hidden">
        <div class="card">
            <h2 class="section-title">এডমিন প্যানেল</h2>
            
            <div style="display: flex; gap: 15px; margin-bottom: 20px;">
                <div class="stats-card" style="flex: 1;">
                    <div class="stats-number">1,245</div>
                    <div>মোট ব্যবহারকারী</div>
                </div>
                <div class="stats-card" style="flex: 1;">
                    <div class="stats-number">367</div>
                    <div>সক্রিয় প্রকল্প</div>
                </div>
            </div>
            
            <h3>সাম্প্রতিক কার্যকলাপ</h3>
            <div class="task-item">
                <p><strong>নতুন ব্যবহারকারী রেজিস্টার</strong></p>
                <p>১০ মিনিট আগে</p>
            </div>
            <div class="task-item">
                <p><strong>পেমেন্ট ডিপোজিট</strong></p>
                <p>২৫ মিনিট আগে</p>
            </div>
            
            <div style="margin-top: 20px;">
                <a href="#" class="btn">ব্যবহারকারী ম্যানেজমেন্ট</a>
                <a href="#" class="btn">প্রকল্প মডারেশন</a>
            </div>
        </div>
    </div>

    <script>
        // মেনু টগল ফাংশন
        function toggleMenu() {
            document.getElementById('menuOverlay').classList.toggle('active');
            document.getElementById('overlay').classList.toggle('active');
        }
        
        // পেজ দেখানোর ফাংশন
        function showPage(pageId) {
            // সব পেজ লুকানো
            document.querySelectorAll('.page').forEach(page => {
                page.classList.add('hidden');
            });
            
            // নির্বাচিত পেজ দেখানো
            document.getElementById(pageId).classList.remove('hidden');
            
            // মেনু বন্ধ করা
            toggleMenu();
        }
    </script>
</body>
</html>
