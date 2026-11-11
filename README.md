<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مطعم الأصالة الشرقي | أشهى الأطباق الشرقية</title>
    <!-- استيراد خطوط عربية فاخرة -->
    <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">
    <!-- مكتبة الأيقونات FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #d4af37; /* ذهبي فاخر */
            --secondary-color: #800020; /* نبيذي/بُرغندي */
            --dark-color: #1a1a1a;
            --light-color: #f9f9f9;
            --accent-color: #2c2c2c;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Cairo', sans-serif;
        }

        body {
            background-color: var(--light-color);
            color: var(--dark-color);
            line-height: 1.6;
        }

        h1, h2, h3, .brand-font {
            font-family: 'Amiri', serif;
        }

        /* شريط التنقل */
        header {
            background-color: var(--dark-color);
            color: #fff;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .navbar {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
        }

        .logo {
            font-size: 24px;
            color: var(--primary-color);
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 25px;
        }

        .nav-links a {
            color: #fff;
            text-decoration: none;
            transition: color 0.3s;
            font-size: 16px;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .cart-btn {
            background-color: var(--primary-color);
            color: var(--dark-color);
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
        }

        /* تأثير التوهج والإضاءة الجميل للسلة عند التفاعل */
        @keyframes cartGlow {
            0% { transform: scale(1); box-shadow: 0 0 5px #d4af37; }
            50% { transform: scale(1.15); box-shadow: 0 0 20px #d4af37, 0 0 30px #ffdf73; background-color: #fff; color: #800020; }
            100% { transform: scale(1); box-shadow: 0 0 5px #d4af37; }
        }

        .cart-glow {
            animation: cartGlow 0.6s ease;
        }

        .cart-btn:hover {
            background-color: #e5c158;
        }

        /* قسم الواجهة الرئيسية (Hero) */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80') no-repeat center center/cover;
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: #fff;
            padding: 0 20px;
            margin-top: 60px;
        }

        .hero h1 {
            font-size: 48px;
            color: var(--primary-color);
            margin-bottom: 15px;
        }

        .hero p {
            font-size: 20px;
            margin-bottom: 25px;
            max-width: 600px;
        }

        .btn-main {
            background-color: var(--secondary-color);
            color: #fff;
            padding: 12px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: background 0.3s;
        }

        .btn-main:hover {
            background-color: #a30029;
        }

        /* قسم القائمة */
        .menu-section {
            max-width: 1200px;
            margin: 50px auto;
            padding: 0 20px;
        }

        .section-title {
            text-align: center;
            font-size: 36px;
            color: var(--secondary-color);
            margin-bottom: 10px;
        }

        .section-subtitle {
            text-align: center;
            color: #666;
            margin-bottom: 40px;
        }

        .filter-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .filter-btn {
            background: #fff;
            border: 1px solid #ddd;
            padding: 8px 20px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--primary-color);
            color: var(--dark-color);
            border-color: var(--primary-color);
        }

        /* شبكة الأطباق */
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .menu-card {
            background: #fff;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
            display: flex;
            flex-direction: column;
        }

        .menu-card:hover {
            transform: translateY(-5px);
        }

        .menu-img {
            height: 200px;
            width: 100%;
            object-fit: cover;
        }

        .menu-content {
            padding: 20px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .menu-title-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .menu-title-price h3 {
            font-size: 20px;
            color: var(--dark-color);
        }

        .price {
            color: var(--secondary-color);
            font-weight: bold;
            font-size: 18px;
        }

        .menu-desc {
            color: #666;
            font-size: 14px;
            margin-bottom: 20px;
            flex-grow: 1;
        }

        .add-to-cart {
            background-color: var(--dark-color);
            color: #fff;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .add-to-cart:hover {
            background-color: var(--secondary-color);
        }

        .added-animation {
            background-color: #25d366 !important;
            transform: scale(0.95);
        }

        /* سلة الطلبات الجانبية */
        .cart-drawer {
            position: fixed;
            top: 0;
            left: -400px;
            width: 350px;
            height: 100%;
            background: #fff;
            box-shadow: 5px 0 15px rgba(0,0,0,0.2);
            z-index: 2000;
            transition: left 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .cart-drawer.open {
            left: 0;
        }

        .cart-header {
            background: var(--dark-color);
            color: #fff;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .close-cart {
            background: none;
            border: none;
            color: #fff;
            font-size: 20px;
            cursor: pointer;
        }

        .cart-items {
            padding: 20px;
            flex-grow: 1;
            overflow-y: auto;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }

        .cart-item-controls {
            display: flex;
            align-items: center;
            gap: 8px;
            margin-top: 5px;
        }

        .qty-btn {
            background: #ddd;
            border: none;
            width: 25px;
            height: 25px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
        }

        .qty-btn:hover {
            background: var(--primary-color);
        }

        /* إيموجي الإكس للحذف */
        .remove-item-btn {
            background: none;
            border: none;
            font-size: 20px;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .remove-item-btn:hover {
            transform: scale(1.3);
        }

        .cart-footer {
            padding: 20px;
            background: #f1f1f1;
            border-top: 1px solid #ddd;
        }

        .total-price {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 15px;
            display: flex;
            justify-content: space-between;
        }

        .checkout-btn {
            background-color: #25d366;
            color: #fff;
            border: none;
            width: 100%;
            padding: 12px;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            font-size: 16px;
        }

        .checkout-btn:hover {
            background-color: #1ebe5d;
        }

        /* الفوتر ولوحة المبرمج */
        footer {
            background-color: var(--dark-color);
            color: #fff;
            text-align: center;
            padding: 30px 20px;
            margin-top: 50px;
        }

        footer p {
            color: #aaa;
            font-size: 14px;
            margin-bottom: 10px;
        }

        .admin-link {
            background: var(--primary-color);
            color: var(--dark-color);
            border: none;
            padding: 8px 16px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
            font-weight: bold;
            margin-top: 10px;
            transition: background 0.3s;
        }

        .admin-link:hover {
            background: #e5c158;
        }

        /* نافذة لوحة تحكم المبرمج */
        .admin-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 3000;
            justify-content: center;
            align-items: center;
        }

        .admin-content {
            background: #fff;
            padding: 30px;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            color: var(--dark-color);
            text-align: right;
            max-height: 90vh;
            overflow-y: auto;
        }

        .admin-content h3 {
            margin-bottom: 20px;
            color: var(--secondary-color);
        }

        .admin-content input, .admin-content select, .admin-content textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .admin-btn {
            background-color: var(--secondary-color);
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
            margin-bottom: 10px;
        }

        .close-admin {
            background: #ccc;
            color: #333;
        }
    </style>
</head>
<body>

    <!-- شريط التنقل -->
    <header>
        <div class="navbar">
            <div class="logo">
                <i class="fa-solid fa-utensils"></i> مطعم الأصالة
            </div>
            <ul class="nav-links">
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#menu">قائمة الطعام</a></li>
            </ul>
            <button class="cart-btn" id="cartButton" onclick="toggleCart()">
                <i class="fa-solid fa-cart-shopping"></i> السلة (<span id="cart-count">0</span>)
            </button>
        </div>
    </header>

    <!-- الواجهة -->
    <section class="hero" id="home">
        <h1>أصالة المذاق الشرقي بين يديك</h1>
        <p>استمتع بألذ الأطباق الشرقية المحضرة بعناية وأجود المكونات الطازجة يومياً.</p>
        <a href="#menu" class="btn-main">تصفح القائمة الآن</a>
    </section>

    <!-- قائمة الطعام -->
    <section class="menu-section" id="menu">
        <h2 class="section-title">قائمة الطعام الفاخرة</h2>
        <p class="section-subtitle">اختر ما تشتهيه من أطباقنا الشهية</p>

        <!-- أزرار التصنيف -->
        <div class="filter-buttons">
            <button class="filter-btn active" onclick="filterMenu('all')">الكل</button>
            <button class="filter-btn" onclick="filterMenu('main')">أطباق رئيسية</button>
            <button class="filter-btn" onclick="filterMenu('appetizers')">مقبلات</button>
            <button class="filter-btn" onclick="filterMenu('desserts')">حلويات</button>
        </div>

        <!-- شبكة الأطباق -->
        <div class="menu-grid" id="menu-grid"></div>
    </section>

    <!-- السلة الجانبية -->
    <div class="cart-drawer" id="cartDrawer">
        <div class="cart-header">
            <h3>سلة الطلبات</h3>
            <button class="close-cart" onclick="toggleCart()">&times;</button>
        </div>
        <div class="cart-items" id="cartItems">
            <p style="text-align: center; color: #777; margin-top: 20px;">السلة فارغة حالياً</p>
        </div>
        <div class="cart-footer">
            <div class="total-price">
                <span>المجموع:</span>
                <span id="totalAmount">0 ج.م</span>
            </div>
            <button class="checkout-btn" onclick="sendToWhatsApp()">
                <i class="fa-brands fa-whatsapp"></i> اطلب عبر الواتساب
            </button>
        </div>
    </div>

    <!-- نافذة لوحة تحكم المبرمج -->
    <div class="admin-modal" id="adminModal">
        <div class="admin-content">
            <h3>لوحة تحكم المبرمج / الإدارة</h3>
            <label>إضافة طبق جديد:</label>
            <input type="text" id="newTitle" placeholder="اسم الطبق (مثلاً: حواوشي مصري)">
            <input type="number" id="newPrice" placeholder="السعر بالجنيه المصري (مثلاً: 120)">
            <input type="text" id="newImage" placeholder="رابط الصورة (URL)">
            <textarea id="newDesc" placeholder="وصف الطبق"></textarea>
            <select id="newCategory">
                <option value="main">أطباق رئيسية</option>
                <option value="appetizers">مقبلات</option>
                <option value="desserts">حلويات</option>
            </select>
            <button class="admin-btn" onclick="addNewDish()">إضافة الطبق للقائمة</button>
            <button class="admin-btn close-admin" onclick="closeAdminPanel()">إغلاق اللوحة</button>
        </div>
    </div>

    <!-- الفوتر -->
    <footer>
        <p>جميع الحقوق محفوظة &copy; مطعم الأصالة الشرقي 2026</p>
        <button class="admin-link" onclick="openAdminPanel()"><i class="fa-solid fa-lock"></i> دخول المبرمج</button>
    </footer>

    <!-- جافاسكريبت للتفاعل -->
    <script>
        let menuItems = [
            { id: 1, title: 'مشاوي مشكلة فاخرة', price: 350, image: 'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=500&q=80', desc: 'تشكيلة مميزة من كباب، شيش طاووق، وكلاجات مشوية على الفحم.', category: 'main' },
            { id: 2, title: 'مندي لحم بلدي', price: 400, image: 'https://images.unsplash.com/photo-1563379091339-03b21ab4a4f8?auto=format&fit=crop&w=500&q=80', desc: 'لحم ضأن طري مطهو على الطريقة التقليدية مع الأرز البسمتي البهار الأصيل.', category: 'main' },
            { id: 3, title: 'مقبلات شرقية مشكلة', price: 120, image: 'https://images.unsplash.com/photo-1577805947697-89e18249d767?auto=format&fit=crop&w=500&q=80', desc: 'حمص، متبل، ورق عنب، وفتوش طازج يُقدم مع الخبز الساخن.', category: 'appetizers' },
            { id: 4, title: 'كنافة نابلسية بالجبن', price: 90, image: 'https://images.unsplash.com/photo-1579372786545-d24232daf58c?auto=format&fit=crop&w=500&q=80', desc: 'كنافة ذهبية مقرمشة محشية بالجبن الفاخر ومسقية بالقطر الساخن والفستق.', category: 'desserts' }
        ];

        let cart = [];
        let failedAttempts = 0;
        let lockUntil = 0;

        function renderMenu(category = 'all') {
            let grid = document.getElementById('menu-grid');
            grid.innerHTML = '';
            let filtered = menuItems.filter(item => category === 'all' || item.category === category);

            filtered.forEach((item, idx) => {
                grid.innerHTML += `
                    <div class="menu-card" data-category="${item.category}">
                        <img src="${item.image}" alt="${item.title}" class="menu-img">
                        <div class="menu-content">
                            <div class="menu-title-price">
                                <h3>${item.title}</h3>
                                <span class="price">${item.price} ج.م</span>
                            </div>
                            <p class="menu-desc">${item.desc}</p>
                            <button class="add-to-cart" id="btn-${idx}" onclick="addToCart('${item.title}', ${item.price}, 'btn-${idx}')">أضف للسلة</button>
                        </div>
                    </div>
                `;
            });
        }

        function openAdminPanel() {
            let now = Date.now();
            if (now < lockUntil) {
                let remainingSecs = Math.ceil((lockUntil - now) / 1000);
                alert(`لقد تجاوزت عدد المحاولات الخاطئة. يرجى الانتظار ${remainingSecs} ثانية قبل المحاولة مرة أخرى.`);
                return;
            }

            let code = prompt("أدخل كود المبرمج السري:");
            if (code === "01005872291 asdfghj") {
                failedAttempts = 0; 
                document.getElementById('adminModal').style.display = 'flex';
            } else if (code !== null) {
                failedAttempts++;
                if (failedAttempts >= 5) {
                    lockUntil = Date.now() + 60000;
                    alert("لقد أدخلت الكود خطأ 5 مرات! تم قفل اللوحة لمدة دقيقة.");
                } else {
                    alert(`الكود غير صحيح! متبقي لك ${5 - failedAttempts} محاولات.`);
                }
            }
        }

        function closeAdminPanel() {
            document.getElementById('adminModal').style.display = 'none';
        }

        function addNewDish() {
            let title = document.getElementById('newTitle').value;
            let price = parseFloat(document.getElementById('newPrice').value);
            let image = document.getElementById('newImage').value;
            let desc = document.getElementById('newDesc').value;
            let category = document.getElementById('newCategory').value;

            if (!title || !price || !image) {
                alert('الرجاء إدخال اسم الطبق والسعر ورابط الصورة!');
                return;
            }

            menuItems.push({
                id: menuItems.length + 1,
                title,
                price,
                image,
                desc: desc || 'طبق شرقي مميز.',
                category
            });

            renderMenu();
            closeAdminPanel();
            alert('تم إضافة الطبق بنجاح!');
            
            document.getElementById('newTitle').value = '';
            document.getElementById('newPrice').value = '';
            document.getElementById('newImage').value = '';
            document.getElementById('newDesc').value = '';
        }

        function toggleCart() {
            document.getElementById('cartDrawer').classList.toggle('open');
        }

        // دالة لإشعال وتوهج السلة
        function triggerCartGlow() {
            let cartBtn = document.getElementById('cartButton');
            cartBtn.classList.add('cart-glow');
            setTimeout(() => {
                cartBtn.classList.remove('cart-glow');
            }, 600);
        }

        function addToCart(name, price, btnId) {
            let btn = document.getElementById(btnId);
            btn.classList.add('added-animation');
            btn.innerText = 'تمت الإضافة ✓';
            setTimeout(() => {
                btn.classList.remove('added-animation');
                btn.innerText = 'أضف للسلة';
            }, 600);

            triggerCartGlow(); // تشغيل إضاءة السلة

            let existingItem = cart.find(item => item.name === name);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ name, price, quantity: 1 });
            }
            updateCartUI();
        }

        // زيادة الكمية (+1)
        function increaseQty(index) {
            cart[index].quantity += 1;
            triggerCartGlow();
            updateCartUI();
        }

        // نقصان الكمية (-1) أو الحذف لو وصلت الصفر
        function decreaseQty(index) {
            if (cart[index].quantity > 1) {
                cart[index].quantity -= 1;
            } else {
                cart.splice(index, 1);
            }
            triggerCartGlow();
            updateCartUI();
        }

        function removeItem(index) {
            cart.splice(index, 1);
            triggerCartGlow();
            updateCartUI();
        }

        function updateCartUI() {
            let cartItemsContainer = document.getElementById('cartItems');
            let cartCount = document.getElementById('cartCount');
            let totalAmountElement = document.getElementById('totalAmount');

            cartItemsContainer.innerHTML = '';
            let total = 0;
            let count = 0;

            if (cart.length === 0) {
                cartItemsContainer.innerHTML = '<p style="text-align: center; color: #777; margin-top: 20px;">السلة فارغة حالياً</p>';
            } else {
                cart.forEach((item, index) => {
                    total += item.price * item.quantity;
                    count += item.quantity;
                    cartItemsContainer.innerHTML += `
                        <div class="cart-item">
                            <div>
                                <h4>${item.name}</h4>
                                <small>${item.price} ج.م × ${item.quantity}</small>
                                <div class="cart-item-controls">
                                    <button class="qty-btn" onclick="decreaseQty(${index})">-</button>
                                    <span>${item.quantity}</span>
                                    <button class="qty-btn" onclick="increaseQty(${index})">+</button>
                                </div>
                            </div>
                            <button class="remove-item-btn" onclick="removeItem(${index})" title="حذف الطبق">❌</button>
                        </div>
                    `;
                });
            }

            cartCount.innerText = count;
            totalAmountElement.innerText = total + ' ج.م';
        }

        function filterMenu(category) {
            let buttons = document.querySelectorAll('.filter-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            renderMenu(category);
        }

        function sendToWhatsApp() {
            if (cart.length === 0) {
                alert('سلة الطلبات فارغة!');
                return;
            }

            let message = 'مرحباً، أريـد طلب الأطباق التالية:%0A';
            let total = 0;
            cart.forEach(item => {
                message += `- ${item.name} (${item.quantity}) - ${item.price * item.quantity} ج.م%0A`;
                total += item.price * item.quantity;
            });
            message += `%0A*المجموع الإجمالي: ${total} ج.م*`;

            let phone = '01005872291';
            let url = `https://wa.me/${phone}?text=${message}`;
            window.open(url, '_blank');
        }

        renderMenu();
    </script>
</body>
</html>

