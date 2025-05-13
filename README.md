<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TopMyst - Setting new trends</title>
    <style>
        /* 全局样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', 'Microsoft YaHei', sans-serif;
        }
        
        body {
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* 导航栏 */
        header {
            background-color: #1a1a2e;
            color: white;
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        nav {
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
        
        .logo img {
            height: 40px;
            margin-right: 10px;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 30px;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: #4cc9f0;
        }
        
        /* 英雄区域 */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1518770660439-4636190af475?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            height: 80vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: white;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            animation: fadeIn 1.5s ease-in-out;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            animation: fadeIn 2s ease-in-out;
        }
        
        .btn {
            display: inline-block;
            background-color: #4cc9f0;
            color: white;
            padding: 12px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
            animation: fadeIn 2.5s ease-in-out;
        }
        
        .btn:hover {
            background-color: #3aa8d8;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        /* 关于我们 */
        .about {
            padding: 80px 0;
            background-color: white;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            font-size: 36px;
            color: #1a1a2e;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: #4cc9f0;
            margin: 15px auto;
        }
        
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-image {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            transition: transform 0.5s;
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        /* 产品展示 */
        .products {
            padding: 80px 0;
            background-color: #f5f7fa;
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        
        .product-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .product-image {
            height: 250px;
            overflow: hidden;
        }
        
        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .product-card:hover .product-image img {
            transform: scale(1.1);
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-info h3 {
            font-size: 22px;
            margin-bottom: 10px;
            color: #1a1a2e;
        }
        
        .product-info p {
            color: #666;
            margin-bottom: 15px;
        }
        
        .product-price {
            font-size: 20px;
            font-weight: bold;
            color: #4cc9f0;
        }
        
        /* 联系我们 */
        .contact {
            padding: 80px 0;
            background-color: white;
        }
        
        .contact-container {
            display: flex;
            gap: 50px;
        }
        
        .contact-info {
            flex: 1;
        }
        
        .contact-info h3 {
            font-size: 24px;
            margin-bottom: 20px;
            color: #1a1a2e;
        }
        
        .contact-info p {
            margin-bottom: 15px;
        }
        
        .contact-info i {
            color: #4cc9f0;
            margin-right: 10px;
            width: 20px;
            text-align: center;
        }
        
        .contact-form {
            flex: 1;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        
        .form-group textarea {
            height: 150px;
        }
        
        .submit-btn {
            background-color: #4cc9f0;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .submit-btn:hover {
            background-color: #3aa8d8;
        }
        
        /* 页脚 */
        footer {
            background-color: #1a1a2e;
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            margin-bottom: 40px;
        }
        
        .footer-column {
            flex: 1;
            padding: 0 20px;
        }
        
        .footer-column h3 {
            font-size: 20px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: #4cc9f0;
        }
        
        .footer-column p {
            margin-bottom: 15px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            color: white;
            font-size: 20px;
            transition: color 0.3s;
        }
        
        .social-links a:hover {
            color: #4cc9f0;
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* 动画 */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .about-content {
                flex-direction: column;
            }
            
            .contact-container {
                flex-direction: column;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 30px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- 导航栏 -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <img src="https://via.placeholder.com/40x40" alt="TopMyst">
                    <span>TopMyst</span>
                </div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Innovative Entertainment</h1>
                <p>TopMyst is committed to providing high-quality toys to customers around the world, so that children can grow up with fun!</p>
                <a href="#products" class="btn">Explore Products</a>
            </div>
        </div>
    </section>

    <!-- 关于我们 -->
    <section class="about" id="about">
        <div class="container">
            <h2 class="section-title">About TopMyst</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>TopMyst is a toy company that specializes in healthy entertainment for kids. We have a team of experienced engineers and designers dedicated to creating innovative and fun toys.</p>
                    <p>Our mission is to "bring more happiness to children" and our vision is to be the leading toy brand in the world.</p>
                                 </div>
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="TopMyst Office">
                </div>
            </div>
        </div>
    </section>

    <!-- 产品展示 -->
    <section class="products" id="products">
        <div class="container">
            <h2 class="section-title">Our Products</h2>
            <div class="product-grid">
                <!-- 产品1 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1546054454-aa26e2b734c7?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="智能手表">
                    </div>
                    <div class="product-info">
                        <h3>星辰智能手表Pro</h3>
                        <p>全新升级的健康监测系统，支持血氧、心率、睡眠监测，30天超长续航。</p>
                        <div class="product-price">￥1299</div>
                    </div>
                </div>
                
                <!-- 产品2 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1592899677977-9c10ca588bbd?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="无线耳机">
                    </div>
                    <div class="product-info">
                        <h3>星辰无线耳机Air</h3>
                        <p>主动降噪技术，Hi-Fi音质，24小时续航，IPX5防水等级。</p>
                        <div class="product-price">￥799</div>
                    </div>
                </div>
                
                <!-- 产品3 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1585771724684-38269d6639fd?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="智能音箱">
                    </div>
                    <div class="product-info">
                        <h3>星辰智能音箱X</h3>
                        <p>360°环绕音效，AI语音助手，智能家居控制中心。</p>
                        <div class="product-price">￥599</div>
                    </div>
                </div>
                
                <!-- 产品4 -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1592155931584-901ac15763e3?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="智能灯泡">
                    </div>
                    <div class="product-info">
                        <h3>星辰智能灯泡</h3>
                        <p>1600万色可选，语音控制，定时开关，节能环保。</p>
                        <div class="product-price">￥129</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 联系我们 -->
    <section class="contact" id="contact">
        <div class="container">
            <h2 class="section-title">Contact us</h2>
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Contact details</h3>
                   
                    <p><i class="fas fa-envelope"></i> haihua@topmyst.cn</p>
                   
                    <h3 style="margin-top: 30px;">Follow us</h3>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-weixin"></i></a>
                        <a href="#"><i class="fab fa-weibo"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                
                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Phone</label>
                            <input type="tel" id="phone">
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" required></textarea>
                        </div>
                        <button type="submit" class="submit-btn">Sent</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>About TopMyst</h3>
                    <p>TopMyst is committed to providing high-quality toys to customers around the world, so that children can grow up with fun!</p>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <p><a href="#home" style="color: white; text-decoration: none;">Home page</a></p>
                    <p><a href="#about" style="color: white; text-decoration: none;">About us</a></p>
                    <p><a href="#products" style="color: white; text-decoration: none;">Product center</a></p>
                    <p><a href="#contact" style="color: white; text-decoration: none;">Contact us</a></p>
                </div>
                <div class="footer-column">
                    <h3>Subscribe to us</h3>
                    <p>Subscribe to our newsletter for the latest product information and special offers.</p>
                    <div class="form-group" style="margin-top: 15px;">
                        <input type="email" placeholder="Your e-mail address" style="width: 100%; padding: 10px; border-radius: 5px; border: none;">
                    </div>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 TopMyst.</p>
            </div>
        </div>
    </footer>
</body>
</html>
