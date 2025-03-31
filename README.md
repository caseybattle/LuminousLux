[

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Luminous | Luxury Artisan Candles</title>

   

    <!-- Fonts -->

    <link rel="preconnect" href="https://fonts.googleapis.com">

    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600&family=Montserrat:wght@300;400;500&family=Italiana&display=swap" rel="stylesheet">

   

    <!-- Font Awesome -->

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

   

    <!-- Favicon -->

    <link rel="icon" type="image/png" href="https://placehold.co/32x32">

   

    <!-- Meta Tags -->

    <meta name="description" content="Discover luxury handcrafted candles at Luminous. Our premium collection features exotic scents and elegant designs for the modern home.">

    <meta name="keywords" content="luxury candles, handcrafted candles, scented candles, home fragrance, aromatherapy, soy candles">

    <meta property="og:title" content="Luminous | Luxury Artisan Candles">

    <meta property="og:description" content="Discover luxury handcrafted candles at Luminous. Premium collection of exotic scents and elegant designs.">

    <meta property="og:image" content="https://placehold.co/1200x630">

    <meta property="og:url" content="https://luminouscandles.com">

   

    <!-- GSAP for animations -->

    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>

   

    <!-- Locomotive Scroll for smooth scrolling -->

    <script src="https://cdn.jsdelivr.net/npm/locomotive-scroll@4.1.4/dist/locomotive-scroll.min.js"></script>

   

    <!-- Swiper for carousels -->

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.css" />

    <script src="https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.js"></script>

   

    <!-- Three.js for 3D elements -->

    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

   

    <!-- Custom styles -->

    <style>

        :root {

            --primary-color: #8a6d5f;

            --secondary-color: #f5f1ed;

            --accent-color: #d4b59e;

            --dark-accent: #3a2e28;

            --text-dark: #333333;

            --text-light: #f8f5f2;

            --font-heading: 'Italiana', serif;

            --font-subheading: 'Cormorant Garamond', serif;

            --font-body: 'Montserrat', sans-serif;

            --transition-slow: 0.7s cubic-bezier(0.25, 1, 0.5, 1);

            --transition-medium: 0.4s cubic-bezier(0.25, 1, 0.5, 1);

            --transition-fast: 0.2s cubic-bezier(0.25, 1, 0.5, 1);

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

            color: var(--text-dark);

            line-height: 1.6;

            background-color: var(--secondary-color);

            overflow-x: hidden;

        }

       

        h1, h2, h3, h4, h5 {

            font-family: var(--font-heading);

            font-weight: 400;

            letter-spacing: 1px;

        }

       

        h6 {

            font-family: var(--font-subheading);

            font-weight: 500;

            letter-spacing: 0.5px;

        }

       

        a {

            text-decoration: none;

            color: inherit;

            transition: all var(--transition-fast);

        }

       

        button {

            cursor: pointer;

            font-family: var(--font-body);

            transition: all var(--transition-fast);

        }

       

        .container {

            max-width: 1400px;

            margin: 0 auto;

            padding: 0 2rem;

        }

       

        .section-title {

            font-size: 3rem;

            margin-bottom: 1.5rem;

            position: relative;

            display: inline-block;

        }

       

        .section-title::after {

            content: '';

            position: absolute;

            width: 60px;

            height: 2px;

            background-color: var(--accent-color);

            bottom: -10px;

            left: 0;

        }

       

        .text-center {

            text-align: center;

        }

       

        .text-center .section-title::after {

            left: 50%;

            transform: translateX(-50%);

        }

       

        /* Cursor */

        .custom-cursor {

            position: fixed;

            width: 20px;

            height: 20px;

            border-radius: 50%;

            background-color: rgba(138, 109, 95, 0.3);

            pointer-events: none;

            z-index: 9999;

            transform: translate(-50%, -50%);

            transition: width 0.3s, height 0.3s, background-color 0.3s;

            mix-blend-mode: difference;

        }

       

        .custom-cursor.active {

            width: 50px;

            height: 50px;

            background-color: rgba(138, 109, 95, 0.2);

        }

       

        /* Navigation */

        .nav-container {

            position: fixed;

            width: 100%;

            top: 0;

            left: 0;

            z-index: 1000;

            transition: background-color 0.4s ease, padding 0.4s ease;

        }

       

        .nav-container.scrolled {

            background-color: rgba(245, 241, 237, 0.95);

            backdrop-filter: blur(10px);

            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);

            padding: 0.5rem 0;

        }

       

        .nav-content {

            max-width: 1400px;

            margin: 0 auto;

            display: flex;

            justify-content: space-between;

            align-items: center;

            padding: 1.5rem 2rem;

            transition: padding 0.4s ease;

        }

       

        .scrolled .nav-content {

            padding: 1rem 2rem;

        }

       

        .logo {

            font-family: var(--font-heading);

            font-size: 2rem;

            letter-spacing: 3px;

            color: var(--primary-color);

            position: relative;

            z-index: 2;

        }

       

        .nav-links {

            display: flex;

            gap: 3rem;

        }

       

        .nav-link {

            font-size: 0.9rem;

            text-transform: uppercase;

            letter-spacing: 1.5px;

            position: relative;

            padding: 0.5rem 0;

        }

       

        .nav-link:after {

            content: '';

            position: absolute;

            width: 0;

            height: 1px;

            bottom: 0;

            left: 0;

            background-color: var(--primary-color);

            transition: width var(--transition-medium);

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

            font-size: 1.2rem;

            color: var(--primary-color);

            position: relative;

        }

       

        .cart-count {

            position: absolute;

            top: -8px;

            right: -8px;

            background-color: var(--accent-color);

            color: white;

            border-radius: 50%;

            width: 18px;

            height: 18px;

            display: flex;

            align-items: center;

            justify-content: center;

            font-size: 0.7rem;

            font-weight: 500;

        }

       

        .menu-toggle {

            display: none;

            background: none;

            border: none;

            color: var(--primary-color);

            font-size: 1.5rem;

            z-index: 2;

        }

       

        /* Hero Section */

        .hero {

            height: 100vh;

            position: relative;

            overflow: hidden;

            margin-top: 0;

        }

       

        .hero-bg {

            position: absolute;

            top: 0;

            left: 0;

            width: 100%;

            height: 100%;

            background: linear-gradient(135deg, var(--secondary-color) 0%, #e9e1d9 100%);

            z-index: -1;

        }

       

        .hero-content {

            display: flex;

            height: 100%;

            align-items: center;

            justify-content: space-between;

            padding: 0 5%;

        }

       

        .hero-text {

            max-width: 600px;

            z-index: 1;

        }

       

        .hero-subtitle {

            font-family: var(--font-subheading);

            font-size: 1.2rem;

            color: var(--accent-color);

            margin-bottom: 1rem;

            letter-spacing: 3px;

            text-transform: uppercase;

            opacity: 0;

            transform: translateY(20px);

            animation: fadeInUp 1s forwards 0.2s;

        }

       

        .hero-title {

            font-size: 5rem;

            line-height: 1.1;

            margin-bottom: 1.5rem;

            color: var(--dark-accent);

            opacity: 0;

            transform: translateY(20px);

            animation: fadeInUp 1s forwards 0.4s;

        }

       

        .hero-description {

            font-size: 1.1rem;

            margin-bottom: 2.5rem;

            font-weight: 300;

            max-width: 500px;

            opacity: 0;

            transform: translateY(20px);

            animation: fadeInUp 1s forwards 0.6s;

        }

       

        .cta-button {

            background-color: var(--primary-color);

            color: white;

            border: none;

            padding: 15px 40px;

            font-size: 0.9rem;

            letter-spacing: 2px;

            text-transform: uppercase;

            border-radius: 0;

            position: relative;

            overflow: hidden;

            opacity: 0;

            transform: translateY(20px);

            animation: fadeInUp 1s forwards 0.8s;

        }

       

        .cta-button::before {

            content: '';

            position: absolute;

            top: 0;

            left: -100%;

            width: 100%;

            height: 100%;

            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);

            transition: left 0.7s;

        }

       

        .cta-button:hover {

            background-color: var(--dark-accent);

            transform: translateY(-3px);

            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);

        }

       

        .cta-button:hover::before {

            left: 100%;

        }

       

        .hero-image-container {

            position: relative;

            width: 45%;

            height: 80%;

            opacity: 0;

            transform: translateX(20px);

            animation: fadeInRight 1s forwards 1s;

        }

       

        .hero-image {

            width: 100%;

            height: 100%;

            background: url('https://placehold.co/800x1000') center/cover no-repeat;

            border-radius: 5px;

            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.1);

            transition: transform 0.5s ease;

        }

       

        .hero-image:hover {

            transform: scale(1.02);

        }

       

        .floating-elements {

            position: absolute;

            top: 0;

            left: 0;

            width: 100%;

            height: 100%;

            pointer-events: none;

        }

       

        .floating-element {

            position: absolute;

            background-color: var(--accent-color);

            opacity: 0.1;

            border-radius: 50%;

        }

       

        .floating-element:nth-child(1) {

            width: 300px;

            height: 300px;

            top: -150px;

            left: -150px;

        }

       

        .floating-element:nth-child(2) {

            width: 200px;

            height: 200px;

            bottom: -100px;

            right: 10%;

        }

       

        .floating-element:nth-child(3) {

            width: 150px;

            height: 150px;

            top: 20%;

            right: -75px;

        }

       

        .scroll-indicator {

            position: absolute;

            bottom: 40px;

            left: 50%;

            transform: translateX(-50%);

            display: flex;

            flex-direction: column;

            align-items: center;

            opacity: 0;

            animation: fadeIn 1s forwards 1.5s;

        }

       

        .scroll-text {

            font-size: 0.8rem;

            letter-spacing: 2px;

            text-transform: uppercase;

            margin-bottom: 10px;

            color: var(--primary-color);

        }

       

        .scroll-icon {

            width: 30px;

            height: 50px;

            border: 2px solid var(--primary-color);

            border-radius: 15px;

            position: relative;

        }

       

        .scroll-icon::before {

            content: '';

            position: absolute;

            top: 8px;

            left: 50%;

            width: 6px;

            height: 6px;

            background-color: var(--primary-color);

            border-radius: 50%;

            transform: translateX(-50%);

            animation: scrollDown 2s infinite;

        }

       

        /* Featured Products */

        .featured-products {

            padding: 8rem 0;

            background-color: white;

            position: relative;

        }

       

        .product-grid {

            display: grid;

            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));

            gap: 3rem;

            margin-top: 4rem;

        }

       

        .product-card {

            position: relative;

            display: flex;

            flex-direction: column;

            background-color: var(--secondary-color);

            border-radius: 0;

            overflow: hidden;

            transition: transform var(--transition-medium), box-shadow var(--transition-medium);

            height: 100%;

        }

       

        .product-card:hover {

            transform: translateY(-10px);

            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);

        }

       

        .product-image {

            position: relative;

            height: 350px;

            overflow: hidden;

        }

       

        .product-image img {

            width: 100%;

            height: 100%;

            object-fit: cover;

            transition: transform 0.8s ease;

        }

       

        .product-card:hover .product-image img {

            transform: scale(1.1);

        }

       

        .product-overlay {

            position: absolute;

            top: 15px;

            right: 15px;

            background-color: rgba(255, 255, 255, 0.9);

            padding: 5px 15px;

            border-radius: 20px;

            font-size: 0.8rem;

            font-weight: 500;

            letter-spacing: 1px;

        }

       

        .product-actions {

            position: absolute;

            bottom: 0;

            left: 0;

            width: 100%;

            display: flex;

            justify-content: center;

            padding: 1rem;

            background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent);

            opacity: 0;

            transform: translateY(20px);

            transition: opacity var(--transition-medium), transform var(--transition-medium);

        }

       

        .product-card:hover .product-actions {

            opacity: 1;

            transform: translateY(0);

        }

       

        .product-action-btn {

            background-color: white;

            color: var(--primary-color);

            border: none;

            width: 40px;

            height: 40px;

            border-radius: 50%;

            display: flex;

            align-items: center;

            justify-content: center;

            margin: 0 5px;

            transition: all var(--transition-fast);

        }

       

        .product-action-btn:hover {

            background-color: var(--primary-color);

            color: white;

            transform: translateY(-3px);

        }

       

        .product-info {

            padding: 1.5rem;

            display: flex;

            flex-direction: column;

            flex-grow: 1;

        }

       

        .product-category {

            font-size: 0.8rem;

            text-transform: uppercase;

            letter-spacing: 1px;

            color: var(--accent-color);

            margin-bottom: 0.5rem;

        }

       

        .product-card h3 {

            font-family: var(--font-subheading);

            font-size: 1.5rem;

            margin-bottom: 0.8rem;

            transition: color var(--transition-fast);

        }

       

        .product-card:hover h3 {

            color: var(--primary-color);

        }

       

        .product-card p {

            font-size: 0.9rem;

            margin-bottom: 1.5rem;

            color: #666;

            flex-grow: 1;

        }

       

        .product-details {

            display: flex;

            align-items: center;

            margin-bottom: 1rem;

            font-size: 0.8rem;

            color: #888;

        }

       

        .separator {

            margin: 0 0.5rem;

        }

       

        .product-bottom {

            display: flex;

            justify-content: space-between;

            align-items: center;

        }

       

        .price {

            font-size: 1.2rem;

            font-weight: 500;

            color: var(--dark-accent);

        }

       

        .add-to-cart {

            background-color: transparent;

            border: 1px solid var(--primary-color);

            color: var(--primary-color);

            padding: 10px 20px;

            font-size: 0.8rem;

            letter-spacing: 1px;

            text-transform: uppercase;

            border-radius: 0;

            transition: all var(--transition-fast);

        }

       

        .add-to-cart:hover {

            background-color: var(--primary-color);

            color: white;

        }

       

        /* Collection Showcase */

        .collection-showcase {

            padding: 8rem 0;

            background-color: #f9f6f3;

            position: relative;

            overflow: hidden;

        }

       

        .collection-bg {

            position: absolute;

            top: 0;

            left: 0;

            width: 100%;

            height: 100%;

            background: radial-gradient(circle at 70% 50%, rgba(212, 181, 158, 0.1) 0%, rgba(212, 181, 158, 0) 70%);

            z-index: 0;

        }

       

        .collection-content {

            position: relative;

            z-index: 1;

        }

       

        .collection-text {

            text-align: center;

            max-width: 700px;

            margin: 0 auto 5rem;

        }

       

        .collection-text h2 {

            font-size: 3rem;

            color: var(--dark-accent);

            margin-bottom: 1.5rem;

        }

       

        .collection-text p {

            font-size: 1.1rem;

            color: #666;

        }

       

        .collection-slider {

            position: relative;

            width: 100%;

            overflow: hidden;

        }

       

        .swiper-container {

            width: 100%;

            padding-bottom: 50px;

        }

       

        .collection-slide {

            position: relative;

            height: 500px;

            overflow: hidden;

            border-radius: 5px;

            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);

            transition: transform 0.5s ease;

        }

       

        .collection-slide:hover {

            transform: translateY(-10px);

        }

       

        .collection-slide img {

            width: 100%;

            height: 100%;

            object-fit: cover;

            transition: transform 0.8s ease;

        }

       

        .collection-slide:hover img {

            transform: scale(1.05);

        }

       

        .collection-info {

            position: absolute;

            bottom: 0;

            left: 0;

            width: 100%;

            padding: 2rem;

            background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent);

            color: white;

        }

       

        .collection-info h3 {

            font-family: var(--font-subheading);

            font-size: 1.8rem;

            margin-bottom: 0.5rem;

        }

       

        .collection-info p {

            font-size: 0.9rem;

            opacity: 0.9;

            margin-bottom: 1rem;

        }

       

        .collection-link {

            font-size: 0.8rem;

            text-transform: uppercase;

            letter-spacing: 1px;

            color: var(--accent-color);

            display: inline-flex;

            align-items: center;

        }

       

        .collection-link i {

            margin-left: 5px;

            transition: transform 0.3s ease;

        }

       

        .collection-link:hover i {

            transform: translateX(5px);

        }

       

        .swiper-pagination {

            position: absolute;

            bottom: 0;

        }

       

        .swiper-pagination-bullet {

            width: 10px;

            height: 10px;

            background-color: var(--primary-color);

            opacity: 0.3;

        }

       

        .swiper-pagination-bullet-active {

            opacity: 1;

            background-color: var(--primary-color);

        }

       

        .swiper-button-next, .swiper-button-prev {

            color: var(--primary-color);

        }

       

        /* 3D Product Showcase */

        .product-3d-showcase {

            padding: 8rem 0;

            background-color: white;

            position: relative;

        }

       

        .showcase-content {

            display: flex;

            align-items: center;

            justify-content: space-between;

            gap: 5rem;

        }

       

        .showcase-text {

            flex: 1;

        }

       

        .showcase-text h2 {

            font-size: 3rem;

            color: var(--dark-accent);

            margin-bottom: 1.5rem;

        }

       

        .showcase-text p {

            font-size: 1.1rem;

            color: #666;

            margin-bottom: 2rem;

        }

       

        .showcase-features {

            margin-bottom: 2rem;

        }

       

        .showcase-feature {

            display: flex;

            align-items: flex-start;

            margin-bottom: 1rem;

        }

       

        .feature-icon {

            color: var(--primary-color);

            font-size: 1.2rem;

            margin-right: 1rem;

            margin-top: 0.2rem;

        }

       

        .feature-text h4 {

            font-family: var(--font-subheading);

            font-size: 1.2rem;

            margin-bottom: 0.3rem;

        }

       

        .feature-text p {

            font-size: 0.9rem;

            margin-bottom: 0;

        }

       

        .showcase-3d {

            flex: 1;

            height: 500px;

            position: relative;

        }

       

        .canvas-container {

            width: 100%;

            height: 100%;

            background-color: var(--secondary-color);

            border-radius: 5px;

            overflow: hidden;

            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);

        }

       

        .canvas-placeholder {

            width: 100%;

            height: 100%;

            display: flex;

            align-items: center;

            justify-content: center;

            background: url('https://placehold.co/600x600') center/cover no-repeat;

        }

       

        .rotate-hint {

            position: absolute;

            bottom: 20px;

            left: 50%;

            transform: translateX(-50%);

            background-color: rgba(255, 255, 255, 0.9);

            padding: 10px 20px;

            border-radius: 20px;

            font-size: 0.8rem;

            display: flex;

            align-items: center;

            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);

        }

       

        .rotate-hint i {

            margin-right: 8px;

            animation: rotate 2s infinite linear;

        }

       

        /* Features */

        .features {

            padding: 8rem 0;

            background-color: var(--secondary-color);

            position: relative;

        }

       

        .features-grid {

            display: grid;

            grid-template-columns: repeat(3, 1fr);

            gap: 3rem;

            margin-top: 4rem;

        }

       

        .feature-card {

            text-align: center;

            padding: 3rem 2rem;

            background-color: white;

            border-radius: 5px;

            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);

            transition: transform var(--transition-medium), box-shadow var(--transition-medium);

        }

       

        .feature-card:hover {

            transform: translateY(-10px);

            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);

        }

       

        .feature-card i {

            font-size: 2.5rem;

            color: var(--primary-color);

            margin-bottom: 1.5rem;

            transition: transform var(--transition-medium);

        }

       

        .feature-card:hover i {

            transform: scale(1.1);

        }

       

        .feature-card h3 {

            font-family: var(--font-subheading);

            font-size: 1.5rem;

            margin-bottom: 1rem;

            color: var(--dark-accent);

        }

       

        .feature-card p {

            font-size: 0.9rem;

            color: #666;

        }

       

        /* Newsletter */

        .newsletter {

            padding: 8rem 0;

            background-color: var(--primary-color);

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

            background: radial-gradient(circle at 30% 50%, rgba(255, 255, 255, 0.1) 0%, rgba(255, 255, 255, 0) 70%);

            z-index: 0;

        }

       

        .newsletter-content {

            position: relative;

            z-index: 1;

            max-width: 700px;

            margin: 0 auto;

        }

       

        .newsletter h2 {

            font-size: 3rem;

            margin-bottom: 1.5rem;

        }

       

        .newsletter p {

            font-size: 1.1rem;

            max-width: 600px;

            margin: 0 auto 3rem;

            opacity: 0.9;

        }

       

        .newsletter-form {

            display: flex;

            max-width: 500px;

            margin: 0 auto;

            position: relative;

        }

       

        .newsletter-form input {

            flex-grow: 1;

            padding: 15px 20px;

            border: none;

            border-radius: 0;

            font-family: var(--font-body);

            font-size: 1rem;

        }

       

        .newsletter-form button {

            background-color: var(--dark-accent);

            color: white;

            border: none;

            padding: 0 30px;

            font-size: 0.9rem;

            letter-spacing: 1px;

            text-transform: uppercase;

            transition: all var(--transition-fast);

        }

       

        .newsletter-form button:hover {

            background-color: var(--accent-color);

            color: var(--text-dark);

        }

       

        /* Footer */

        footer {

            background-color: #2c2420;

            color: #e0d8d2;

            padding: 6rem 0 2rem;

        }

       

        .footer-content {

            display: grid;

            grid-template-columns: 2fr 1fr 1fr 1fr;

            gap: 4rem;

        }

       

        .footer-logo {

            font-family: var(--font-heading);

            font-size: 2rem;

            letter-spacing: 3px;

            color: white;

            margin-bottom: 1.5rem;

        }

       

        .footer-about p {

            font-size: 0.9rem;

            margin-bottom: 2rem;

            opacity: 0.8;

            line-height: 1.8;

        }

       

        .footer-social {

            display: flex;

            gap: 1rem;

        }

       

        .social-icon {

            width: 40px;

            height: 40px;

            border-radius: 50%;

            background-color: rgba(255, 255, 255, 0.1);

            display: flex;

            align-items: center;

            justify-content: center;

            transition: all var(--transition-fast);

        }

       

        .social-icon:hover {

            background-color: var(--accent-color);

            color: var(--text-dark);

            transform: translateY(-3px);

        }

       

        .footer-section h3 {

            font-family: var(--font-subheading);

            font-size: 1.2rem;

            margin-bottom: 1.5rem;

            color: white;

            position: relative;

            padding-bottom: 0.8rem;

        }

       

        .footer-section h3::after {

            content: '';

            position: absolute;

            width: 40px;

            height: 2px;

            background-color: var(--accent-color);

            bottom: 0;

            left: 0;

        }

       

        .footer-links {

            display: flex;

            flex-direction: column;

        }

       

        .footer-link {

            margin-bottom: 1rem;

            font-size: 0.9rem;

            opacity: 0.8;

            transition: all var(--transition-fast);

            display: flex;

            align-items: center;

        }

       

        .footer-link i {

            margin-right: 10px;

            font-size: 0.8rem;

        }

       

        .footer-link:hover {

            opacity: 1;

            color: var(--accent-color);

            transform: translateX(5px);

        }

       

        .footer-contact p {

            display: flex;

            align-items: flex-start;

            margin-bottom: 1rem;

            font-size: 0.9rem;

            opacity: 0.8;

        }

       

        .footer-contact i {

            margin-right: 15px;

            margin-top: 5px;

        }

       

        .footer-bottom {

            margin-top: 4rem;

            padding-top: 2rem;

            border-top: 1px solid rgba(255, 255, 255, 0.1);

            display: flex;

            justify-content: space-between;

            align-items: center;

        }

       

        .copyright {

            font-size: 0.8rem;

            opacity: 0.7;

        }

       

        .footer-bottom-links {

            display: flex;

            gap: 2rem;

        }

       

        .footer-bottom-link {

            font-size: 0.8rem;

            opacity: 0.7;

            transition: all var(--transition-fast);

        }

       

        .footer-bottom-link:hover {

            opacity: 1;

            color: var(--accent-color);

        }

       

        /* Animations */

        @keyframes fadeIn {

            from {

                opacity: 0;

            }

            to {

                opacity: 1;

            }

        }

       

        @keyframes fadeInUp {

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

                transform: translateX(20px);

            }

            to {

                opacity: 1;

                transform: translateX(0);

            }

        }

       

        @keyframes scrollDown {

            0% {

                opacity: 1;

                transform: translateX(-50%) translateY(0);

            }

            75% {

                opacity: 0;

                transform: translateX(-50%) translateY(20px);

            }

            76% {

                opacity: 0;

                transform: translateX(-50%) translateY(0);

            }

            100% {

                opacity: 1;

                transform: translateX(-50%) translateY(0);

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

       

        /* Responsive Design */

        @media (max-width: 1200px) {

            .hero-title {

                font-size: 4rem;

            }

           

            .showcase-content {

                flex-direction: column;

                gap: 3rem;

            }

           

            .footer-content {

                grid-template-columns: repeat(2, 1fr);

            }

        }

       

        @media (max-width: 992px) {

            .nav-links {

                display: none;

                position: fixed;

                top: 0;

                left: 0;

                width: 100%;

                height: 100vh;

                background-color: var(--secondary-color);

                flex-direction: column;

                justify-content: center;

                align-items: center;

                gap: 2rem;

                z-index: 1;

            }

           

            .nav-links.active {

                display: flex;

            }

           

            .menu-toggle {

                display: block;

            }

           

            .hero-content {

                flex-direction: column;

                text-align: center;

                padding-top: 6rem;

            }

           

            .hero-text {

                margin-bottom: 3rem;

            }

           

            .hero-image-container {

                width: 80%;

                height: 50%;

            }

           

            .hero-title {

                font-size: 3.5rem;

            }

           

            .section-title {

                font-size: 2.5rem;

            }

           

            .features-grid {

                grid-template-columns: repeat(2, 1fr);

            }

        }

       

        @media (max-width: 768px) {

            .hero-title {

                font-size: 3rem;

            }

           

            .product-grid {

                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));

            }

           

            .features-grid {

                grid-template-columns: 1fr;

            }

           

            .newsletter-form {

                flex-direction: column;

                gap: 1rem;

            }

           

            .newsletter-form input,

            .newsletter-form button {

                width: 100%;

            }

           

            .footer-content {

                grid-template-columns: 1fr;

                gap: 3rem;

            }

           

            .footer-bottom {

                flex-direction: column;

                gap: 1rem;

                text-align: center;

            }

        }

       

        @media (max-width: 576px) {

            .hero-title {

                font-size: 2.5rem;

            }

           

            .hero-subtitle {

                font-size: 1rem;

            }

           

            .hero-description {

                font-size: 1rem;

            }

           

            .section-title {

                font-size: 2rem;

            }

           

            .collection-slide {

                height: 400px;

            }

        }

    </style>

