# laptop-web
laptop web
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TECHCORE - Watches, Laptops & Phones</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Archivo+Black&display=swap" rel="stylesheet">
    <style>
        :root {
            --black: #0a0a0a;
            --white: #fafafa;
            --accent: #00ff88;
            --gray: #808080;
            --border: #2a2a2a;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'JetBrains Mono', monospace;
            background: var(--black);
            color: var(--white);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: var(--black);
            border-bottom: 2px solid var(--accent);
            padding: 1.5rem 2rem;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-family: 'Archivo Black', sans-serif;
            font-size: 1.8rem;
            color: var(--accent);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 1px;
            position: relative;
            transition: color 0.3s;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        /* Hero Section */
        .hero {
            margin-top: 80px;
            height: 90vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, var(--black) 0%, #1a1a1a 100%);
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            animation: fadeInUp 1s ease-out;
        }

        .hero h1 {
            font-family: 'Archivo Black', sans-serif;
            font-size: 5rem;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            animation: glitch 3s infinite;
        }

        .hero-accent {
            color: var(--accent);
            display: block;
            font-size: 6rem;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 2rem;
            letter-spacing: 2px;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: var(--accent);
            color: var(--black);
            text-decoration: none;
            text-transform: uppercase;
            font-weight: bold;
            letter-spacing: 2px;
            border: none;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--white);
            transition: left 0.3s;
        }

        .cta-button:hover::before {
            left: 0;
        }

        .cta-button span {
            position: relative;
            z-index: 1;
        }

        /* Grid Background Animation */
        .grid-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(var(--border) 1px, transparent 1px),
                linear-gradient(90deg, var(--border) 1px, transparent 1px);
            background-size: 50px 50px;
            opacity: 0.3;
            animation: gridMove 20s linear infinite;
        }

        @keyframes gridMove {
            0% { transform: translateY(0); }
            100% { transform: translateY(50px); }
        }

        /* Category Section */
        .categories {
            padding: 5rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            font-family: 'Archivo Black', sans-serif;
            font-size: 3rem;
            text-align: center;
            margin-bottom: 3rem;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .category-card {
            background: linear-gradient(135deg, #1a1a1a 0%, #0f0f0f 100%);
            border: 2px solid var(--border);
            padding: 2rem;
            position: relative;
            overflow: hidden;
            transition: all 0.4s;
            cursor: pointer;
        }

        .category-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, var(--accent), transparent);
            opacity: 0;
            transition: opacity 0.4s;
            z-index: 0;
        }

        .category-card:hover::before {
            opacity: 0.3;
        }

        .category-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent);
        }

        .category-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
        }

        .category-card h3 {
            font-family: 'Archivo Black', sans-serif;
            font-size: 2rem;
            margin-bottom: 1rem;
            text-transform: uppercase;
            position: relative;
            z-index: 1;
        }

        .category-card p {
            color: var(--gray);
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 1;
        }

        .category-link {
            color: var(--accent);
            text-decoration: none;
            text-transform: uppercase;
            font-weight: bold;
            letter-spacing: 1px;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            position: relative;
            z-index: 1;
        }

        .category-link::after {
            content: '→';
            transition: transform 0.3s;
        }

        .category-card:hover .category-link::after {
            transform: translateX(5px);
        }

        /* Products Section */
        .products {
            padding: 5rem 2rem;
            background: #0f0f0f;
        }

        .products-container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .product-card {
            background: var(--black);
            border: 1px solid var(--border);
            overflow: hidden;
            transition: all 0.3s;
            position: relative;
        }

        .product-card:hover {
            border-color: var(--accent);
            box-shadow: 0 10px 40px rgba(0, 255, 136, 0.2);
        }

        .product-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #1a1a1a, #2a2a2a);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            border-bottom: 1px solid var(--border);
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-info h4 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .product-price {
            color: var(--accent);
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        .product-description {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .add-to-cart {
            width: 100%;
            padding: 0.8rem;
            background: transparent;
            color: var(--accent);
            border: 2px solid var(--accent);
            text-transform: uppercase;
            font-family: 'JetBrains Mono', monospace;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .add-to-cart:hover {
            background: var(--accent);
            color: var(--black);
        }

        /* Features Section */
        .features {
            padding: 5rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }

        .feature {
            text-align: center;
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--accent);
        }

        .feature h4 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
        }

        .feature p {
            color: var(--gray);
        }

        /* Footer */
        footer {
            background: var(--black);
            border-top: 2px solid var(--accent);
            padding: 3rem 2rem;
            text-align: center;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: var(--gray);
            text-decoration: none;
            text-transform: uppercase;
            font-size: 0.9rem;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--accent);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes glitch {
            0%, 90%, 100% {
                text-shadow: none;
            }
            92% {
                text-shadow: 3px 0 var(--accent), -3px 0 #ff0088;
            }
            94% {
                text-shadow: -3px 0 var(--accent), 3px 0 #ff0088;
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 3rem;
            }

            .hero-accent {
                font-size: 3.5rem;
            }

            .nav-links {
                gap: 1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .category-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">TECHCORE</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#categories">Categories</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="grid-bg"></div>
        <div class="hero-content">
            <h1>
                PREMIUM TECH
                <span class="hero-accent">REDEFINED</span>
            </h1>
            <p>Watches • Laptops • Phones</p>
            <a href="#products" class="cta-button"><span>EXPLORE NOW</span></a>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories" id="categories">
        <h2 class="section-title">Browse by Category</h2>
        <div class="category-grid">
            <div class="category-card">
                <div class="category-icon">⌚</div>
                <h3>Watches</h3>
                <p>Discover premium smartwatches and luxury timepieces that blend style with cutting-edge technology.</p>
                <a href="#products" class="category-link">View Collection</a>
            </div>

            <div class="category-card">
                <div class="category-icon">💻</div>
                <h3>Laptops</h3>
                <p>High-performance laptops for work, gaming, and creativity. Power meets portability.</p>
                <a href="#products" class="category-link">View Collection</a>
            </div>

            <div class="category-card">
                <div class="category-icon">📱</div>
                <h3>Phones</h3>
                <p>Latest smartphones with cutting-edge features, stunning displays, and powerful cameras.</p>
                <a href="#products" class="category-link">View Collection</a>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <div class="products-container">
            <h2 class="section-title">Featured Products</h2>
            <div class="product-grid">
                <!-- Watch Products -->
                <div class="product-card">
                    <div class="product-image">⌚</div>
                    <div class="product-info">
                        <h4>Smart Watch Pro</h4>
                        <div class="product-price">$399</div>
                        <p class="product-description">Fitness tracking, heart rate monitor, GPS, waterproof design.</p>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">⌚</div>
                    <div class="product-info">
                        <h4>Luxury Chrono</h4>
                        <div class="product-price">$899</div>
                        <p class="product-description">Premium mechanical watch with sapphire crystal and leather strap.</p>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <!-- Laptop Products -->
                <div class="product-card">
                    <div class="product-image">💻</div>
                    <div class="product-info">
                        <h4>UltraBook X1</h4>
                        <div class="product-price">$1,299</div>
                        <p class="product-description">Intel i7, 16GB RAM, 512GB SSD, 14" 4K display, ultralight design.</p>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">💻</div>
                    <div class="product-info">
                        <h4>Gaming Beast</h4>
                        <div class="product-price">$2,499</div>
                        <p class="product-description">RTX 4070, Intel i9, 32GB RAM, 1TB SSD, RGB keyboard, 17" display.</p>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <!-- Phone Products -->
                <div class="product-card">
                    <div class="product-image">📱</div>
                    <div class="product-info">
                        <h4>Pixel Pro Max</h4>
                        <div class="product-price">$999</div>
                        <p class="product-description">6.7" OLED, 256GB, 50MP camera, 5G, all-day battery life.</p>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">📱</div>
                    <div class="product-info">
                        <h4>Quantum Phone</h4>
                        <div class="product-price">$799</div>
                        <p class="product-description">6.5" display, 128GB, triple camera, fast charging, sleek design.</p>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <h2 class="section-title">Why Choose TechCore</h2>
        <div class="features-grid">
            <div class="feature">
                <div class="feature-icon">🚚</div>
                <h4>Free Shipping</h4>
                <p>Free delivery on all orders over $100</p>
            </div>

            <div class="feature">
                <div class="feature-icon">🔒</div>
                <h4>Secure Payment</h4>
                <p>100% secure payment processing</p>
            </div>

            <div class="feature">
                <div class="feature-icon">↩️</div>
                <h4>Easy Returns</h4>
                <p>30-day money-back guarantee</p>
            </div>

            <div class="feature">
                <div class="feature-icon">⚡</div>
                <h4>Fast Support</h4>
                <p>24/7 customer service available</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <div class="footer-links">
                <a href="#home">Home</a>
                <a href="#categories">Categories</a>
                <a href="#products">Products</a>
                <a href="#about">About Us</a>
                <a href="#privacy">Privacy Policy</a>
                <a href="#terms">Terms & Conditions</a>
            </div>
            <p style="color: var(--gray); margin-top: 2rem;">
                © 2026 TECHCORE. All rights reserved.
            </p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add to cart functionality
        document.querySelectorAll('.add-to-cart').forEach(button => {
            button.addEventListener('click', function() {
                const productName = this.closest('.product-info').querySelector('h4').textContent;
                alert(`${productName} added to cart!`);
                this.textContent = 'Added ✓';
                this.style.background = 'var(--accent)';
                this.style.color = 'var(--black)';
                
                setTimeout(() => {
                    this.textContent = 'Add to Cart';
                    this.style.background = 'transparent';
                    this.style.color = 'var(--accent)';
                }, 2000);
            });
        });

        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.6s ease-out forwards';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.category-card, .product-card, .feature').forEach(el => {
            el.style.opacity = '0';
            observer.observe(el);
        });
    </script>
</body>
</html>
