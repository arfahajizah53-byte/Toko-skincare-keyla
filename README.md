<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GlowBeauty - Toko Skincare Online</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 50%, #ffafbd 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        header {
            background: white;
            padding: 30px;
            border-radius: 30px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            margin-bottom: 30px;
        }

        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .logo {
            font-size: 36px;
            font-weight: bold;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tagline {
            font-size: 14px;
            color: #999;
            margin-top: 5px;
        }

        .member-badge {
            background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%);
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            font-size: 13px;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .header-actions {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .btn-header {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 15px;
            font-weight: bold;
            box-shadow: 0 8px 25px rgba(240, 147, 251, 0.4);
            transition: transform 0.3s;
            position: relative;
        }

        .btn-header:hover {
            transform: translateY(-3px);
        }

        .cart-count, .wishlist-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #FF1744;
            color: white;
            border-radius: 50%;
            width: 24px;
            height: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            font-weight: bold;
        }

        .search-section {
            margin-top: 20px;
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .search-bar {
            flex: 1;
            min-width: 250px;
            position: relative;
        }

        .search-bar input {
            width: 100%;
            padding: 15px 50px 15px 20px;
            border: 3px solid #ffecd2;
            border-radius: 30px;
            font-size: 15px;
            outline: none;
            transition: all 0.3s;
        }

        .search-bar input:focus {
            border-color: #f093fb;
            box-shadow: 0 5px 20px rgba(240, 147, 251, 0.3);
        }

        .search-icon {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 22px;
        }

        .skin-type-selector {
            display: flex;
            gap: 10px;
        }

        .skin-type-btn {
            padding: 12px 20px;
            border: 2px solid #f093fb;
            background: white;
            color: #f093fb;
            border-radius: 25px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.3s;
        }

        .skin-type-btn.active {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
        }

        .filters {
            background: white;
            padding: 25px;
            border-radius: 30px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            margin-bottom: 30px;
        }

        .filter-section {
            margin-bottom: 20px;
        }

        .filter-section:last-child {
            margin-bottom: 0;
        }

        .filter-title {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 15px;
            color: #f5576c;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .filter-buttons {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 12px 24px;
            border: 2px solid #f093fb;
            background: white;
            color: #f5576c;
            border-radius: 30px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.3s;
        }

        .filter-btn.active {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            border-color: #f093fb;
            transform: scale(1.05);
        }

        .filter-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(240, 147, 251, 0.3);
        }

        .promo-banner {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 25px;
            border-radius: 25px;
            margin-bottom: 30px;
            text-align: center;
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
        }

        .promo-banner h2 {
            font-size: 26px;
            margin-bottom: 10px;
        }

        .promo-code {
            background: white;
            color: #667eea;
            padding: 8px 20px;
            border-radius: 20px;
            font-weight: bold;
            display: inline-block;
            margin-top: 5px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .product-card {
            background: white;
            border-radius: 30px;
            overflow: hidden;
            box-shadow: 0 15px 45px rgba(0,0,0,0.15);
            transition: all 0.3s;
            cursor: pointer;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 60px rgba(0,0,0,0.25);
        }

        .product-image {
            width: 100%;
            height: 280px;
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 100px;
            position: relative;
            overflow: hidden;
        }

        .product-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background: #FF1744;
            color: white;
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 12px;
            font-weight: bold;
            z-index: 10;
        }

        .product-badge.new {
            background: #00E676;
        }

        .product-badge.best {
            background: #FFD700;
            color: #333;
        }

        .wishlist-icon {
            position: absolute;
            top: 15px;
            right: 15px;
            background: white;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            cursor: pointer;
            transition: all 0.3s;
            z-index: 10;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
        }

        .wishlist-icon:hover {
            transform: scale(1.2);
        }

        .wishlist-icon.active {
            background: #FF1744;
        }

        .product-info {
            padding: 25px;
        }

        .product-brand {
            color: #f5576c;
            font-size: 13px;
            font-weight: 600;
            text-transform: uppercase;
            margin-bottom: 8px;
            letter-spacing: 1px;
        }

        .product-name {
            font-size: 19px;
            font-weight: bold;
            margin-bottom: 10px;
            color: #333;
            line-height: 1.3;
        }

        .product-description {
            font-size: 14px;
            color: #666;
            margin-bottom: 12px;
            line-height: 1.5;
        }

        .product-benefits {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-bottom: 12px;
        }

        .benefit-tag {
            background: #f0f0f0;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 11px;
            color: #666;
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: 8px;
            margin-bottom: 15px;
        }

        .stars {
            color: #FFD700;
            font-size: 16px;
        }

        .rating-text {
            color: #666;
            font-size: 13px;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 2px solid #f5f5f5;
        }

        .product-price {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }

        .price-current {
            font-size: 24px;
            font-weight: bold;
            color: #f5576c;
        }

        .price-original {
            font-size: 14px;
            color: #999;
            text-decoration: line-through;
        }

        .add-to-cart {
            padding: 12px 20px;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 14px;
            font-weight: bold;
            transition: transform 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .add-to-cart:hover {
            transform: scale(1.08);
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            border-radius: 30px;
            padding: 35px;
            max-width: 650px;
            width: 100%;
            max-height: 85vh;
            overflow-y: auto;
            box-shadow: 0 30px 80px rgba(0,0,0,0.5);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }

        .modal-title {
            font-size: 28px;
            font-weight: bold;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .close-btn {
            background: none;
            border: none;
            font-size: 35px;
            cursor: pointer;
            color: #999;
            line-height: 1;
            transition: color 0.3s;
        }

        .close-btn:hover {
            color: #333;
        }

        .cart-item {
            display: flex;
            gap: 20px;
            padding: 20px;
            border-bottom: 2px solid #f5f5f5;
            align-items: center;
        }

        .cart-item-icon {
            font-size: 50px;
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .cart-item-info {
            flex: 1;
        }

        .cart-item-brand {
            font-size: 12px;
            color: #f5576c;
            font-weight: 600;
            margin-bottom: 5px;
        }

        .cart-item-name {
            font-weight: bold;
            font-size: 16px;
            margin-bottom: 8px;
            color: #333;
        }

        .cart-item-price {
            color: #f5576c;
            font-weight: bold;
            font-size: 18px;
        }

        .cart-item-quantity {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-top: 10px;
        }

        .qty-btn {
            background: #f5576c;
            color: white;
            border: none;
            width: 32px;
            height: 32px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.2s;
        }

        .qty-btn:hover {
            transform: scale(1.15);
        }

        .qty-display {
            font-weight: bold;
            min-width: 30px;
            text-align: center;
            font-size: 16px;
        }

        .cart-item-remove {
            background: #FF1744;
            color: white;
            border: none;
            padding: 10px 18px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 13px;
            font-weight: bold;
            transition: transform 0.3s;
        }

        .cart-item-remove:hover {
            transform: scale(1.05);
        }

        .cart-total {
            margin-top: 25px;
            padding-top: 25px;
            border-top: 3px solid #ffecd2;
        }

        .total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 12px;
            font-size: 16px;
        }

        .total-row.discount {
            color: #00E676;
            font-weight: bold;
        }

        .total-row.grand-total {
            font-size: 26px;
            font-weight: bold;
            color: #f5576c;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 2px solid #ffecd2;
        }

        .promo-section {
            margin: 20px 0;
            padding: 15px;
            background: #f8f8f8;
            border-radius: 20px;
        }

        .promo-input-group {
            display: flex;
            gap: 10px;
        }

        .promo-input {
            flex: 1;
            padding: 12px 20px;
            border: 2px solid #ffecd2;
            border-radius: 25px;
            font-size: 14px;
            outline: none;
        }

        .apply-promo-btn {
            padding: 12px 25px;
            background: #667eea;
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            transition: transform 0.3s;
        }

        .apply-promo-btn:hover {
            transform: scale(1.05);
        }

        .checkout-btn {
            width: 100%;
            margin-top: 20px;
            padding: 18px;
            background: linear-gradient(135deg, #00E676 0%, #00C853 100%);
            color: white;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
            transition: transform 0.3s;
        }

        .checkout-btn:hover {
            transform: scale(1.03);
        }

        .empty-cart {
            text-align: center;
            padding: 50px 20px;
            color: #999;
        }

        .empty-cart-icon {
            font-size: 80px;
            margin-bottom: 20px;
        }

        .beauty-tips {
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            padding: 20px;
            border-radius: 20px;
            margin-top: 20px;
            text-align: center;
        }

        .beauty-tips h3 {
            color: #f5576c;
            margin-bottom: 10px;
        }

        .beauty-tips p {
            color: #666;
            font-size: 14px;
            line-height: 1.6;
        }

        @media (max-width: 768px) {
            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
                gap: 20px;
            }

            .product-image {
                height: 220px;
                font-size: 80px;
            }

            .logo {
                font-size: 28px;
            }

            .header-actions {
                width: 100%;
            }

            .btn-header {
                flex: 1;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="header-top">
                <div>
                    <div class="logo">✨ GlowBeauty</div>
                    <div class="tagline">Your Skin, Our Passion</div>
                </div>
                <div class="member-badge">
                    👑 Member Gold
                </div>
            </div>
            <div class="header-top" style="margin-top: 20px;">
                <div class="header-actions">
                    <button class="btn-header" onclick="toggleWishlist()">
                        💝 Wishlist
                        <span class="wishlist-count" id="wishlistCount">0</span>
                    </button>
                    <button class="btn-header" onclick="toggleCart()">
                        🛒 Keranjang
                        <span class="cart-count" id="cartCount">0</span>
                    </button>
                </div>
            </div>
            <div class="search-section">
                <div class="search-bar">
                    <input type="text" id="searchInput" placeholder="Cari produk skincare impian Anda..." onkeyup="searchProducts()">
                    <span class="search-icon">🔍</span>
                </div>
            </div>
        </header>

        <div class="promo-banner">
            <h2>🎁 Flash Sale! Diskon Hingga 30%</h2>
            <p>Gunakan kode promo untuk mendapatkan diskon spesial</p>
            <span class="promo-code">GLOWUP30</span>
        </div>

        <div class="filters">
            <div class="filter-section">
                <div class="filter-title">🏷️ Kategori Produk</div>
                <div class="filter-buttons">
                    <button class="filter-btn active" onclick="filterByCategory('all')">Semua Produk</button>
                    <button class="filter-btn" onclick="filterByCategory('cleanser')">Cleanser</button>
                    <button class="filter-btn" onclick="filterByCategory('serum')">Serum</button>
                    <button class="filter-btn" onclick="filterByCategory('moisturizer')">Moisturizer</button>
                    <button class="filter-btn" onclick="filterByCategory('sunscreen')">Sunscreen</button>
                    <button class="filter-btn" onclick="filterByCategory('mask')">Mask</button>
                </div>
            </div>
            
            <div class="filter-section">
                <div class="filter-title">💧 Jenis Kulit</div>
                <div class="filter-buttons">
                    <button class="filter-btn active" onclick="filterBySkinType('all')">Semua</button>
                    <button class="filter-btn" onclick="filterBySkinType('normal')">Normal</button>
                    <button class="filter-btn" onclick="filterBySkinType('kering')">Kering</button>
                    <button class="filter-btn" onclick="filterBySkinType('berminyak')">Berminyak</button>
                    <button class="filter-btn" onclick="filterBySkinType('sensitif')">Sensitif</button>
                </div>
            </div>
        </div>

        <div class="products-grid" id="productsGrid"></div>
    </div>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-title">🛒 Keranjang Belanja</div>
                <button class="close-btn" onclick="toggleCart()">&times;</button>
            </div>
            <div id="cartItems"></div>
            <div class="promo-section">
                <div class="promo-input-group">
                    <input type="text" class="promo-input" id="promoCode" placeholder="Masukkan kode promo">
                    <button class="apply-promo-btn" onclick="applyPromo()">Terapkan</button>
                </div>
            </div>
            <div class="cart-total" id="cartTotalSection"></div>
            <div class="beauty-tips">
                <h3>💡 Beauty Tips</h3>
                <p>Gunakan produk secara teratur untuk hasil optimal. Double cleansing di malam hari untuk kulit bersih sempurna!</p>
            </div>
        </div>
    </div>

    <!-- Wishlist Modal -->
    <div class="modal" id="wishlistModal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-title">💝 Wishlist Saya</div>
                <button class="close-btn" onclick="toggleWishlist()">&times;</button>
            </div>
            <div id="wishlistItems"></div>
        </div>
    </div>

    <script>
        const products = [
            { 
                id: 1, 
                name: 'Gentle Foam Cleanser', 
                brand: 'SKINLOVE',
                category: 'cleanser', 
                skinType: ['normal', 'berminyak', 'sensitif'],
                price: 89000,
                originalPrice: 120000,
                icon: '🧴', 
                badge: 'Best Seller',
                badgeType: 'best',
                description: 'Pembersih wajah dengan formula lembut untuk kulit sensitif',
                benefits: ['Hypoallergenic', 'pH Balanced', 'Non-comedogenic'],
                rating: 4.8,
                reviews: 1243
            },
            { 
                id: 2, 
                name: 'Vitamin C Brightening Serum', 
                brand: 'GLOWLAB',
                category: 'serum', 
                skinType: ['normal', 'kering', 'berminyak'],
                price: 195000,
                originalPrice: 280000,
                icon: '💧', 
                badge: 'Diskon 30%',
                badgeType: 'sale',
                description: 'Serum pencerah dengan 15% Vitamin C untuk kulit glowing',
                benefits: ['Brightening', 'Anti-aging', 'Antioxidant'],
                rating: 4.9,
                reviews: 2156
            },
            { 
                id: 3, 
                name: 'Hydrating Day Cream SPF 30', 
                brand: 'DEWYSOFT',
                category: 'moisturizer', 
                skinType: ['kering', 'normal'],
                price: 145000,
                originalPrice: null,
                icon: '🧴', 
                badge: null,
                badgeType: null,
                description: 'Pelembab harian dengan SPF 30 untuk proteksi maksimal',
                benefits: ['UV Protection', 'Hydrating', '24H Moisture'],
                rating: 4.7,
                reviews: 892
            },
            { 
                id: 4, 
                name: 'Niacinamide 10% Serum', 
                brand: 'PUREDERMA',
                category: 'serum', 
                skinType: ['berminyak', 'normal'],
                price: 125000,
                originalPrice: 175000,
                icon: '💫', 
                badge: 'New',
                badgeType: 'new',
                description: 'Serum dengan 10% Niacinamide untuk kontrol sebum',
                benefits: ['Pore Minimizer', 'Oil Control', 'Brightening'],
                rating: 4.8,
                reviews: 1567
            },
            { 
                id: 5, 
                name: 'Sunscreen Gel SPF 50+ PA++++', 
                brand: 'UVSHIELD',
                category: 'sunscreen', 
                skinType: ['normal', 'berminyak', 'sensitif'],
                price: 98000,
                originalPrice: 140000,
                icon: '☀️', 
                badge: 'Best Seller',
                badgeType: 'best',
                description: 'Sunscreen ringan dengan proteksi maksimal tanpa whitecast',
                benefits: ['No Whitecast', 'Water Resistant', 'Non-greasy'],
                rating: 4.9,
                reviews: 3421
            },
            { 
                id: 6, 
                name: 'Clay Mask Detox', 
                brand: 'CLAYPURE',
                category: 'mask', 
                skinType: ['berminyak', 'normal'],
                price: 115000,
                originalPrice: null,
                icon: '🎭', 
                badge: null,
                badgeType: null,
                description: 'Masker clay untuk membersihkan pori-pori secara mendalam',
                benefits: ['Deep Cleansing', 'Detoxifying', 'Mattifying'],
                rating: 4.6,
                reviews: 654
            },
            { 
                id: 7, 
                name: 'Hyaluronic Acid Serum', 
                brand: 'AQUABURST',
                category: 'serum', 
                skinType: ['kering', 'normal', 'sensitif'],
                price: 165000,
                originalPrice: 225000,
                icon: '💧', 
                badge: 'Diskon 27%',
                badgeType: 'sale',
                description: 'Serum super hydrating dengan 3 jenis Hyaluronic Acid',
                benefits: ['Deep Hydration', 'Plumping', 'Anti-aging'],
                rating: 4.9,
                reviews: 1889
            },
            { 
                id: 8, 
                name: 'Micellar Water 3-in-1', 
                brand: 'CLEANPRO',
                category: 'cleanser', 
                skinType: ['normal', 'sensitif', 'kering'],
                price: 75000,
                originalPrice: 95000,
                icon: '💦', 
                badge: 'New',
                badgeType: 'new',
                description: 'Pembersih makeup all-in-one tanpa bilas',
                benefits: ['Makeup Remover', 'No Rinse', 'Gentle'],
                rating: 4.7,
                reviews: 1023
            },
            { 
                id: 9, 
                name: 'Night Repair Cream', 
                brand: 'NIGHTGLOW',
                category: 'moisturizer', 
                skinType: ['normal', 'kering', 'sensitif'],
                price: 185000,
                originalPrice: null,
                icon: '🌙', 
                badge: 'Best Seller',
                badgeType: 'best',
                description: 'Krim malam untuk regenerasi kulit maksimal',
                benefits: ['Cell Regeneration', 'Anti-aging', 'Nourishing'],
                rating: 4.8,
                reviews: 1456
            },
            { 
                id: 10, 
                name: 'Sheet Mask Collagen Boost', 
                brand: 'MASKLY',
                category: 'mask', 
                skinType: ['normal', 'kering', 'sensitif'],
                price: 25000,
                originalPrice: 35000,
                icon: '🎭', 
                badge: 'Diskon 29%',
                badgeType: 'sale',
                description: 'Sheet mask dengan essence collagen untuk kulit kenyal',
                benefits: ['Firming', 'Hydrating', 'Instant Glow'],
                rating: 4.7,
                reviews: 2341
            },
            { 
                id: 11, 
                name: 'Retinol Night Serum', 
                brand: 'YOUTHLAB',
                category: 'serum', 
                skinType: ['normal', 'berminyak'],
                price: 225000,
                originalPrice: null,
                icon: '✨', 
                badge: 'Premium',
                badgeType: 'best',
                description: 'Serum retinol untuk anti-aging dan mencerahkan',
                benefits: ['Anti-wrinkle', 'Skin Renewal', 'Firming'],
                rating: 4.9,
                reviews: 876
            },
            { 
                id: 12, 
                name: 'Oil-Free Gel Moisturizer', 
                brand: 'PUREMATTE',
                category: 'moisturizer', 
                skinType: ['berminyak', 'normal'],
                price: 95000,
                originalPrice: 135000,
                icon: '💚', 
                badge: 'New',
                badgeType: 'new',
                description: 'Pelembab gel ringan untuk kulit berminyak',
                benefits: ['Oil-free', 'Non-comedogenic', 'Mattifying'],
                rating: 4.6,
                reviews: 743
            },
            { 
                id: 13, 
                name: 'Exfoliating Toner AHA BHA', 
                brand: 'SMOOTHSKIN',
                category: 'cleanser', 
                skinType: ['berminyak', 'normal'],
                price: 135000,
                originalPrice: 180000,
                icon: '🧪', 
                badge: 'Diskon 25%',
                badgeType: 'sale',
                description: 'Toner eksfoliasi untuk kulit lebih halus dan cerah',
                benefits: ['Exfoliating', 'Pore Refining', 'Brightening'],
                rating: 4.8,
                reviews: 1234
            },
            { 
                id: 14, 
                name: 'Mineral Sunscreen Stick SPF 50', 
                brand: 'SHIELDPRO',
                category: 'sunscreen', 
                skinType: ['normal', 'sensitif', 'kering'],
                price: 125000,
                originalPrice: null,
                icon: '🌞', 
                badge: null,
                badgeType: null,
                description: 'Sunscreen stick praktis untuk reapply on-the-go',
                benefits: ['Mineral Based', 'Easy Application', 'Travel-friendly'],
                rating: 4.7,
                reviews: 567
            },
            { 
                id: 15, 
                name: 'Sleeping Mask Lavender', 
                brand: 'DREAMSKIN',
                category: 'mask', 
                skinType: ['normal', 'kering', 'sensitif'],
                price: 155000,
                originalPrice: 210000,
                icon: '😴', 
                badge: 'Best Seller',
                badgeType: 'best',
                description: 'Sleeping mask dengan aroma lavender yang menenangkan',
                benefits: ['Overnight Treatment', 'Calming', 'Hydrating'],
                rating: 4.9,
                reviews: 1987
            }
        ];

        let cart = [];
        let wishlist = [];
        let currentCategory = 'all';
        let currentSkinType = 'all';
        let currentSearch = '';
        let promoApplied = false;
        let discountAmount = 0;

        function renderProducts() {
            const grid = document.getElementById('productsGrid');
            let filteredProducts = products;

            if (currentCategory !== 'all') {
                filteredProducts = filteredProducts.filter(p => p.category === currentCategory);
            }

            if (currentSkinType !== 'all') {
                filteredProducts = filteredProducts.filter(p => p.skinType.includes(currentSkinType));
            }

            if (currentSearch) {
                filteredProducts = filteredProducts.filter(p => 
                    p.name.toLowerCase().includes(currentSearch.toLowerCase()) ||
                    p.brand.toLowerCase().includes(currentSearch.toLowerCase()) ||
                    p.description.toLowerCase().includes(currentSearch.toLowerCase())
                );
            }

            grid.innerHTML = filteredProducts.map(product => {
                const isInWishlist = wishlist.some(item => item.id === product.id);
                const stars = '⭐'.repeat(Math.floor(product.rating));
                
                return `
                    <div class="product-card">
                        <div class="product-image">
                            ${product.icon}
                            ${product.badge ? `<div class="product-badge ${product.badgeType}">${product.badge}</div>` : ''}
                            <div class="wishlist-icon ${isInWishlist ? 'active' : ''}" onclick="toggleWishlist(${product.id})">
                                ${isInWishlist ? '❤️' : '🤍'}
                            </div>
                        </div>
                        <div class="product-info">
                            <div class="product-brand">${product.brand}</div>
                            <div class="product-name">${product.name}</div>
                            <div class="product-description">${product.description}</div>
                            <div class="product-benefits">
                                ${product.benefits.map(b => `<span class="benefit-tag">✓ ${b}</span>`).join('')}
                            </div>
                            <div class="product-rating">
                                <span class="stars">${stars}</span>
                                <span class="rating-text">${product.rating} (${product.reviews})</span>
                            </div>
                            <div class="product-footer">
                                <div class="product-price">
                                    <div class="price-current">Rp ${product.price.toLocaleString('id-ID')}</div>
                                    ${product.originalPrice ? `<div class="price-original">Rp ${product.originalPrice.toLocaleString('id-ID')}</div>` : ''}
                                </div>
                                <button class="add-to-cart" onclick="addToCart(${product.id})">
                                    <span>🛒</span>
                                    Beli
                                </button>
                            </div>
                        </div>
                    </div>
                `;
            }).join('');
        }

        function filterByCategory(category) {
            currentCategory = category;
            document.querySelectorAll('.filter-section:first-child .filter-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            renderProducts();
        }

        function filterBySkinType(skinType) {
            currentSkinType = skinType;
            document.querySelectorAll('.filter-section:last-child .filter-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            renderProducts();
        }

        function searchProducts() {
            currentSearch = document.getElementById('searchInput').value;
            renderProducts();
        }

        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existingItem = cart.find(item => item.id === productId);

            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateCart();
            
            event.target.innerHTML = '<span>✓</span> Ditambahkan!';
            setTimeout(() => {
                event.target.innerHTML = '<span>🛒</span> Beli';
            }, 1200);
        }

        function updateQuantity(productId, change) {
            const item = cart.find(item => item.id === productId);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    removeFromCart(productId);
                } else {
                    updateCart();
                }
            }
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCart();
        }

        function updateCart() {
            const cartCount = document.getElementById('cartCount');
            const cartItems = document.getElementById('cartItems');
            const cartTotalSection = document.getElementById('cartTotalSection');

            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;

            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="empty-cart">
                        <div class="empty-cart-icon">🛒</div>
                        <div class="empty-cart-text">Keranjang masih kosong</div>
                        <p style="color: #999; margin-top: 10px;">Mulai belanja skincare favoritmu!</p>
                    </div>
                `;
                cartTotalSection.innerHTML = '';
                return;
            }

            cartItems.innerHTML = cart.map(item => `
                <div class="cart-item">
                    <div class="cart-item-icon">${item.icon}</div>
                    <div class="cart-item-info">
                        <div class="cart-item-brand">${item.brand}</div>
                        <div class="cart-item-name">${item.name}</div>
                        <div class="cart-item-price">Rp ${item.price.toLocaleString('id-ID')}</div>
                        <div class="cart-item-quantity">
                            <button class="qty-btn" onclick="updateQuantity(${item.id}, -1)">-</button>
                            <span class="qty-display">${item.quantity}</span>
                            <button class="qty-btn" onclick="updateQuantity(${item.id}, 1)">+</button>
                        </div>
                    </div>
                    <button class="cart-item-remove" onclick="removeFromCart(${item.id})">Hapus</button>
                </div>
            `).join('');

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const shipping = subtotal >= 200000 ? 0 : 15000;
            const discount = promoApplied ? discountAmount : 0;
            const total = subtotal + shipping - discount;

            cartTotalSection.innerHTML = `
                <div class="total-row">
                    <span>Subtotal:</span>
                    <span>Rp ${subtotal.toLocaleString('id-ID')}</span>
                </div>
                <div class="total-row">
                    <span>Ongkos Kirim:</span>
                    <span>${shipping === 0 ? 'GRATIS! 🎉' : 'Rp ' + shipping.toLocaleString('id-ID')}</span>
                </div>
                ${promoApplied ? `
                <div class="total-row discount">
                    <span>Diskon Promo:</span>
                    <span>- Rp ${discount.toLocaleString('id-ID')}</span>
                </div>
                ` : ''}
                <div class="total-row grand-total">
                    <span>Total Bayar:</span>
                    <span>Rp ${total.toLocaleString('id-ID')}</span>
                </div>
                ${subtotal < 200000 ? `
                <p style="color: #f5576c; font-size: 13px; margin-top: 10px; text-align: center;">
                    💡 Belanja Rp ${(200000 - subtotal).toLocaleString('id-ID')} lagi untuk GRATIS ONGKIR!
                </p>
                ` : ''}
                <button class="checkout-btn" onclick="checkout()">✨ Checkout Sekarang</button>
            `;
        }

        function toggleWishlistItem(productId) {
            const product = products.find(p => p.id === productId);
            const existingIndex = wishlist.findIndex(item => item.id === productId);

            if (existingIndex > -1) {
                wishlist.splice(existingIndex, 1);
            } else {
                wishlist.push(product);
            }

            updateWishlist();
            renderProducts();
        }

        function updateWishlist() {
            const wishlistCount = document.getElementById('wishlistCount');
            const wishlistItems = document.getElementById('wishlistItems');

            wishlistCount.textContent = wishlist.length;

            if (wishlist.length === 0) {
                wishlistItems.innerHTML = `
                    <div class="empty-cart">
                        <div class="empty-cart-icon">💝</div>
                        <div class="empty-cart-text">Wishlist masih kosong</div>
                        <p style="color: #999; margin-top: 10px;">Simpan produk favorit Anda di sini!</p>
                    </div>
                `;
                return;
            }

            wishlistItems.innerHTML = wishlist.map(item => {
                const stars = '⭐'.repeat(Math.floor(item.rating));
                return `
                    <div class="cart-item">
                        <div class="cart-item-icon">${item.icon}</div>
                        <div class="cart-item-info">
                            <div class="cart-item-brand">${item.brand}</div>
                            <div class="cart-item-name">${item.name}</div>
                            <div class="product-rating">
                                <span class="stars">${stars}</span>
                            </div>
                            <div class="cart-item-price">Rp ${item.price.toLocaleString('id-ID')}</div>
                        </div>
                        <button class="cart-item-remove" onclick="toggleWishlistItem(${item.id})">Hapus</button>
                    </div>
                `;
            }).join('');
        }

        function applyPromo() {
            const promoCode = document.getElementById('promoCode').value.toUpperCase();
            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);

            if (promoCode === 'GLOWUP30') {
                discountAmount = Math.floor(subtotal * 0.3);
                promoApplied = true;
                alert('✨ Selamat! Kode promo berhasil diterapkan!\n\nAnda mendapat diskon 30%: Rp ' + discountAmount.toLocaleString('id-ID'));
                updateCart();
            } else if (promoCode === 'SKINGLOW') {
                discountAmount = 100000;
                promoApplied = true;
                alert('✨ Selamat! Kode promo berhasil diterapkan!\n\nAnda mendapat diskon Rp 100.000');
                updateCart();
            } else if (promoCode === 'NEWBIE20') {
                discountAmount = Math.floor(subtotal * 0.2);
                promoApplied = true;
                alert('✨ Selamat! Kode promo member baru berhasil!\n\nAnda mendapat diskon 20%: Rp ' + discountAmount.toLocaleString('id-ID'));
                updateCart();
            } else if (promoCode === '') {
                alert('❌ Mohon masukkan kode promo');
            } else {
                alert('❌ Kode promo tidak valid\n\nCoba gunakan:\n• GLOWUP30 (Diskon 30%)\n• SKINGLOW (Diskon Rp 100K)\n• NEWBIE20 (Member Baru 20%)');
            }
        }

        function toggleCart() {
            const modal = document.getElementById('cartModal');
            modal.classList.toggle('active');
        }

        function toggleWishlist(productId = null) {
            if (productId !== null) {
                toggleWishlistItem(productId);
            } else {
                const modal = document.getElementById('wishlistModal');
                modal.classList.toggle('active');
            }
        }

        function checkout() {
            if (cart.length === 0) {
                alert('❌ Keranjang belanja masih kosong!\n\nYuk tambahkan produk skincare favoritmu! 💝');
                return;
            }

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const shipping = subtotal >= 200000 ? 0 : 15000;
            const discount = promoApplied ? discountAmount : 0;
            const total = subtotal + shipping - discount;

            const itemsList = cart.map(item => 
                `  • ${item.brand} - ${item.name} (${item.quantity}x)\n    Rp ${(item.price * item.quantity).toLocaleString('id-ID')}`
            ).join('\n');

            const orderNumber = 'GB' + Date.now().toString().slice(-8);

            alert(`✨ PESANAN BERHASIL! ✨

📦 Nomor Pesanan: ${orderNumber}

💄 Rincian Pesanan:
${itemsList}

💰 Rincian Pembayaran:
   Subtotal: Rp ${subtotal.toLocaleString('id-ID')}
   Ongkir: ${shipping === 0 ? 'GRATIS' : 'Rp ' + shipping.toLocaleString('id-ID')}
   ${promoApplied ? `Diskon: -Rp ${discount.toLocaleString('id-ID')}\n   ` : ''}
   ═══════════════════
   Total: Rp ${total.toLocaleString('id-ID')}

📱 Kami akan menghubungi Anda segera
📦 Estimasi pengiriman: 2-4 hari kerja
🎁 Bonus: Free sample untuk pembelian pertama!

💝 Terima kasih sudah berbelanja!
Dapatkan kulit glowing impian Anda! ✨`);

            cart = [];
            promoApplied = false;
            discountAmount = 0;
            document.getElementById('promoCode').value = '';
            updateCart();
            toggleCart();
        }

        // Initialize
        renderProducts();
        updateWishlist();
    </script>
</body>
</html># Toko-skincare-keyla