</head>

<body>

    <!-- Custom Cursor -->

    <div class="custom-cursor"></div>

   

    <!-- Navigation -->

    <nav class="nav-container">

        <div class="nav-content">

            <a href="#" class="logo">LUMINOUS</a>

            <div class="nav-links">

                <a href="#" class="nav-link">Home</a>

                <a href="#" class="nav-link">Shop</a>

                <a href="#" class="nav-link">Collections</a>

                <a href="#" class="nav-link">About</a>

                <a href="#" class="nav-link">Contact</a>

            </div>

            <div class="nav-actions">

                <a href="#" class="nav-icon"><i class="fas fa-search"></i></a>

                <a href="#" class="nav-icon"><i class="fas fa-user"></i></a>

                <a href="#" class="nav-icon">

                    <i class="fas fa-shopping-bag"></i>

                    <span class="cart-count">3</span>

                </a>

            </div>

            <button class="menu-toggle">

                <i class="fas fa-bars"></i>

            </button>

        </div>

    </nav>

   

    <!-- Hero Section -->

    <section class="hero">

        <div class="hero-bg"></div>

        <div class="floating-elements">

            <div class="floating-element"></div>

            <div class="floating-element"></div>

            <div class="floating-element"></div>

        </div>

        <div class="hero-content">

            <div class="hero-text">

                <h6 class="hero-subtitle">Artisan Crafted</h6>

                <h1 class="hero-title">Illuminate Your Space</h1>

                <p class="hero-description">Discover our collection of handcrafted luxury candles designed to transform your environment with exquisite scents and elegant aesthetics.</p>

                <button class="cta-button">Explore Collection</button>

            </div>

            <div class="hero-image-container">

                <div class="hero-image"></div>

            </div>

        </div>

        <div class="scroll-indicator">

            <span class="scroll-text">Scroll Down</span>

            <div class="scroll-icon"></div>

        </div>

    </section>

   

    <!-- Featured Products -->

    <section class="featured-products">

        <div class="container">

            <div class="text-center">

                <h2 class="section-title">Bestsellers</h2>

                <p>Our most coveted fragrances, crafted with premium ingredients</p>

            </div>

            <div class="product-grid">

                <div class="product-card">

                    <div class="product-image">

                        <img src="https://placehold.co/400x600" alt="Midnight Jasmine Candle">

                        <div class="product-overlay">

                            <span class="burn-time">65 hours</span>

                        </div>

                        <div class="product-actions">

                            <button class="product-action-btn"><i class="far fa-heart"></i></button>

                            <button class="product-action-btn"><i class="fas fa-eye"></i></button>

                            <button class="product-action-btn"><i class="fas fa-shopping-cart"></i></button>

                        </div>

                    </div>

                    <div class="product-info">

                        <span class="product-category">Floral Collection</span>

                        <h3>Midnight Jasmine</h3>

                        <p>A luxurious blend of night-blooming jasmine, Madagascar vanilla, and white musk. Notes of ylang-ylang and bergamot create an enchanting evening ambiance.</p>

                        <div class="product-details">

                            <span class="weight">350g</span>

                            <span class="separator">•</span>

                            <span class="wax-type">Soy Blend</span>

                        </div>

                        <div class="product-bottom">

                            <span class="price">$58.00</span>

                            <button class="add-to-cart">Add to Cart</button>

                        </div>

                    </div>

                </div>

               

                <div class="product-card">

                    <div class="product-image">

                        <img src="https://placehold.co/400x600" alt="Amber & Sandalwood Candle">

                        <div class="product-overlay">

                            <span class="burn-time">70 hours</span>

                        </div>

                        <div class="product-actions">

                            <button class="product-action-btn"><i class="far fa-heart"></i></button>

                            <button class="product-action-btn"><i class="fas fa-eye"></i></button>

                            <button class="product-action-btn"><i class="fas fa-shopping-cart"></i></button>

                        </div>

                    </div>

                    <div class="product-info">

                        <span class="product-category">Woody Collection</span>

                        <h3>Amber & Sandalwood</h3>

                        <p>Rich notes of amber and sandalwood blend with warm vanilla and cedarwood. A sophisticated fragrance that creates a cozy, inviting atmosphere.</p>

                        <div class="product-details">

                            <span class="weight">400g</span>

                            <span class="separator">•</span>

                            <span class="wax-type">Coconut Blend</span>

                        </div>

                        <div class="product-bottom">

                            <span class="price">$62.00</span>

                            <button class="add-to-cart">Add to Cart</button>

                        </div>

                    </div>

                </div>

               

                <div class="product-card">

                    <div class="product-image">

                        <img src="https://placehold.co/400x600" alt="Mediterranean Fig Candle">

                        <div class="product-overlay">

                            <span class="burn-time">60 hours</span>

                        </div>

                        <div class="product-actions">

                            <button class="product-action-btn"><i class="far fa-heart"></i></button>

                            <button class="product-action-btn"><i class="fas fa-eye"></i></button>

                            <button class="product-action-btn"><i class="fas fa-shopping-cart"></i></button>

                        </div>

                    </div>

                    <div class="product-info">

                        <span class="product-category">Fresh Collection</span>

                        <h3>Mediterranean Fig</h3>

                        <p>Sun-ripened figs blend with notes of bergamot and vetiver. This fresh, green scent evokes the essence of Mediterranean gardens in summer.</p>

                        <div class="product-details">

                            <span class="weight">320g</span>

                            <span class="separator">•</span>

                            <span class="wax-type">Beeswax Blend</span>

                        </div>

                        <div class="product-bottom">

                            <span class="price">$54.00</span>

                            <button class="add-to-cart">Add to Cart</button>

                        </div>

                    </div>

                </div>

            </div>

        </div>

    </section>

   

    <!-- Collection Showcase -->

    <section class="collection-showcase">

        <div class="collection-bg"></div>

        <div class="container collection-content">

            <div class="collection-text">

                <h2 class="section-title">Our Collections</h2>

                <p>Explore our curated collections, each designed to evoke a distinct mood and atmosphere</p>

            </div>

            <div class="collection-slider">

                <div class="swiper-container">

                    <div class="swiper-wrapper">

                        <div class="swiper-slide">

                            <div class="collection-slide">

                                <img src="https://placehold.co/800x800" alt="Botanical Collection">

                                <div class="collection-info">

                                    <h3>Botanical Collection</h3>

                                    <p>Fresh, green scents inspired by nature's garden</p>

                                    <a href="#" class="collection-link">Explore Collection <i class="fas fa-arrow-right"></i></a>

                                </div>

                            </div>

                        </div>

                        <div class="swiper-slide">

                            <div class="collection-slide">

                                <img src="https://placehold.co/800x800" alt="Noir Collection">

                                <div class="collection-info">

                                    <h3>Noir Collection</h3>

                                    <p>Deep, mysterious fragrances for evening ambiance</p>

                                    <a href="#" class="collection-link">Explore Collection <i class="fas fa-arrow-right"></i></a>

                                </div>

                            </div>

                        </div>

                        <div class="swiper-slide">

                            <div class="collection-slide">

                                <img src="https://placehold.co/800x800" alt="Coastal Collection">

                                <div class="collection-info">

                                    <h3>Coastal Collection</h3>

                                    <p>Ocean-inspired scents that evoke seaside memories</p>

                                    <a href="#" class="collection-link">Explore Collection <i class="fas fa-arrow-right"></i></a>

                                </div>

                            </div>

                        </div>

                        <div class="swiper-slide">

                            <div class="collection-slide">

                                <img src="https://placehold.co/800x800" alt="Spice Route Collection">

                                <div class="collection-info">

                                    <h3>Spice Route Collection</h3>

                                    <p>Exotic fragrances inspired by ancient trade routes</p>

                                    <a href="#" class="collection-link">Explore Collection <i class="fas fa-arrow-right"></i></a>

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

    </section>

   

    <!-- 3D Product Showcase -->

    <section class="product-3d-showcase">

        <div class="container">

            <div class="showcase-content">

                <div class="showcase-text">

                    <h2 class="section-title">Experience Our Craftsmanship</h2>

                    <p>Each Luminous candle is meticulously crafted using traditional techniques and premium materials. Our commitment to quality ensures an exceptional sensory experience.</p>

                   

                    <div class="showcase-features">

                        <div class="showcase-feature">

                            <div class="feature-icon">

                                <i class="fas fa-leaf"></i>

                            </div>

                            <div class="feature-text">

                                <h4>Sustainable Materials</h4>

                                <p>We use ethically sourced, sustainable ingredients in all our products.</p>

                            </div>

                        </div>

                       

                        <div class="showcase-feature">

                            <div class="feature-icon">

                                <i class="fas fa-fire-alt"></i>

                            </div>

                            <div class="feature-text">

                                <h4>Clean Burning</h4>

                                <p>Our proprietary wax blend ensures a clean, even burn with minimal soot.</p>

                            </div>

                        </div>

                       

                        <div class="showcase-feature">

                            <div class="feature-icon">

                                <i class="fas fa-flask"></i>

                            </div>

                            <div class="feature-text">

                                <h4>Master Perfumers</h4>

                                <p>We collaborate with world-class perfumers to create unique, complex fragrances.</p>

                            </div>

                        </div>

                    </div>

                   

                    <button class="cta-button">Discover Our Process</button>

                </div>

               

                <div class="showcase-3d">

                    <div class="canvas-container">

                        <div class="canvas-placeholder"></div>

                    </div>

                    <div class="rotate-hint">

                        <i class="fas fa-sync-alt"></i>

                        <span>Rotate to explore</span>

                    </div>

                </div>

            </div>

        </div>

    </section>

   

    <!-- Features -->

    <section class="features">

        <div class="container">

            <div class="text-center">

                <h2 class="section-title">Why Choose Luminous</h2>

                <p>Elevate your space with our premium candle collection</p>

            </div>

           

            <div class="features-grid">

                <div class="feature-card">

                    <i class="fas fa-shipping-fast"></i>

                    <h3>Complimentary Shipping</h3>

                    <p>Enjoy free shipping on all orders over $75. We carefully package each item to ensure safe delivery.</p>

                </div>

               

                <div class="feature-card">

                    <i class="fas fa-hand-holding-heart"></i>

                    <h3>Handcrafted Quality</h3>

                    <p>Each candle is handcrafted in small batches to ensure exceptional quality and attention to detail.</p>

                </div>

               

                <div class="feature-card">

                    <i class="fas fa-recycle"></i>

                    <h3>Sustainable Practices</h3>

                    <p>Our commitment to sustainability extends from our ingredients to our recyclable packaging.</p>

                </div>

            </div>

        </div>

    </section>

   

    <!-- Newsletter -->

    <section class="newsletter">

        <div class="newsletter-bg"></div>

        <div class="container newsletter-content">

            <h2>Join Our Community</h2>

            <p>Subscribe to receive exclusive offers, early access to new collections, and expert tips on creating the perfect ambiance.</p>

            <form class="newsletter-form">

                <input type="email" placeholder="Enter your email address" required>

                <button type="submit">Subscribe</button>

            </form>

        </div>

    </section>

   

    <!-- Footer -->

    <footer>

        <div class="container">

            <div class="footer-content">

                <div class="footer-about">

                    <div class="footer-logo">LUMINOUS</div>

                    <p>At Luminous, we believe in the transformative power of scent. Our artisan candles are crafted to enhance your space and create moments of tranquility in your everyday life.</p>

                    <div class="footer-social">

                        <a href="#" class="social-icon"><i class="fab fa-instagram"></i></a>

                        <a href="#" class="social-icon"><i class="fab fa-pinterest"></i></a>

                        <a href="#" class="social-icon"><i class="fab fa-facebook-f"></i></a>

                        <a href="#" class="social-icon"><i class="fab fa-twitter"></i></a>

                    </div>

                </div>

               

                <div class="footer-section">

                    <h3>Shop</h3>

                    <div class="footer-links">

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> All Products</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Collections</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Gift Sets</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Accessories</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Limited Editions</a>

                    </div>

                </div>

               

                <div class="footer-section">

                    <h3>About</h3>

                    <div class="footer-links">

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Our Story</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Craftsmanship</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Sustainability</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Press</a>

                        <a href="#" class="footer-link"><i class="fas fa-chevron-right"></i> Careers</a>

                    </div>

                </div>

               

                <div class="footer-section">

                    <h3>Contact</h3>

                    <div class="footer-contact">

                        <p><i class="fas fa-map-marker-alt"></i> 123 Artisan Way, New York, NY 10001</p>

                        <p><i class="fas fa-phone-alt"></i> +1 (212) 555-7890</p>

                        <p><i class="fas fa-envelope"></i> hello@luminouscandles.com</p>

                    </div>

                </div>

            </div>

           

            <div class="footer-bottom">

                <div class="copyright">© 2025 Luminous. All rights reserved.</div>

                <div class="footer-bottom-links">

                    <a href="#" class="footer-bottom-link">Privacy Policy</a>

                    <a href="#" class="footer-bottom-link">Terms of Service</a>

                    <a href="#" class="footer-bottom-link">Shipping & Returns</a>

                </div>

            </div>

        </div>

    </footer>

   

    <!-- Custom Scripts -->

    <script>

        // Initialize GSAP ScrollTrigger

        gsap.registerPlugin(ScrollTrigger);

       

        // Navigation scroll effect

        window.addEventListener('scroll', function() {

            const nav = document.querySelector('.nav-container');

            if (window.scrollY > 50) {

                nav.classList.add('scrolled');

            } else {

                nav.classList.remove('scrolled');

            }

        });

       

        // Mobile menu toggle

        const menuToggle = document.querySelector('.menu-toggle');

        const navLinks = document.querySelector('.nav-links');

       

        menuToggle.addEventListener('click', function() {

            navLinks.classList.toggle('active');

            document.body.classList.toggle('menu-open');

        });

       

        // Custom cursor

        const cursor = document.querySelector('.custom-cursor');

       

        document.addEventListener('mousemove', (e) => {

            cursor.style.left = e.clientX + 'px';

            cursor.style.top = e.clientY + 'px';

        });

       

        document.addEventListener('mousedown', () => {

            cursor.classList.add('active');

        });

       

        document.addEventListener('mouseup', () => {

            cursor.classList.remove('active');

        });

       

        // Add hover effect for interactive elements

        const interactiveElements = document.querySelectorAll('a, button, .product-card, .collection-slide, .feature-card');

       

        interactiveElements.forEach(element => {

            element.addEventListener('mouseenter', () => {

                cursor.classList.add('active');

            });

           

            element.addEventListener('mouseleave', () => {

                cursor.classList.remove('active');

            });

        });

       

        // Initialize Swiper

        const swiper = new Swiper('.swiper-container', {

            slidesPerView: 1,

            spaceBetween: 30,

            loop: true,

            centeredSlides: true,

            autoplay: {

                delay: 5000,

                disableOnInteraction: false,

            },

            pagination: {

                el: '.swiper-pagination',

                clickable: true,

            },

            navigation: {

                nextEl: '.swiper-button-next',

                prevEl: '.swiper-button-prev',

            },

            breakpoints: {

                640: {

                    slidesPerView: 1.5,

                },

                992: {

                    slidesPerView: 2.5,

                }

            }

        });

       

        // GSAP Animations

        // Hero section animations are handled with CSS for initial load

       

        // Scroll animations for sections

        const sections = document.querySelectorAll('section:not(.hero)');

       

        sections.forEach(section => {

            gsap.from(section.querySelector('.section-title'), {

                scrollTrigger: {

                    trigger: section,

                    start: "top 80%"

                },

                y: 50,

                opacity: 0,

                duration: 1

            });

           

            if (section.querySelector('p:not(.hero-description)')) {

                gsap.from(section.querySelector('p:not(.hero-description)'), {

                    scrollTrigger: {

                        trigger: section,

                        start: "top 80%"

                    },

                    y: 30,

                    opacity: 0,

                    duration: 1,

                    delay: 0.2

                });

            }

        });

       

        // Product cards animation

        gsap.from('.product-card',


](https://github.com/caseybattle/LuminousLux.git)
