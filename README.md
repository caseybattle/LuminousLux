<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LUMINOUS LUX | Premium Artisan Candles</title>
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant:wght@400;500;600&family=Montserrat:wght@300;400;500&family=Playfair+Display:wght@400;500&display=swap" rel="stylesheet">
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Favicon -->
    <link rel="icon" type="image/png" href="https://placehold.co/32x32">
    
    <!-- GSAP -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    
    <!-- Swiper -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.css" />
    <script src="https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.js"></script>
    
    <style>
        :root {
            --primary: #7a6a58;
            --secondary: #f6f4f0;
            --accent: #d8c8b8;
            --dark: #2e2a26;
            --text: #333333;
            --light-text: #f8f5f2;
            --border: 1px solid rgba(0,0,0,0.1);
            --transition: 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            --font-heading: 'Playfair Display', serif;
            --font-subheading: 'Cormorant', serif;
            --font-body: 'Montserrat', sans-serif;
            --shadow-sm: 0 1px 3px rgba(0,0,0,0.05);
            --shadow-md: 0 4px 12px rgba(0,0,0,0.08);
            --shadow-lg: 0 15px 40px rgba(0,0,0,0.12);
            --section-spacing: 120px;
            --container-max: 1480px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: var(--font-body);
            color: var(--text);
            line-height: 1.6;
            background-color: var(--secondary);
            overscroll-behavior: none;
            -webkit-font-smoothing: antialiased;
        }
        
        h1, h2, h3, h4, h5 {
            font-family: var(--font-heading);
            font-weight: 500;
            letter-spacing: 0.5px;
        }
        
        h6 {
            font-family: var(--font-subheading);
            font-weight: 500;
        }
        
        a {
            text-decoration: none;
            color: inherit;
            transition: var(--transition);
        }
        
        button {
            cursor: pointer;
            font-family: var(--font-body);
            transition: var(--transition);
            background: none;
            border: none;
        }
        
        .container {
            max-width: var(--container-max);
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
        }
        
        .section {
            padding: var(--section-spacing) 0;
            position: relative;
        }
        
        .section-title {
            font-size: clamp(2rem, 5vw, 3.5rem);
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
            line-height: 1.2;
        }
        
        .section-title:after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -12px;
            width: 60px;
            height: 2px;
            background: var(--accent);
        }
        
        .text-center {
            text-align: center;
        }
        
        .text-center .section-title:after {
            left: 50%;
            transform: translateX(-50%);
        }
        
        /* Cursor */
        .cursor {
            position: fixed;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background-color: var(--primary);
            opacity: 0.3;
            pointer-events: none;
            z-index: 9999;
            transform: translate(-50%, -50);
            transition: 
                width 0.3s ease,
                height 0.3s ease,
                background-color 0.3s ease;
            mix-blend-mode: multiply;
        }
        
        .cursor.active {
            width: 70px;
            height: 70px;
            opacity: 0.1;
        }
        
        .cursor.click {
            width: 40px;
            height: 40px;
            opacity: 0.2;
        }
        
        /* Navigation */
        .nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 1.5rem 0;
            z-index: 1000;
            transition: all 0.6s ease;
        }
        
        .nav.scrolled {
            background-color: rgba(246, 244, 240, 0.96);
            backdrop-filter: blur(10px);
            box-shadow: var(--shadow-sm);
            padding: 0.8rem 0;
        }
        
        .nav.active {
            background-color: var(--secondary);
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: relative;
        }
        
        .logo {
            font-family: var(--font-heading);
            font-size: 1.8rem;
            letter-spacing: 2px;
            color: var(--primary);
            position: relative;
            z-index: 1001;
        }
        
        .nav-links {
            display: flex;
            gap: 2.5rem;
        }
        
        .nav-link {
            font-size: 0.85rem;
            letter-spacing: 1.5px;
            text-transform: uppercase;
            font-weight: 500;
            position: relative;
            padding: 0.5rem 0;
        }
        
        .nav-link:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 1px;
            background: var(--primary);
            transition: width var(--transition);
        }
        
        .nav-link:hover:after {
            width: 100%;
        }
        
        .nav-actions {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }
        
        .nav-icon {
            font-size: 1.1rem;
            color: var(--primary);
            position: relative;
        }
        
        .nav-icon:hover {
            transform: translateY(-2px);
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--primary);
            color: white;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.6rem;
            font-weight: 600;
        }
        
        .menu-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.4rem;
            color: var(--primary);
            z-index: 1001;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            min-height: 800px;
            position: relative;
            overflow: hidden;
        }
        
        .hero-canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #f3f0eb 0%, #e8e4dd 100%);
            z-index: -1;
        }
        
        .hero-content {
            display: flex;
            height: 100%;
            align-items: center;
            justify-content: space-between;
            padding: 100px 5% 0;
        }
        
        .hero-text {
            max-width: 600px;
            padding right: 3rem;
            z-index: 1;
        }
        
        .hero-subtitle {
            font-family: var(--font-subheading);
            font-size: 1.1rem;
            color: var(--accent);
            margin-bottom: 1.5rem;
            letter-spacing: 3px;
            text-transform: uppercase;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeIn 0.8s forwards 0.4s;
        }
        
        .hero-title {
            font-size: clamp(3rem, 7vw, 5.5rem);
            line-height: 1.1;
            margin-bottom: 2rem;
            color: var(--dark);
            transform: translateY(30px);
            opacity: 0;
            animation: fadeIn 1s forwards 0.6s;
        }
        
        .hero-description {
            font-size: 1.1rem;
            margin-bottom: 3rem;
            font-weight: 300;
            max-width: 500px;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeIn 1s forwards 0.8s;
        }
        
        .btn {
            display: inline-block;
            background: var(--primary);
            color: white;
            border: none;
            padding: 16px 42px;
            font-size: 0.9rem;
                    letter-spacing: 1.5px;
            text-transform: uppercase;
            border-radius: 0;
            position: relative;
            overflow: hidden;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeIn 1s forwards 1s;
        }
        
        .btn:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.7s ease;
        }
        
        .btn:hover {
            background: var(--dark);
            transform: translateY(-3px);
            box-shadow: var(--shadow-sm);
        }
        
        .btn:hover:before {
            left: 100;
        }
        
        .hero-image {
            position: relative;
            width: 50%;
            height: 80%;
            opacity: 0;
            transform: translateX(40px);
            animation: fadeInRight 1s forwards 1.2s;
        }
        
        .hero-image-inner {
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1606222748467-0c4c8f427adb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80') center/cover no-repeat;
            box-shadow: var(--shadow-lg);
            position: relative;
            transition: transform 0.6s ease;
        }
        
        .hero-image-inner:hover {
            transform: scale(1.02);
        }
        
        .hero-image-deco {
            position: absolute;
            background: var(--accent);
            opacity: 0.2;
            border-radius: 50%;
            z-index: -1;
        }
        
        .hero-image-deco-1 {
            width: 280px;
            height: 280px;
            top: -140px;
            left: -140px;
        }
        
        .hero-image-deco-2 {
            width: 180px;
            height: 180px;
            bottom: -80px;
            right: -80px;
        }
        
        .scroll-hint {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            animation: fadeIn 1s ease 1.6s forwards;
            opacity: 0;
        }
        
        .scroll-hint-text {
            font-size: 0.75rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .scroll-hint-icon {
            width: 2px;
            height: 40px;
            background: var(--primary);
            position: relative;
            overflow: hidden;
        }
        
        .scroll-hint-icon:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 20px;
            background: white;
            animation: scroll 2s infinite;
        }
        
        /* Featured Products */
        .products {
            padding: var(--section-spacing) 0;
            background: white;
        }
        
        .products-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 5rem;
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }
        
        .product-card {
            position: relative;
            display: flex;
            flex-direction: column;
            background: var(--secondary);
            transition: all var(--transition);
            overflow: hidden;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-md);
        }
        
        .product-media {
            position: relative;
            height: 420px;
            overflow: hidden;
        }
        
        .product-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 1.2s ease;
        }
        
        .product-card:hover .product-image {
            transform: scale(1.05);
        }
        
        .product-overlay {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            background: rgba(255,255,255,0.9);
            padding: 0.3rem 1.2rem;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
            letter-spacing: 0.5px;
            color: var(--text);
        }
        
        .product-actions {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: center;
            padding: 1.5rem;
            background: linear-gradient(to top, rgba(0,0,0,0.7), transparent);
            opacity: 0;
            transform: translateY(20px);
            transition: all var(--transition);
        }
        
        .product-card:hover .product-actions {
            opacity: 1;
            transform: translateY(0);
        }
        
        .product-action-btn {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: white;
            color: var(--primary);
            border: none;
            margin: 0 0.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all var(--transition);
        }
        
        .product-action-btn:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-2px);
        }
        
        .product-info {
            padding: 2rem;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }
        
        .product-category {
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--accent);
            margin-bottom: 0.8rem;
        }
        
        .product-title {
            font-family: var(--font-subheading);
            font-size: 1.5rem;
            margin-bottom: 1rem;
            transition: color var(--transition);
        }
        
        .product-card:hover .product-title {
            color: var(--primary);
        }
        
        .product-desc {
            font-size: 0.95rem;
            margin-bottom: 2rem;
            color: #666;
            flex-grow: 1;
        }
        
        .product-meta {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
            font-size: 0.85rem;
            color: #888;
        }
        
        .product-meta-separator {
            margin: 0 0.5rem;
        }
        
        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 1rem;
            border-top: var(--border);
        }
        
        .product-price {
            font-size: 1.3rem;
            font-weight: 500;
            color: var(--dark);
        }
        
        .product-price.sale {
            color: #a62121;
            text-decoration: line-through;
            margin-right: 0.5rem;
        }
        
        .product-price-final {
            color: var(--dark);
            font-weight: 600;
        }
        
        .product-add-to-cart {
            background: transparent;
            border: 1px solid var(--primary);
            color: var(--primary);
            padding: 0.8rem 1.8rem;
            font-size: 0.8rem;
            letter-spacing: 1px;
            text-transform: uppercase;
            transition: all var(--transition);
        }
        
        .product-add-to-cart:hover {
            background: var(--primary);
            color: white;
        }
        
        /* Collection Showcase */
        .collections {
            padding: var(--section-spacing) 0;
            background: var(--secondary);
        }
        
        .collections-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 70% 50%, rgba(216, 200, 184, 0.1) 0%, rgba(216, 200, 184, 0) 70%);
            z-index: 0;
        }
        
        .collections-content {
            position: relative;
            z-index: 1;
        }
        
        .collections-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 5rem;
        }
        
        .collections-slider {
            position: relative;
            width: 100%;
            overflow: hidden;
        }
        
        .swiper {
            width: 100%;
            padding-bottom: 50px;
        }
        
        .collection-slide {
            height: 520px;
            position: relative;
            overflow: hidden;
            border-radius: 4px;
            box-shadow: var(--shadow-md);
            transition: transform 0.6s ease;
        }
        
        .collection-slide:hover {
            transform: translateY(-10px);
        }
        
        .collection-slide:hover .collection-image {
            transform: scale(1.05);
        }
        
        .collection-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 1s ease;
        }
        
        .collection-info {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            padding: 2.5rem;
            background: linear-gradient(to top, rgba 0,0,0,0.7), transparent);
            color: white;
        }
        
        .collection-info-title {
            font-family: var(--font-subheading);
            font-size: 1.8rem;
            margin-bottom: 0.6rem;
        }
        
        .collection-info-desc {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-bottom: 1.5rem;
        }
        
        .collection-link {
            display: inline-flex;
            align-items: center;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--accent);
        }
        
        .collection-link i {
            margin-left: 8px;
            transition: transform 0.4s ease;
        }
        
        .collection-link:hover i {
            transform: translateX(5px);
        }
        
        .swiper-pagination-bullet {
            width: 12px;
            height: 12px;
            background: var(--primary);
            opacity: 0.3;
        }
        
        .swiper-pagination-bullet-active {
            opacity: 1;
        }
        
        .swiper-button-next, .swiper-button-prev {
            color: var(--primary);
        }
        
        /* Craftsmanship */
        .craft {
            padding: var(--section-spacing) 0;
            background: white;
        }
        
        .craft-container {
            display: flex;
            align-items: center;
            gap: 5rem;
        }
        
        .craft-content {
            flex: 1;
        }
        
        .craft-features {
            margin-bottom: 3rem;
        }
        
        .craft-feature {
            display: flex;
            align-items: flex-start;
            margin-bottom: 1.5rem;
            padding-bottom: 1.5rem;
            border-bottom: var(--border);
        }
        
        .craft-feature:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }
        
        .craft-feature-icon {
            font-size: 1.4rem;
            color: var(--primary);
            margin right: 1.5rem;
            margin-top: 0.2rem;
        }
        
        .craft-feature-content h4 {
            font-family: var(--font-subheading);
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }
        
        .craft-feature-content p {
            font-size: 0.95rem;
        }
        
        .craft-media {
            flex: 1;
            height: 500px;
            position: relative;
        }
        
        .craft-media-canvas {
            width: 100%;
            height: 100%;
            background: var(--secondary);
            border-radius: 4px;
            box-shadow: var(--shadow-lg);
            overflow: hidden;
        }
        
        .craft-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: url('https://images.unsplash.com/photo-1583947581924-dd1d0f1bc916?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80') center/cover no-repeat;
        }
        
        .craft-hint {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(255,255,255,0.9);
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            box-shadow: var(--shadow-sm);
            animation: float 4s ease-in-out infinite;
        }
        
        .craft-hint i {
            margin-right: 0.8rem;
            animation: rotate 4s linear infinite;
        }
        
        /* Values */
        .values {
            padding: var(--section-spacing) 0;
            background: var(--secondary);
        }
        
        .values-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 5rem;
        }
        
        .values-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
        }
        
        .value-card {
            text-align: center;
            padding: 3.5rem 2.5rem;
            background: white;
            border-radius: 4px;
            box-shadow: var(--shadow-sm);
            transition: all var(--transition);
        }
        
        .value-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-md);
        }
        
        .value-card-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 2rem;
            transition: transform 0.6s ease;
        }
        
        .value-card:hover .value-card-icon {
            transform: scale(1.1) rotate(5deg);
        }
        
        .value-card-title {
            font-family: var(--font-subheading);
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
        }
        
        .value-card-desc {
            font-size: 0.95rem;
            color: #666;
        }
        
        /* Newsletter */
        .newsletter {
            padding: var(--section-spacing) 0;
            background: var(--primary);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .newsletter-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 50%, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%);
            z-index: 0;
        }
        
        .newsletter-content {
            position: relative;
            z-index: 1;
            max-width: 700px;
            margin: 0 auto;
        }
        
        .newsletter-title {
            font-size: clamp(2rem, 5vw, 3.5rem);
            margin-bottom: 1.5rem;
        }
        
        .newsletter-desc {
            font-size: 1.15rem;
            margin-bottom: 3rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            opacity: 0.9;
        }
        
        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
            position: relative;
        }
        
        .newsletter-input {
            flex: 1;
            padding: 1.1rem 1.5rem;
            border: none;
            font-family: var(--font-body);
            font-size: 1rem;
            color: var(--text);
        }
        
        .newsletter-input:focus {
            outline: none;
        }
        
        .newsletter-submit {
            background: var(--dark);
            color: white;
            border: none;
            padding: 0 2.5rem;
            font-size: 0.9rem;
            letter-spacing: 1.5px;
            text-transform: uppercase;
            transition: background var(--transition);
        }
        
        .newsletter-submit:hover {
            background: #26201c;
        }
        
        /* Footer */
        .footer {
            background: var(--dark);
            color: #e0d8d2;
            padding: 6rem 0 3rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 4rem;
            margin-bottom: 5rem;
        }
        
        .footer-about {
            max-width: 350px;
        }
        
        .footer-logo {
            font-family: var(--font-heading);
            font-size: 1.8rem;
            letter-spacing: 3px;
            color: white;
            margin-bottom: 1.5rem;
            display: inline-block;
        }
        
        .footer-about-text {
            font-size: 0.95rem;
            margin-bottom: 2.5rem;
            opacity: 0.8;
            line-height: 1.8;
        }
        
        .footer-social {
            display: flex;
            gap: 1rem;
        }
        
        .social-link {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all var(--transition);
        }
        
        .social-link:hover {
            background: var(--accent);
            color: var(--dark);
            transform: translateY(-3px);
        }
        
        .footer-heading {
            font-family: var(--font-subheading);
            font-size: 1.3rem;
            margin-bottom: 2rem;
            color: white;
            position: relative;
            padding-bottom: 1rem;
        }
        
        .footer-heading:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 1px;
            background: var(--accent);
        }
        
        .footer-links {
            display: flex;
            flex-direction: column;
            gap: 1.2rem;
        }
        
        .footer-link {
            font-size: 0.95rem;
            opacity: 0.8;
            transition: all var(--transition);
            display: flex;
            align-items: center;
        }
        
        .footer-link i {
            margin-right: 0.8rem;
            font-size: 0.8rem;
        }
        
        .footer-link:hover {
            opacity: 1;
            color: var(--accent);
            transform: translateX(5px);
        }
        
        .footer-contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 1.2rem;
            font-size: 0.95rem;
            opacity: 0.8;
        }
        
        .footer-contact-item i {
            margin-right: 1rem;
            margin-top: 0.4rem;
        }
        
        .footer-bottom {
            padding-top: 3rem;
            border-top: 1px solid rgba(255,255,255,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .copyright {
            font-size: 0.85rem;
            opacity: 0.7;
        }
        
        .footer-legal-links {
            display: flex;
            gap: 2rem;
        }
        
        .footer-legal-link {
            font-size: 0.85rem;
            opacity: 0.7;
            transition: all var(--transition);
        }
        
        .footer-legal-link:hover {
            opacity: 1;
            color: var(--accent);
        }
        
        /* Animations */
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
        
        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(40px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes scroll {
            0% {
                transform: translateY(0);
                opacity: 0;
            }
            20% {
                opacity: 1;
            }
            90% {
                transform: translateY(20px);
                opacity: 0;
            }
            100% {
                transform: translateY(0);
                opacity: 0;
            }
        }
        
        @keyframes rotate {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) translateX(-50%);
            }
            50% {
                transform: translateY(-10px) translateX(-50%);
            }
            100% {
                transform: translateY(0) translateX(-50%);
            }
        }
        
        /* Responsive */
        @media (max-width: 1200px) {
            .craft-container {
                flex-direction: column;
                gap: 3rem;
            }
            
            .craft-media {
                width: 100%;
            }
        }
        
        @media (max-width: 992px) {
            .nav-links {
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100vh;
                background: var(--secondary);
                flex-direction: column;
                justify-content: center;
                align-items: center;
                gap: 2rem;
                z-index: 1000;
                opacity: 0;
                pointer-events: none;
                transition: all 0.6s ease;
            }
            
            .nav-links.active {
                opacity: 1;
                pointer-events: all;
            }
            
            .menu-toggle {
                display: block;
            }
            
            .hero-content {
                flex-direction: column;
                text-align: center;
                padding-top: 120px;
            }
            
            .hero-text {
                max-width: 100%;
                padding-right: 0;
                margin-bottom: 3rem;
            }
            
            .hero-image {
                width: 80%;
            }
            
            .values-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
                gap: 2rem;
            }
        }
        
        @media (max-width: 768px) {
            .section {
                padding: 80px 0;
            }
            
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            }
            
            .newsletter-form {
                flex-direction: column;
                gap: 1rem;
            }
            
            .newsletter-input,
            .newsletter-submit {
                width: 100%;
            }
            
            .collection-slide {
                height: 450px;
            }
        }
        
        @media (max-width: 576px) {
            .hero {
                min-height: 700px;
            }
            
            .hero-title {
                font-size: 3rem;
            }
            
            .hero-description {
                font-size: 1rem;
            }
            
            .hero-image {
                width: 100%;
                height: 50%;
            }
            
            .footer-bottom {
                flex-direction: column;
                gap: 1.5rem;
                text-align: center;
            }
            
            .footer-legal-links {
                flex-direction: column;
                gap: 0.8rem;
            }
        }
    </style>
</head>
<body>
    <!-- Custom Cursor -->
    <div class="cursor"></div>
    
    <!-- Navigation -->
    <nav class="nav">
        <div class="container nav-container">
            <a href="#" class="logo">LUMINOUS LUX</a>
            <div class="nav-links">
                <a href="#" class="nav-link">Home</a>
                <a href="#" class="nav-link">Collections</a>
                <a href="#" class="nav-link">Shop</a>
                <a href="#" class="nav-link">Journal</a>
                <a href="#" class="nav-link">About</a>
            </div>
            <div class="nav-actions">
                <a href="#" class="nav-icon"><i class="fas fa-search"></i></a>
                <a href="#" class="nav-icon"><i class="fas fa-user"></i></a>
                <a href="#" class="nav-icon">
                    <i class="fas fa-shopping-bag"></i>
                    <span class="cart-count">0</span>
                </a>
                <button class="menu-toggle">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
    </nav>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-canvas"></div>
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h6 class="hero-subtitle">Handcrafted Since 2012</h6>
                    <h1 class="hero-title">Illuminate Your Space With Artisan Candles</h1>
                    <p class="hero-description">Our premium soy wax candles are crafted with care, using only the finest ingredients to create lasting fragrances that transform any space.</p>
                    <a href="#" class="btn">Explore Collections</a>
                </div>
                <div class="hero-image">
                    <div class="hero-image-inner"></div>
                    <div class="hero-image-deco hero-image-deco-1"></div>
                    <div class="hero_image-deco hero-image-deco-2"></div>
                </div>
            </div>
            <div class="scroll-hint">
                <div class="scroll-hint-text">Scroll Down</div>
                <div class="scroll-hint-icon"></div>
            </div>
        </div>
    </section>
    
    <!-- Featured Products -->
    <section class="section products">
        <div class="container">
            <div class="products-header text-center">
                <h2 class="section-title">Our Creations</h2>
                <p>Discover our signature collection of handcrafted candles, each with unique scents and premium materials that elevate your senses.</p>
            </div>
            <div class="product-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-media">
                        <img src="https://images.unsplash.com/photo-1606220926170-78e17eee8e44?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=720&q=80" alt="Amber & Moss Candle" class="product-image">
                        <div class="product-overlay">Best Seller</div>
                        <div class="product-actions">
                            <button class="product-action-btn"><i class="fas fa-search"></i></button>
                            <button class="product-action-btn"><i class="far fa-heart"></i></button>
                            <button class="product-action-btn"><i class="fas fa-shopping-cart"></i></button>
                        </div>
                    </div>
                    <div class="product-info">
                        <span class="product-category">Woody Scents</span>
                        <h3 class="product-title">Amber & Moss</h3>
                        <p class="product-desc">A warm, earthy blend of amber, vetiver, and oak moss with hints of spice and vanilla.</p>
                        <div class="product-footer">
                            <div>
                                <span class="product-price">$42.00</span>
                            </div>
                            <button class="product-add-to-cart">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-media">
                        <img src="https://images.unsplash.com/photo-1507914464560-61c8530ad005?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=720&q=80" alt="Lavender Fields Candle" class="product-image">
                        <div class="product-actions">
                            <button class="product-action-btn"><i class="fas fa-search"></i></button>
                            <button class="product-action-btn"><i class="far fa-heart"></i></button>
                            <button class="product-action-btn"><i class="fas fa-shopping-cart"></i></button>
                        </div>
                    </div>
                    <div class="product-info">
                        <span class="product-category">Floral Scents</span>
                        <h3 class="product-title">Lavender Fields</h3>
                        <p class="product-desc">Relaxing floral notes of French lavender blended with herbaceous undertones of rosemary.</p>
                        <div class="product-footer">
                            <div>
                                <span class="product-price">$38.00</span>
                            </div>
                            <button class="product-add-to-cart">Add to Cart</button>
                        </div>
                    </div>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card">
                    <div class="product-media">
                        <img src="https://images.unsplash.com/photo-1654869121817-edae0d5f390e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=720&q=80" alt="Sea Salt & Oak" class="product-image">
                        <div class="product-overlay">New Arrival</div>
                        <div class="product-actions">
                            <button class="product-action-btn"><i class="fas fa-search"></i></button>
                            <button class="product-action-btn"><i class="far fa-heart"></i></button>
                            <button class="product-action-btn"><i class="fas fa-shopping-cart"></i></button>
                        </div>
                    </div>
                    <div class="product-info">
                        <span class="product-category">Fresh Scents</span>
                        <h3 class="product-title">Sea Salt & Oak</h3>
                        <p class="product-desc">Crisp ocean air meets warm oak for a perfectly balanced coastal-inspired fragrance.</p>
                        <div class="product-meta">
                            <span>60hr+ Burn Time</span>
                            <span class="product-meta-separator">•</span>
                            <span>Soy Wax</span>
                        </div>
                        <div class="product-footer">
                            <div>
                                <span class="product-price sale">$45.00</span>
                                <span class="product-price-final">$36.00</span>
                            </div>
                            <button class="product-add-to-cart">Add to Cart</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Collection Showcase -->
    <section class="section collections">
        <div class="collections-bg"></div>
        <div class="container">
            <div class="collections-content">
                <div class="collections-header text-center">
                    <h2 class="section-title">Seasonal Collections</h2>
                    <p>Explore our curated seasonal collections that capture the essence of each period through carefully crafted fragrances and designs.</p>
                </div>
                <div class="collections-slider">
                    <div class="swiper">
                        <div class="swiper-wrapper">
                            <!-- Collection 1 -->
                            <div class="swiper-slide">
                                <div class="collection-slide">
                                    <img src="https://images.unsplash.com/photo-1592864849333-6ba7333fc9f1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Autumn Harvest Collection" class="collection-image">
                                    <div class="collection-info">
                                        <h3 class="collection-info-title">Autumn Harvest</h3>
                                        <p class="collection-info-desc">Warm, cozy scents that embody the richness of the fall season with notes of pumpkin, cinnamon and nutmeg.</p>
                                        <a href="#" class="collection-link">
                                            View Collection
                                            <i class="fas fa-arrow-right"></i>
                                        </a>
                                    </div>
                                </div>
                            </div>
                            
                            <!-- Collection 2 -->
                            <div class="swiper-slide">
                                <div class="collection-slite">
                                    <img src="https://images.unsplash.com/photo-1608069278555-7a88b9305bc2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Winter Solstice Collection" class="collection-image">
                                    <div class="collection-info">
                                        <h3 class="collection-info-title">Winter Solstice</h3>
                                        <p class="collection-info-desc">Invigorating winter scents with crisp pine, peppermint and warm vanilla to brighten the cold season.</p>
                                        <a href="#" class="collection-link">
                                            View Collection
                                            <i class="fas fa-arrow-right"></i>
                                        </a>
                                    </div>
                                </div>
                            </div>
                            
                            <!-- Collection 3 -->
                            <div class="swiper-slide">
                                <div class="collection-slide">
                                    <img src="https://images.unsplash.com/photo-1603114595874-2658d8c98c68?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Spring Awakening Collection" class="collection-image">
                                    <div class="collection-info">
                                        <h3 class="collection-info-title">Spring Awakening</h3>
                                        <p class="collection-info-desc">Fresh floral and citrus notes that capture the renewal of spring with hints of jasmine, bergamot and rain.</p>
                                        <a href="#" class="collection-link">
                                            View Collection
                                            <i class="fas fa-arrow-right"></i>
                                        </a>
                                    </div>
                                </div>
                            </div>
                            
                            <!-- Collection 4 -->
                            <div class="swiper-slide">
                                <div class="collection-slide">
                                    <img src="https images.unsplash.com/photo-1527689368860-454a83d27076?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Summer Nights Collection" class="collection-image">
                                    <div class="collection-info">
                                        <h3 class="collection-info-title">Summer Nights</h3>
                                        <p class="collection-info-desc">Tropical beach-inspired fragrances with coconut, sea salt and night blooming flowers for warm summer evenings.</p>
                                        <a href="#" class="collection-link">
                                            View Collection
                                            <i class="fas fa-arrow-right"></i>
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="swiper-pagination"></div>
                        <div class="swiper-button-next"></div>
                        <div class="swiper-button-prev"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Craftsmanship -->
    <section class="section craft">
        <div class="container">
            <div class="craft-container">
                <div class="craft-content">
                    <h2 class="section-title">The Luminous Lux Craft</h2>
                    <p>Every Luminous Lux candle is the result of meticulous craftsmanship and premium quality materials, ensuring an exceptional experience from first tight to final glow.</p>
                    
                    <div class="craft_features">
                        <div class="craft-feature">
                            <div class="craft-feature-icon">
                                <i class="fas fa-leaf"></i>
                            </div>
                            <div class="craft-feature-content">
                                <h4>Natural Soy Wax</h4>
                                <p>Our proprietary blend of eco-friendly soy wax provides a clean, even burn and maximizes fragrance throw.</p>
                            </div>
                        </div>
                        
                        <div class="craft-feature">
                            <div class="craft-feature-icon">
                                <i class="fas fa-spa"></i>
                            </div>
                            <div class="craft-feature-content">
                                <h4>Premium Fragrances</h4>
                                <p>We source only the highest quality essential oils and fragrance blends to create complex, lasting scents.</p>
                            </div>
                        </div>
                        
                        <div class="craft-feature">
                            <div class="craft-feature-icon">
                                <i class="fas fa-hands"></i>
                            </div>
                            <div class="craft-feature-content">
                                <h4>Hand-poured in Small Batches</h4>
                                <p>Each candle receives individual attention from our artisans to ensure perfect consistency and quality.</p>
                            </div>
                        </div>
                    </div>
                    
                    <a href="#" class="btn">Our Process</a>
                </div>
                
                <div class="craft-media">
                    <div class="craft-media-canvas">
                        <div class="craft-placeholder"></div>
                    </div>
                    <div class="craft-hint">
                        <i class="fas fa-heart"></i>
                        Handmade with Love
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Values -->
    <section class="section values">
        <div class="container">
            <div class="values-header text-center">
                <h2 class="section-title">Our Core Values</h2>
                <p>At Luminous Lux, we're committed to more than just creating beautiful candles. These principles guide everything we do.</p>
            </div>
            
            <div class="values-grid">
                <div class="value-card">
                    <div class="value-card-icon">
                        <i class="fas fa-globe-europe"></i>
                    </div>
                    <h3 class="value-card-title">Sustainability</h3>
                    <p class="value-card-desc">We prioritize environmentally responsible practices, from our plant-based waxes to our recyclable packaging.</p>
                </div>
                
                <div class="value-card">
                    <div class="value-card-icon">
                        <i class="fas fa-gem"></i>
                    </div>
                    <h3 class="value-card-title">Quality</h3>
                    <p class="value-card-desc">Only premium ingredients make the cut - we test every batch to ensure superior performance and longevity.</p>
                </div>
                
                <div class="value-card">
                    <div class="value-card-icon">
                        <i class="fas fa-hand-holding-heart"></i>
                    </div>
                    <h3 class="value-card-title">Ethical Sourcing</h3>
                    <p class="value-card-desc">We build direct relationships with suppliers who share our commitment to fair wages and humane working conditions.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Newsletter -->
    <section class="section newsletter">
        <div class="newsletter-bg"></div>
        <div class="container">
            <div class="newsletter-content">
                <h2 class="newsletter-title">Join Our Community</h2>
                <p class="newsletter-desc">Subscribe to receive exclusive offers, candle care tips, and early access to our seasonal collections.</p>
                
                <form class="newsletter-form">
                    <input type="email" class="newsletter-input" placeholder="Your email address" required>
                    <button type="submit" class="newsletter-submit">Subscribe</button>
                </form>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-about">
                    <a href="#" class="footer-logo">LUMINOUS LUX</a>
                    <p class="footer-about-text">Founded in 2012, Luminous Lux has been dedicated to crafting premium artisan candles that transform spaces into sanctuaries with our signature scents.</p>
                    <div class="footer-social">
                        <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-pinterest"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
                
                <div class="footer-section">
                    <h4 class="footer-heading">Quick Links</h4>
                    <div class="footer-links">
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Shop All
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Best Sellers
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            New Arrivals
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Gift Cards
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Sale
                        </a>
                    </div>
                </div>
                
                <div class="footer-section">
                    <h4 class="footer-heading">Customer Care</h4>
                    <div class="footer-links">
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Contact Us
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            FAQs
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Shipping Policy
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Returns & Exchanges
                        </a>
                        <a href="#" class="footer-link">
                            <i class="fas fa-chevron-right"></i>
                            Candle Care
                        </a>
                    </div>
                </div>
                
                <div class="footer-section">
                    <h4 class="footer-heading">Contact</h4>
                    <div class="footer-contact">
                        <div class="footer-contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>123 Candlelight Lane, Portland, OR 97209</span>
                        </div>
                        <div class="footer-contact-item">
                            <i class="fas fa-phone-alt"></i>
                            <span>(503) 555-0182</span>
                        </div>
                        <div class="footer-contact-item">
                            <i class="fas fa-envelope"></i>
                            <span>hello@luminouslux.com</span>
                        </div>
                        <div class="footer-contact-item">
                            <i class="fas fa-clock"></i>
                            <span>Mon-Fri: 9AM - 5PM PST</span>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p class="copyright">© 2023 Luminous Lux Candles. All rights reserved.</p>
                <div class="footer-legal-links">
                    <a href="#" class="footer-legal-link">Privacy Policy</a>
                    <a href="#" class="footer-legal-link">Terms of Service</a>
                    <a href="#" class="footer-legal-link">Accessibility</a>
                </div>
            </div>
        </div>
    </footer>
    
    <script>
        // Custom Cursor
        const cursor = document.querySelector('.cursor');
        
        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX + 'px';
            cursor.style.top = e.clientY + 'px';
        });
        
        document.querySelectorAll('a, button, .product-action-btn, .nav-icon').forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursor.classList.add('active');
            });
            
            el.addEventListener('mouseleave', () => {
                cursor.classList.remove('active');
            });
        });
        
        document.addEventListener('mousedown', () => {
            cursor.classList.add('click');
        });
        
        document.addEventListener('mouseup', () => {
            cursor.classList.remove('click');
        });
        
        // Mobile Navigation
        const menuToggle = document.querySelector('.menu-toggle');
        const navLinks = document.querySelector('.nav-links');
        
        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            menuToggle.innerHTML = navLinks.classList.contains('active') ? 
                '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
            document.querySelector('.nav').classList.toggle('active');
        });
        
        // Scroll Animation with GSAP
        gsap.registerPlugin(ScrollTrigger);
        
        gsap.utils.toArray('.section').forEach(section => {
            gsap.from(section, {
                scrollTrigger: {
                    trigger: section,
                    start: "top 80%",
                    toggleActions: "play none none none"
                },
                opacity: 0,
                y: 50,
                duration: 1
            });
        });
        
        // Initialize Swiper
        const swiper = new Swiper('.swiper', {
            slidesPerView: 1,
            spaceBetween: 30,
            loop: true,
            autoplay: {
                delay: 5000,
                disableOnInteraction: false
            },
            pagination: {
                el: '.swiper-pagination',
                clickable: true
            },
            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev'
            },
            breakpoints: {
                768: {
                    slidesPerView: 2
                },
                1200: {
                    slidesPerView: 3
                }
            }
        });
        
        // Navigation Scroll Effect
        window.addEventListener('scroll', () => {
            if (window.scrollY > 100) {
                document.querySelector('.nav').classList.add('scrolled');
            } else {
                document.querySelector('.nav').classList.remove('scrolled');
            }
        });
        
        // Smooth Scrolling for Anchor Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 100,
                        behavior: 'smooth'
                    });
                }
                
                // Close mobile menu if open
                if (navLinks.classList.contains('active')) {
                    navLinks.classList.remove('active');
                    menuToggle.innerHTML = '<i class="fas fa-bars"></i>';
                    document.querySelector('.nav').classList.remove('active');
                }
            });
        });
        
        // Add to Cart Interaction
        document.querySelectorAll('.product-add-to-cart').forEach(button => {
            button.addEventListener('click', function() {
                const count = document.querySelector('.cart-count');
                let currentCount = parseInt(count.textContent);
                count.textContent = currentCount + 1;
                
                // Animation
                gsap.to(count, {
                    scale: 1.5,
                    duration: 0.3,
                    yoyo: true,
                    repeat: 1
                });
                
                // Button feedback
                gsap.to(this, {
                    backgroundColor: '#5a4d3d',
                    duration: 0.5,
                    color: '#fff'
                });
                
                // Reset after delay
                setTimeout(() => {
                    gsap.to(this, {
                        backgroundColor: 'transparent',
                        color: '#7a6a58'
                    });
                }, 1000);
            });
        });
    </script>
</body>
</html>

