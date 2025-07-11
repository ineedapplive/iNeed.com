<!DOCTYPE html>
<html lang="en" data-theme="light" data-color-theme="blue">
<head>
  
<meta name="monetag" content="33a4d3a4422acdcab5ce98065037bdfd">  
  
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I Need - All In One</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        :root {
            --primary-color: #1976D2;
            --primary-gradient: linear-gradient(to bottom, var(--primary-color), color-mix(in srgb, var(--primary-color) 85%, black));
            --background-color: #f4f5f7;
            --card-background: #ffffff;
            --card-border-color: #e0e0e0;
            --text-color-dark: #212121;
            --text-color-light: #757575;
            --header-text-color: #ffffff;
            --sidebar-background: #ffffff;
            --shadow-color: rgba(0, 0, 0, 0.05);
            --highlight-color: color-mix(in srgb, var(--primary-color) 10%, transparent);
        }
        html[data-theme='dark'] {
            --background-color: #121212;
            --card-background: #1e1e1e;
            --card-border-color: #333333;
            --text-color-dark: #e0e0e0;
            --text-color-light: #b0b0b0;
            --header-text-color: #ffffff;
            --sidebar-background: #212121;
            --shadow-color: rgba(0, 0, 0, 0.2);
            --highlight-color: color-mix(in srgb, var(--primary-color) 20%, transparent);
        }
        html[data-color-theme='blue'] { --primary-color: #1976D2; }
        html[data-color-theme='green'] { --primary-color: #388E3C; }
        html[data-color-theme='purple'] { --primary-color: #7B1FA2; }
        html[data-color-theme='orange'] { --primary-color: #F57C00; }
        html[data-color-theme='red'] { --primary-color: #D32F2F; }

        * { box-sizing: border-box; margin: 0; padding: 0; transition: background-color 0.3s, color 0.3s, border-color 0.3s, box-shadow 0.3s; }
        body { font-family: 'Roboto', sans-serif; background-color: var(--background-color); color: var(--text-color-dark); -webkit-tap-highlight-color: transparent; }
        .container { padding: 1rem; }

        header { background-image: var(--primary-gradient); color: var(--header-text-color); padding: 0.8rem 1rem; display: flex; align-items: center; justify-content: space-between; position: sticky; top: 0; z-index: 1000; box-shadow: 0 4px 12px var(--shadow-color); }
        .header-left, .header-right { display: flex; align-items: center; gap: 1rem; }
        .menu-btn, .search-btn { background: none; border: none; color: var(--header-text-color); font-size: 1.5rem; cursor: pointer; transition: transform 0.2s; }
        .menu-btn:active, .search-btn:active { transform: scale(1.15); }
        header h1 { font-size: 1.4rem; font-weight: 700; }
        
        .search-container { display: none; padding: 0.8rem 1rem; background-color: var(--card-background); box-shadow: 0 2px 4px rgba(0,0,0,0.1) inset; }
        .search-container.active { display: block; }
        #appSearch { width: 100%; padding: 0.7rem 1rem; font-size: 1rem; border: 1px solid var(--card-border-color); border-radius: 50px; outline: none; background-color: var(--background-color); color: var(--text-color-dark); }

        .main-tabs { background-image: var(--primary-gradient); display: flex; overflow-x: auto; -ms-overflow-style: none; scrollbar-width: none; }
        .main-tabs::-webkit-scrollbar { display: none; }
        .main-tabs a { flex-shrink: 0; padding: 1rem; text-align: center; color: rgba(255, 255, 255, 0.8); text-decoration: none; font-weight: 500; font-size: 0.9rem; text-transform: uppercase; border-bottom: 3px solid transparent; white-space: nowrap; min-width: 100px; transition: color 0.2s, border-bottom-color 0.2s; }
        .main-tabs a.active { color: var(--header-text-color); border-bottom-color: var(--header-text-color); }
        
        .app-section { display: none; }
        .app-section.active { display: block; animation: fadeIn 0.4s; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        
        .grid-heading { font-size: 1.2rem; font-weight: 700; margin: 2rem 0 1rem 0; padding-bottom: 0.5rem; border-bottom: 2px solid var(--primary-color); color: var(--primary-color); }
        .grid-heading i { margin-right: 0.7rem; }
        #section-home .grid-heading:first-child { margin-top: 1rem; }

        .app-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(75px, 1fr)); gap: 1rem; padding-top: 1rem; perspective: 1000px; }
        .app-card { background-color: var(--card-background); border-radius: 12px; border: 1px solid var(--card-border-color); box-shadow: 0 4px 10px var(--shadow-color); padding: 0.75rem; text-align: center; display: flex; flex-direction: column; align-items: center; justify-content: center; text-decoration: none; color: var(--text-color-dark); transition: transform 0.3s ease, box-shadow 0.3s ease; aspect-ratio: 1 / 1; position: relative; cursor: pointer; }
        .app-card:hover { transform: translateY(-6px) rotateY(8deg) scale(1.05); box-shadow: 0 10px 20px rgba(0,0,0,0.15); }
        .app-card .app-logo { width: 40px; height: 40px; object-fit: contain; margin-bottom: 0.5rem; border-radius: 10px; background-color: var(--background-color); }
        .app-card .app-logo-placeholder { width: 40px; height: 40px; margin-bottom: 0.5rem; border-radius: 10px; background-color: #eee; color: #aaa; display: flex; align-items: center; justify-content: center; font-size: 1.5rem; font-weight: bold; }
        .app-card .app-name { font-size: 0.75rem; font-weight: 500; line-height: 1.3; }
        
        .loading-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: var(--background-color); z-index: 4000; display: none; flex-direction: column; align-items: center; justify-content: center; animation: fadeIn 0.3s; }
        .loading-overlay img { width: 80px; height: 80px; border-radius: 20px; margin-bottom: 1.5rem; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
        .loading-overlay p { font-size: 1.2rem; font-weight: 500; color: var(--text-color-dark); }
        .loading-overlay .app-logo-placeholder { width: 80px; height: 80px; border-radius: 20px; margin-bottom: 1.5rem; font-size: 3rem; }

        .sidebar { position: fixed; top: 0; left: 0; width: 280px; height: 100vh; background-color: var(--sidebar-background); z-index: 2000; transform: translateX(-280px); transition: transform 0.3s ease-in-out; box-shadow: 4px 0 15px rgba(0,0,0,0.1); display: flex; flex-direction: column; }
        .sidebar.open { transform: translateX(0); }
        .sidebar-header { padding: 1rem 1.5rem; border-bottom: 1px solid var(--card-border-color); }
        .sidebar-header h2 { font-size: 1.2rem; font-weight: 700; color: var(--primary-color); }
        .sidebar-nav { list-style: none; padding: 0; margin: 0; flex-grow: 1; overflow-y: auto; }
        .sidebar-nav a { display: flex; align-items: center; gap: 1.5rem; padding: 1rem 1.5rem; text-decoration: none; color: var(--text-color-dark); font-weight: 500; border-bottom: 1px solid var(--background-color); }
        .sidebar-nav a:hover { background-color: var(--highlight-color); }
        .sidebar-nav i { font-size: 1.2rem; width: 24px; text-align: center; color: var(--text-color-light); }
        .sidebar-settings { padding: 1rem 1.5rem; border-top: 1px solid var(--card-border-color); }
        .setting-item { display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem; font-weight: 500; }
        .setting-item:last-child { margin-bottom: 0; }
        .color-swatches { display: flex; gap: 0.5rem; }
        .color-swatch { width: 24px; height: 24px; border-radius: 50%; cursor: pointer; border: 2px solid var(--card-border-color); }
        .color-swatch.active { box-shadow: 0 0 0 2px var(--primary-color); }
        .switch { position: relative; display: inline-block; width: 50px; height: 28px; }
        .switch input { opacity: 0; width: 0; height: 0; }
        .slider { position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0; background-color: #ccc; transition: .4s; border-radius: 34px; }
        .slider:before { position: absolute; content: ""; height: 20px; width: 20px; left: 4px; bottom: 4px; background-color: white; transition: .4s; border-radius: 50%; }
        input:checked + .slider { background-color: var(--primary-color); }
        input:checked + .slider:before { transform: translateX(22px); }

        .overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.5); z-index: 1999; opacity: 0; visibility: hidden; transition: opacity 0.3s ease-in-out; }
        .overlay.active { opacity: 1; visibility: visible; }
        
        .modal { position: fixed; z-index: 3000; left: 0; top: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.6); display: none; align-items: center; justify-content: center; padding: 1rem; }
        .modal.show { display: flex; }
        .modal-content { background-color: var(--card-background); color: var(--text-color-dark); padding: 20px 25px; border-radius: 12px; border: 1px solid var(--card-border-color); position: relative; width: 100%; max-width: 500px; max-height: 80vh; overflow-y: auto; box-shadow: 0 5px 15px rgba(0,0,0,0.2); animation: slideIn 0.3s ease-out; }
        @keyframes slideIn { from { transform: translateY(-30px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
        .modal-close-btn { position: absolute; top: 10px; right: 15px; color: var(--text-color-light); font-size: 1.8rem; font-weight: bold; cursor: pointer; }
        .modal-close-btn:hover { color: var(--primary-color); }
        .modal-header h2 { margin-top: 0; color: var(--primary-color); margin-bottom: 15px; border-bottom: 1px solid var(--card-border-color); padding-bottom: 10px; }
        .modal-body p { font-size: 0.95rem; line-height: 1.6; color: var(--text-color-light); }
        .modal-body .disclaimer { margin-top: 25px; padding-top: 15px; border-top: 1px solid var(--card-border-color); font-size: 0.85rem; font-style: italic; }
    </style>
</head>
<body>
  
  
  
  
  
  
  
    <div class="loading-overlay" id="loadingOverlay">
        <img id="loadingLogo" src="" alt="App Logo" style="display: none;">
        <div id="loadingLogoPlaceholder" class="app-logo-placeholder" style="display: none;"></div>
        <p id="loadingAppName"></p>
    </div>
  
    <div class="sidebar" id="sidebar">
        <div class="sidebar-header"> <h2>Categories</h2> </div>
        <ul class="sidebar-nav" id="sidebarNav"></ul>
        <div class="sidebar-settings">
            <div class="setting-item"> <span>Dark Mode</span> <label class="switch"> <input type="checkbox" id="darkModeToggle"> <span class="slider"></span> </label> </div>
            <div class="setting-item"> <span>Theme Color</span> <div class="color-swatches" id="colorSwatchesContainer"></div> </div>
        </div>
    </div>
    <div class="overlay" id="overlay"></div>

    <header>
        <div class="header-left"> <button class="menu-btn" id="menuBtn"><i class="fas fa-bars"></i></button> <h1>I Need</h1> </div>
        <div class="header-right"> <button class="search-btn" id="searchBtn"><i class="fas fa-search"></i></button> </div>
    </header>

    <div class="search-container" id="searchContainer">
        <input type="text" id="appSearch" placeholder="Search for any app..." onkeyup="filterApps()">
    </div>
    
    <nav class="main-tabs" id="mainTabs"></nav>
    
    <main class="container" id="appSectionsContainer"></main>
    
    <div id="aboutModal" class="modal">
        <div class="modal-content">
            <span class="modal-close-btn">×</span>
            <div class="modal-header"> <h2>About 'I Need'</h2> </div>
            <div class="modal-body">
                <p>Welcome to 'I Need'! We've brought together all your essential web apps into one platform, saving your phone's precious storage and giving you one-tap access to everything you need.</p>
                <p class="disclaimer"> <strong>🛑 Important Note:</strong><br> All website content and logos are owned by their respective websites. We do not hold any copyright over the content or logo of other websites. These third-party sites have separate and independent privacy policies and terms. Please read their policies and terms carefully. </p>
            </div>
        </div>
    </div>

    <script>
        const categoryInfo = {
            "home": { name: "Home", icon: "fa-solid fa-house" },
            "favourite": { name: "Favourite", icon: "fa-solid fa-star" },
            "social": { name: "Social Media", icon: "fa-solid fa-users" },
            "video_entertainment": { name: "OTT & Movies", icon: "fa-solid fa-tv" },
            "islamic": { name: "Islamic", icon: "fa-solid fa-mosque" },
            "news": { name: "News", icon: "fa-solid fa-newspaper" },
            "education": { name: "Education", icon: "fa-solid fa-user-graduate" },
            "jobs_career": { name: "Jobs & Career", icon: "fa-solid fa-user-tie" },
            "shopping": { name: "Shopping", icon: "fa-solid fa-bag-shopping" },
            "finance_wallet": { name: "Finance & Wallet", icon: "fa-solid fa-wallet" },
            "banking": { name: "Banking", icon: "fa-solid fa-landmark" },
            "ai_tools": { name: "AI Tools", icon: "fa-solid fa-robot" },
            "games": { name: "Games", icon: "fa-solid fa-gamepad" },
            "government_info": { name: "Government / Info", icon: "fa-solid fa-building-columns" },
            "religion_hinduism": { name: "Religion - Hinduism", icon: "fa-solid fa-om" },
            "religion_christianity": { name: "Religion - Christianity", icon: "fa-solid fa-cross" },
            "religion_others": { name: "Religion - Others", icon: "fa-solid fa-place-of-worship" },
            "tools_utilities": { name: "Tools / Utilities", icon: "fa-solid fa-screwdriver-wrench" },
            "communication": { name: "Communication", icon: "fa-solid fa-envelope" },
            "developer_tech": { name: "Developer & Tech", icon: "fa-solid fa-code" },
            "cloud_storage": { name: "Cloud & Storage", icon: "fa-solid fa-cloud" },
            "design_edit": { name: "Design & Edit", icon: "fa-solid fa-palette" },
            "maps_travel": { name: "Travel & Transport", icon: "fa-solid fa-map-location-dot" },
            "notes_office": { name: "Notes & Office", icon: "fa-solid fa-file-pen" },
            "music": { name: "Music", icon: "fa-solid fa-music" },
            "blogging_writing": { name: "Blogging / Writing", icon: "fa-solid fa-feather-pointed" },
            "kids_learning": { name: "Kids & Learning", icon: "fa-solid fa-shapes" },
            "health_fitness": { name: "Health & Fitness", icon: "fa-solid fa-heart-pulse" },
            "food_delivery": { name: "Food Delivery", icon: "fa-solid fa-utensils" },
            "offers_coupons": { name: "Offers & Coupons", icon: "fa-solid fa-tags" },
            "pro_design_ai": { name: "Pro Design & AI", icon: "fa-solid fa-cubes" },
        };

        const appsData = [
            // Social Media
            { name: "Facebook", url: "https://m.facebook.com/", category: "social", isFavourite: true },
            { name: "Instagram", url: "https://www.instagram.com/", category: "social" },
            { name: "X (Twitter)", url: "https://twitter.com/", category: "social" },
            { name: "Threads", url: "https://www.threads.net/", category: "social" },
            { name: "Pinterest", url: "https://www.pinterest.com/", category: "social" },
            { name: "Reddit", url: "https://www.reddit.com/", category: "social" },
            { name: "Quora", url: "https://www.quora.com/", category: "social" },
            { name: "LinkedIn", url: "https://www.linkedin.com/", category: "social" },
            { name: "Tumblr", url: "https://www.tumblr.com/", category: "social" },
            { name: "MeWe", url: "https://mewe.com/", category: "social" },
            { name: "Mastodon", url: "https://mastodon.social/", category: "social" },
            { name: "BeReal", url: "https://bere.al/", category: "social" },
            { name: "Telegram WebK", url: "https://web.telegram.org/k/", category: "communication" },
            { name: "Snapchat Web", url: "https://web.snapchat.com/", category: "communication" },
            
            // Shopping
            { name: "Amazon", url: "https://www.amazon.in/", category: "shopping", isFavourite: true },
            { name: "Flipkart", url: "https://www.flipkart.com/", category: "shopping" },
            { name: "Meesho", url: "https://www.meesho.com/", category: "shopping" },
            { name: "Myntra", url: "https://www.myntra.com/", category: "shopping" },
            { name: "Ajio", url: "https://www.ajio.com/", category: "shopping" },
            { name: "Snapdeal", url: "https://www.snapdeal.com/", category: "shopping" },
            { name: "Nykaa", url: "https://www.nykaa.com/", category: "shopping" },
            { name: "JioMart", url: "https://www.jiomart.com/", category: "shopping" },
            { name: "BigBasket", url: "https://www.bigbasket.com/", category: "shopping" },
            { name: "Tata CLiQ", url: "https://www.tatacliq.com/", category: "shopping" },
            { name: "Purplle", url: "https://www.purplle.com/", category: "shopping" },
            { name: "Lenskart", url: "https://www.lenskart.com/", category: "shopping" },
            { name: "FirstCry", url: "https://www.firstcry.com/", category: "shopping" },
            { name: "Shopsy", url: "https://www.shopsy.in/", category: "shopping" },
            { name: "ShopClues", url: "https://www.shopclues.com/", category: "shopping" },
            { name: "Daraz", url: "https://www.daraz.com.bd/", category: "shopping" },
            { name: "AliExpress", url: "https://www.aliexpress.com/", category: "shopping" },

            // OTT & Movies
            { name: "YouTube", url: "https://m.youtube.com/", category: "video_entertainment", isFavourite: true },
            { name: "Netflix", url: "https://www.netflix.com/", category: "video_entertainment" },
            { name: "Prime Video", url: "https://www.primevideo.com/", category: "video_entertainment" },
            { name: "Disney+ Hotstar", url: "https://www.hotstar.com/", category: "video_entertainment" },
            { name: "SonyLIV", url: "https://www.sonyliv.com/", category: "video_entertainment" },
            { name: "Zee5", url: "https://www.zee5.com/", category: "video_entertainment" },
            { name: "JioCinema", url: "https://www.jiocinema.com/", category: "video_entertainment" },
            { name: "MX Player", url: "https://www.mxplayer.in/", category: "video_entertainment" },
            { name: "Hungama Play", url: "https://www.hungama.com/movies/", category: "video_entertainment" },
            { name: "Hoichoi", url: "https://www.hoichoi.tv/", category: "video_entertainment" },
            { name: "Aha", url: "https://www.aha.video/", category: "video_entertainment" },
            { name: "IMDb", url: "https://m.imdb.com/", category: "video_entertainment" },

            // Games
            { name: "Miniclip", url: "https://www.miniclip.com/", category: "games", isFavourite: true },
            { name: "Poki", url: "https://poki.com/", category: "games" },
            { name: "Y8.com", url: "https://www.y8.com/", category: "games" },
            { name: "CrazyGames", url: "https://www.crazygames.com/", category: "games" },
            { name: "Lagged", url: "https://www.lagged.com/", category: "games" },
            { name: "GamePix", url: "https://www.gamepix.com/", category: "games" },
            { name: "PlayCanvas", url: "https://playcanvas.com/", category: "games" },
            { name: "Kizi", url: "https://kizi.com/", category: "games" },
            { name: "Agame", url: "https://www.agame.com/", category: "games" },
            { name: "Friv", url: "https://www.friv.com/", category: "games" },

            // Food Delivery
            { name: "Zomato", url: "https://www.zomato.com/", category: "food_delivery", isFavourite: true },
            { name: "Swiggy", url: "https://www.swiggy.com/", category: "food_delivery" },
            { name: "Dominos India", url: "https://www.dominos.co.in/", category: "food_delivery" },
            { name: "KFC India", url: "https://online.kfc.co.in/", category: "food_delivery" },
            { name: "Pizza Hut India", url: "https://www.pizzahut.co.in/", category: "food_delivery" },
            { name: "McDonald’s India", url: "https://www.mcdelivery.co.in/", category: "food_delivery" },
            { name: "Uber Eats", url: "https://www.ubereats.com/", category: "food_delivery" },
            { name: "FoodPanda", url: "https://www.foodpanda.com/", category: "food_delivery" },

            // News
            { name: "BBC News", url: "https://www.bbc.com/news", category: "news", isFavourite: true },
            { name: "CNN", url: "https://edition.cnn.com/", category: "news" },
            { name: "NDTV", url: "https://www.ndtv.com/", category: "news" },
            { name: "ABP Live", url: "https://www.abplive.com/", category: "news" },
            { name: "AajTak", url: "https://www.aajtak.in/", category: "news" },
            { name: "Zee News", url: "https://zeenews.india.com/", category: "news" },
            { name: "Anandabazar", url: "https://www.anandabazar.com/", category: "news" },
            { name: "Hindustan Times", url: "https://www.hindustantimes.com/", category: "news" },
            { name: "Reuters", url: "https://www.reuters.com/", category: "news" },
            { name: "The Guardian", url: "https://www.theguardian.com/international", category: "news" },
            { name: "India Today", url: "https://www.indiatoday.in/", category: "news" },
            { name: "Prothom Alo", url: "https://www.prothomalo.com/", category: "news" },

            // Travel & Transport
            { name: "Google Maps", url: "https://maps.google.com/", category: "maps_travel", isFavourite: true, isNew: true },
            { name: "MakeMyTrip", url: "https://www.makemytrip.com/", category: "maps_travel" },
            { name: "Goibibo", url: "https://www.goibibo.com/", category: "maps_travel" },
            { name: "RedBus", url: "https://www.redbus.in/", category: "maps_travel" },
            { name: "Booking.com", url: "https://www.booking.com/", category: "maps_travel" },
            { name: "OYO", url: "https://www.oyorooms.com/", category: "maps_travel" },
            { name: "Agoda", url: "https://www.agoda.com/", category: "maps_travel" },
            { name: "Airbnb", url: "https://www.airbnb.com/", category: "maps_travel" },
            { name: "Cleartrip", url: "https://www.cleartrip.com/", category: "maps_travel" },
            { name: "ixigo", url: "https://www.ixigo.com/", category: "maps_travel" },
            { name: "IRCTC Next Gen", url: "https://www.irctc.co.in/", category: "maps_travel" },
            { name: "Uber Web", url: "https://m.uber.com/", category: "maps_travel" },
            { name: "Ola Web", url: "https://www.olacabs.com/", category: "maps_travel" },

            // Health
            { name: "1mg", url: "https://www.1mg.com/", category: "health_fitness", isFavourite: true },
            { name: "Practo", url: "https://www.practo.com/", category: "health_fitness" },
            { name: "Apollo 24|7", url: "https://www.apollo247.com/", category: "health_fitness" },
            { name: "Tata Health", url: "https://www.tatahealth.com/", category: "health_fitness" },
            { name: "MedPlus Mart", url: "https://www.medplusmart.com/", category: "health_fitness" },
            { name: "PharmEasy", url: "https://pharmeasy.in/", category: "health_fitness" },
            { name: "HealthifyMe", url: "https://www.healthifyme.com/", category: "health_fitness" },
            { name: "MyFitnessPal", url: "https://www.myfitnesspal.com/", category: "health_fitness" },
            { name: "WebMD", url: "https://www.webmd.com/", category: "health_fitness" },
            
            // Islamic
            { name: "Quran.com", url: "https://quran.com/", category: "islamic", isFavourite: true },
            { name: "Muslim Pro Web", url: "https://www.muslimpro.com/en/web", category: "islamic" },
            { name: "IslamicFinder", url: "https://www.islamicfinder.org/", category: "islamic" },
            { name: "Alim.org", url: "https://www.alim.org/", category: "islamic" },
            { name: "Kalamullah", url: "https://www.kalamullah.com/", category: "islamic" },
            { name: "HadithCollection", url: "https://hadithcollection.com/", category: "islamic" },
            { name: "IslamQA", url: "https://islamqa.info/en", category: "islamic" },
            { name: "Salat Time", url: "https://www.salattime.net/", category: "islamic" },
            { name: "Ummah.com", url: "https://www.ummah.com/sisters/", category: "islamic" },
            { name: "Dua Center", url: "https://www.duacenter.com/", category: "islamic" },
            { name: "Archive.org", url: "https://archive.org/", category: "islamic" },
            { name: "Sunnah.com", url: "https://sunnah.com/", category: "islamic" },

            // Music
            { name: "Spotify", url: "https://open.spotify.com/", category: "music", isFavourite: true },
            { name: "JioSaavn", url: "https://www.jiosaavn.com/", category: "music" },
            { name: "Gaana", url: "https://gaana.com/", category: "music" },
            { name: "Wynk Music", url: "https://wynk.in/music", category: "music" },
            { name: "Resso", url: "https://www.resso.com/", category: "music" },
            { name: "YouTube Music", url: "https://music.youtube.com/", category: "music" },
            { name: "SoundCloud", url: "https://soundcloud.com/", category: "music" },
            
            // AI Tools
            { name: "ChatGPT", url: "https://chat.openai.com/", category: "ai_tools", isFavourite: true },
            { name: "Gemini", url: "https://gemini.google.com/", category: "ai_tools" },
            { name: "Perplexity AI", url: "https://www.perplexity.ai/", category: "ai_tools" },
            { name: "Poe", url: "https://poe.com/", category: "ai_tools" },
            { name: "YouChat", url: "https://you.com/chat", category: "ai_tools" },
            { name: "DALL·E", url: "https://labs.openai.com/", category: "ai_tools" },
            { name: "AI Dungeon", url: "https://play.aidungeon.io/", category: "ai_tools" },
            { name: "Magic Eraser", url: "https://magicstudio.com/magiceraser/", category: "ai_tools" },
            { name: "Cleanup.pictures", url: "https://cleanup.pictures/", category: "ai_tools" },
            
            // Pro Design & AI
            { name: "Spline", url: "https://spline.design/", category: "pro_design_ai", isFavourite: true, isNew: true },
            { name: "RunwayML", url: "https://runwayml.com/", category: "pro_design_ai" },
            { name: "Luma AI", url: "https://lumalabs.ai/", category: "pro_design_ai" },
            { name: "Krea AI", url: "https://www.krea.ai/", category: "pro_design_ai" },
            { name: "Framer AI", url: "https://www.framer.com/ai/", category: "pro_design_ai" },
            { name: "Vectary", url: "https://www.vectary.com/", category: "pro_design_ai" },
            { name: "Playground AI", url: "https://playground.com/", category: "pro_design_ai" },

            // Editing Tools
            { name: "Canva", url: "https://www.canva.com/", category: "design_edit", isFavourite: true },
            { name: "Pixlr", url: "https://pixlr.com/m/", category: "design_edit" },
            { name: "Photopea", url: "https://www.photopea.com/", category: "design_edit" },
            { name: "Remove.bg", url: "https://www.remove.bg/", category: "design_edit" },
            { name: "Fotor", url: "https://www.fotor.com/", category: "design_edit" },
            { name: "BeFunky", url: "https://www.befunky.com/", category: "design_edit" },
            { name: "Kapwing", url: "https://www.kapwing.com/", category: "design_edit" },
            { name: "Img2Go", url: "https://www.img2go.com/", category: "design_edit" },
            
            // Coding/HTML Tools
            { name: "GitHub", url: "https://github.com/", category: "developer_tech", isFavourite: true },
            { name: "CodePen", url: "https://codepen.io/", category: "developer_tech" },
            { name: "JSFiddle", url: "https://jsfiddle.net/", category: "developer_tech" },
            { name: "W3Schools Tryit", url: "https://www.w3schools.com/tryit/", category: "developer_tech" },
            { name: "StackBlitz", url: "https://stackblitz.com/", category: "developer_tech" },
            { name: "HTMLColorCodes", url: "https://htmlcolorcodes.com/", category: "developer_tech" },
            { name: "CSSGradient.io", url: "https://cssgradient.io/", category: "developer_tech" },
            { name: "Replit", url: "https://replit.com/", category: "developer_tech" },

            // Tools / Utilities (including Converters & PDF)
            { name: "Grammarly", url: "https://www.grammarly.com/", category: "tools_utilities", isFavourite: true },
            { name: "Smallpdf", url: "https://smallpdf.com/", category: "tools_utilities" },
            { name: "iLovePDF", url: "https://www.ilovepdf.com/", category: "tools_utilities" },
            { name: "PDFCandy", url: "https://pdfcandy.com/", category: "tools_utilities" },
            { name: "PDF2Go", url: "https://www.pdf2go.com/", category: "tools_utilities" },
            { name: "Convertio", url: "https://convertio.co/", category: "tools_utilities" },
            { name: "UnitConverters.net", url: "https://www.unitconverters.net/", category: "tools_utilities" },
            { name: "Online-Convert", url: "https://www.online-convert.com/", category: "tools_utilities" },
            { name: "TinyPNG", url: "https://tinypng.com/", category: "tools_utilities" },
            { name: "10MinuteMail", url: "https://10minutemail.com/", category: "tools_utilities" },
            { name: "IFTTT", url: "https://ifttt.com/", category: "tools_utilities" },
            { name: "Bitly", url: "https://bitly.com/", category: "tools_utilities" },
            { name: "Calendly", url: "https://calendly.com/", category: "tools_utilities" },
            
            // Cloud & Storage
            { name: "Google Drive", url: "https://drive.google.com/", category: "cloud_storage", isFavourite: true },
            { name: "Dropbox", url: "https://www.dropbox.com/", category: "cloud_storage" },
            { name: "OneDrive", url: "https://onedrive.live.com/", category: "cloud_storage" },
            { name: "Bitwarden", url: "https://vault.bitwarden.com/", category: "cloud_storage" },
            
            // Notes & Office
            { name: "Google Keep", url: "https://keep.google.com/", category: "notes_office", isFavourite: true },
            { name: "Notion", url: "https://www.notion.so/", category: "notes_office" },
            { name: "Trello", url: "https://trello.com/", category: "notes_office" },
            { name: "Todoist", url: "https://todoist.com/", category: "notes_office" },
            { name: "Google Forms", url: "https://forms.google.com/", category: "notes_office" },
            { name: "Google Docs", url: "https://docs.google.com/", category: "notes_office" },
            { name: "Google Sheets", url: "https://sheets.google.com/", category: "notes_office" },
            { name: "Google Calendar", url: "https://calendar.google.com/", category: "notes_office" },

            // Education
            { name: "Khan Academy", url: "https://www.khanacademy.org/", category: "education", isFavourite: true },
            { name: "Coursera", url: "https://www.coursera.org/", category: "education" },
            { name: "edX", url: "https://www.edx.org/", category: "education" },
            { name: "BYJU'S", url: "https://byjus.com/", category: "education" },
            { name: "Unacademy", url: "https://unacademy.com/", category: "education" },
            { name: "Vedantu", url: "https://www.vedantu.com/", category: "education" },
            { name: "Duolingo", url: "https://www.duolingo.com/", category: "education" },
            { name: "Quizizz", url: "https://quizizz.com/", category: "education" },
            { name: "Brainly", url: "https://brainly.in/", category: "education" },
            { name: "Study.com", url: "https://study.com/", category: "education" },

            // Religious Sites (Others)
            { name: "BibleGateway", url: "https://www.biblegateway.com/", category: "religion_christianity", isFavourite: true },
            { name: "JW.org", url: "https://www.jw.org/", category: "religion_christianity" },
            { name: "LDS.org", url: "https://www.churchofjesuschrist.org/", category: "religion_christianity" },
            { name: "Blue Letter Bible", url: "https://www.blueletterbible.org/", category: "religion_christianity" },
            { name: "Vedabase.io", url: "https://vedabase.io/", category: "religion_hinduism" },
            { name: "ISKCON.org", url: "https://www.iskcon.org/", category: "religion_hinduism" },
            { name: "SikhNet", url: "https://www.sikhnet.com/", category: "religion_others" },

            // Offers & Coupons
            { name: "CouponDunia", url: "https://www.coupondunia.in/", category: "offers_coupons", isFavourite: true },
            { name: "CashKaro", url: "https://cashkaro.com/", category: "offers_coupons" },
            { name: "FreeKaaMaal", url: "https://freekaamaal.com/", category: "offers_coupons" },
            { name: "GrabOn", url: "https://www.grabon.in/", category: "offers_coupons" },
            { name: "Coupert", url: "https://www.coupert.com/", category: "offers_coupons" },
            { name: "RetailMeNot", url: "https://www.retailmenot.com/", category: "offers_coupons" },
            { name: "Slickdeals", url: "https://slickdeals.net/", category: "offers_coupons" },
            { name: "Offers.com", url: "https://www.offers.com/", category: "offers_coupons" },

            // Finance & Wallet
            { name: "Paytm", url: "https://paytm.com/", category: "finance_wallet", isFavourite: true },
            { name: "Google Pay", url: "https://pay.google.com/", category: "finance_wallet" },
            { name: "PhonePe", url: "https://www.phonepe.com/", category: "finance_wallet" },
            { name: "bKash", url: "https://www.bkash.com/", category: "finance_wallet" },
            { name: "Nagad", url: "https://www.nagad.com.bd/", category: "finance_wallet" },
            { name: "PayPal", url: "https://www.paypal.com/", category: "finance_wallet" },
        ];
        
        let mainTabsOrder = ['favourite', 'home', 'social', 'video_entertainment', 'shopping', 'food_delivery', 'pro_design_ai', 'ai_tools', 'news', 'games', 'maps_travel', 'tools_utilities'];
        
        const colorThemes = [ { name: 'red', value: '#D32F2F' }, { name: 'blue', value: '#1976D2' }, { name: "green", value: '#388E3C' }, { name: 'purple', value: '#7B1FA2' }, { name: 'orange', value: '#F57C00' } ];

        document.addEventListener('DOMContentLoaded', () => {
            const fullAppsData = [...new Map(appsData.map(item => [item.name, item])).values()];
            applySavedThemes();
            setupUI(fullAppsData);
            addEventListeners(fullAppsData);
            setupThemeControls();
            showTabContent('home');
        });

        function applySavedThemes() {
            const savedTheme = localStorage.getItem('theme') || 'light';
            const savedColor = localStorage.getItem('colorTheme') || 'blue';
            document.documentElement.setAttribute('data-theme', savedTheme);
            document.documentElement.setAttribute('data-color-theme', savedColor);
        }

        function setupUI(currentAppsData) {
            const mainTabsContainer = document.getElementById('mainTabs');
            const appSectionsContainer = document.getElementById('appSectionsContainer');
            const sidebarNav = document.getElementById('sidebarNav');

            const usedCategories = new Set(currentAppsData.map(app => app.category));
            
            const visibleMainTabs = mainTabsOrder.filter(catKey => usedCategories.has(catKey) || catKey === 'home' || catKey === 'favourite');
            visibleMainTabs.forEach(catKey => {
                if (!categoryInfo[catKey]) return;
                const tab = document.createElement('a');
                tab.href = '#'; tab.dataset.category = catKey;
                tab.textContent = categoryInfo[catKey].name.replace(/–| \(.*\)/g, '').trim();
                mainTabsContainer.appendChild(tab);
            });
            
            const sortedCategories = Object.keys(categoryInfo)
                .filter(k => k !== 'home' && k !== 'favourite' && usedCategories.has(k))
                .sort((a,b) => categoryInfo[a].name.localeCompare(categoryInfo[b].name));
            
            sidebarNav.appendChild(createSidebarLink('favourite'));
            sortedCategories.forEach(catKey => {
                sidebarNav.appendChild(createSidebarLink(catKey));
                const section = document.createElement('div');
                section.id = `section-${catKey}`; section.className = 'app-section';
                section.innerHTML = `<div class="app-grid" id="grid-${catKey}"></div>`;
                appSectionsContainer.appendChild(section);
            });
            
            // --- [UPDATE] Added Privacy Policy link ---
            const staticItems = [
                { id: 'aboutBtn', icon: 'fa-circle-info', text: 'About App' },
                { href: 'https://publicqgrm.github.io/ineed-privacy-policy/', icon: 'fa-shield-halved', text: 'Privacy Policy', target: '_blank' }
            ];

            staticItems.forEach(item => {
                const link = document.createElement('a');
                link.href = item.href || '#';
                if (item.id) link.id = item.id;
                if (item.target) {
                    link.target = item.target;
                    link.rel = 'noopener noreferrer';
                }
                link.innerHTML = `<i class="fa-solid ${item.icon}"></i><span>${item.text}</span>`;
                sidebarNav.appendChild(document.createElement('li')).appendChild(link);
            });
            
            const homeSection = document.createElement('div');
            homeSection.id = 'section-home'; homeSection.className = 'app-section';
            appSectionsContainer.prepend(homeSection);

            const favSection = document.createElement('div');
            favSection.id = 'section-favourite'; favSection.className = 'app-section';
            favSection.innerHTML = `<div class="app-grid" id="grid-favourite"></div>`;
            appSectionsContainer.appendChild(favSection);
            
            currentAppsData.forEach(app => {
                const categoryGrid = document.getElementById(`grid-${app.category}`);
                if (categoryGrid) categoryGrid.appendChild(createAppCard(app));
            });
            
            const favGrid = document.getElementById('grid-favourite');
            currentAppsData.filter(app => app.isFavourite).forEach(app => favGrid.appendChild(createAppCard(app)));

            populateSmartHomePage(currentAppsData);
        }

        function createSidebarLink(catKey) {
            const link = document.createElement('a');
            link.href = '#'; link.dataset.category = catKey;
            link.innerHTML = `<i class="${categoryInfo[catKey].icon}"></i><span>${categoryInfo[catKey].name}</span>`;
            const listItem = document.createElement('li');
            listItem.appendChild(link);
            return listItem;
        }
        
        function populateSmartHomePage(currentAppsData) {
            const homeSection = document.getElementById('section-home');
            homeSection.innerHTML = ''; 

            const favourites = currentAppsData.filter(app => app.isFavourite);
            if(favourites.length > 0) {
                homeSection.innerHTML += `<h2 class="grid-heading"><i class="fa-solid fa-star"></i> Favourites</h2>`;
                const favGrid = document.createElement('div');
                favGrid.className = 'app-grid';
                favourites.slice(0, 8).forEach(app => favGrid.appendChild(createAppCard(app)));
                homeSection.appendChild(favGrid);
            }

            const newApps = currentAppsData.filter(app => app.isNew);
             if(newApps.length > 0) {
                homeSection.innerHTML += `<h2 class="grid-heading"><i class="fa-solid fa-wand-magic-sparkles"></i> New Arrivals</h2>`;
                const newGrid = document.createElement('div');
                newGrid.className = 'app-grid';
                newApps.forEach(app => newGrid.appendChild(createAppCard(app)));
                homeSection.appendChild(newGrid);
            }

            homeSection.innerHTML += `<h2 class="grid-heading"><i class="fa-solid fa-compass"></i> Discover Apps</h2>`;
            const discoverGrid = document.createElement('div');
            discoverGrid.className = 'app-grid';
            const shuffled = [...currentAppsData].sort(() => 0.5 - Math.random());
            shuffled.slice(0, 12).forEach(app => discoverGrid.appendChild(createAppCard(app)));
            homeSection.appendChild(discoverGrid);
        }
        
        function createAppCard(app) {
            const card = document.createElement('a');
            card.className = 'app-card'; card.href = app.url;
            card.dataset.name = app.name.toLowerCase();
            card.dataset.placeholder = app.name.charAt(0).toUpperCase();
            
            const logoUrl = `https://www.google.com/s2/favicons?sz=64&domain_url=${app.url}`;
            const logoHtml = `<img src="${logoUrl}" alt="${app.name} Logo" class="app-logo" onerror="this.style.display='none'; this.nextSibling.style.display='flex';">
                            <div class="app-logo-placeholder" style="display:none;">${card.dataset.placeholder}</div>`;
            card.insertAdjacentHTML('beforeend', `${logoHtml}<span class="app-name">${app.name}</span>`);
            return card;
        }

        function showTabContent(category) {
            document.querySelectorAll('#mainTabs a').forEach(tab => tab.classList.toggle('active', tab.dataset.category === category));
            document.querySelectorAll('.app-section').forEach(section => section.classList.toggle('active', section.id === `section-${category}`));
            const searchInput = document.getElementById('appSearch');
            searchInput.value = ''; filterApps(); 
            const categoryName = categoryInfo[category]?.name || 'any app';
            searchInput.placeholder = `Search in ${categoryName}...`;
            window.scrollTo(0, 0);
        }
        
        function addEventListeners() {
            const menuBtn = document.getElementById('menuBtn');
            const sidebar = document.getElementById('sidebar');
            const overlay = document.getElementById('overlay');
            const searchBtn = document.getElementById('searchBtn');
            const searchContainer = document.getElementById('searchContainer');
            const searchInput = document.getElementById('appSearch');
            const aboutModal = document.getElementById('aboutModal');
            const closeBtn = aboutModal.querySelector('.modal-close-btn');

            const toggleSidebar = () => { sidebar.classList.toggle('open'); overlay.classList.toggle('active'); };
            menuBtn.addEventListener('click', toggleSidebar);
            overlay.addEventListener('click', toggleSidebar);

            searchBtn.addEventListener('click', () => { searchContainer.classList.toggle('active'); if (searchContainer.classList.contains('active')) searchInput.focus(); });
            
            document.querySelectorAll('#sidebarNav a[data-category]').forEach(tab => {
                tab.addEventListener('click', (e) => {
                    e.preventDefault();
                    const link = e.target.closest('a');
                    if (link && link.dataset.category) { showTabContent(link.dataset.category); if (sidebar.classList.contains('open')) toggleSidebar(); }
                });
            });

            document.querySelectorAll('#mainTabs a').forEach(tab => {
                tab.addEventListener('click', (e) => {
                    e.preventDefault();
                    const link = e.target.closest('a');
                    if (link && link.dataset.category) { showTabContent(link.dataset.category); }
                });
            });

            sidebarNav.addEventListener('click', (e) => {
                const link = e.target.closest('a');
                if (link && link.id === 'aboutBtn') { 
                    e.preventDefault(); 
                    aboutModal.classList.add('show'); 
                    if (sidebar.classList.contains('open')) toggleSidebar(); 
                }
            });
            
            document.getElementById('appSectionsContainer').addEventListener('click', function(e) {
                const card = e.target.closest('.app-card');
                if (card) { e.preventDefault(); showSplashScreen(card); }
            });

            closeBtn.addEventListener('click', () => aboutModal.classList.remove('show'));
            window.addEventListener('click', (event) => { if (event.target == aboutModal) aboutModal.classList.remove('show'); });
            searchInput.addEventListener('keydown', (event) => { if (event.key === 'Enter') { event.preventDefault(); const query = searchInput.value.trim(); if (query) window.open(`https://www.google.com/search?q=${encodeURIComponent(query)}`, '_blank'); } });
        }
        
        function showSplashScreen(card) {
            const loadingOverlay = document.getElementById('loadingOverlay');
            const loadingLogo = document.getElementById('loadingLogo');
            const loadingLogoPlaceholder = document.getElementById('loadingLogoPlaceholder');
            const loadingAppName = document.getElementById('loadingAppName');
            const url = card.href;
            const appName = card.querySelector('.app-name').textContent;
            const logoImg = card.querySelector('.app-logo');
            loadingAppName.textContent = `Opening ${appName}...`;
            if (logoImg.style.display !== 'none' && logoImg.complete && logoImg.naturalHeight !== 0) {
                loadingLogo.src = logoImg.src; loadingLogo.style.display = 'block'; loadingLogoPlaceholder.style.display = 'none';
            } else {
                loadingLogoPlaceholder.textContent = card.dataset.placeholder; loadingLogo.style.display = 'none'; loadingLogoPlaceholder.style.display = 'flex';
            }
            loadingOverlay.style.display = 'flex';
            setTimeout(() => { window.location.href = url; }, 1200); // Redirect in same tab
        }

        function filterApps() {
            const searchTerm = document.getElementById('appSearch').value.toLowerCase();
            const activeSection = document.querySelector('.app-section.active');
            if (!activeSection) return;
            const grids = activeSection.querySelectorAll('.app-grid');
            grids.forEach(grid => {
                let hasVisibleCard = false;
                grid.querySelectorAll('.app-card').forEach(card => {
                    const isVisible = card.dataset.name.includes(searchTerm);
                    card.style.display = isVisible ? 'flex' : 'none';
                    if (isVisible) hasVisibleCard = true;
                });
                const heading = grid.previousElementSibling;
                if(heading && heading.classList.contains('grid-heading')) { heading.style.display = hasVisibleCard ? 'block' : 'none'; }
            });
        }

        function setupThemeControls() {
            const darkModeToggle = document.getElementById('darkModeToggle');
            const swatchesContainer = document.getElementById('colorSwatchesContainer');
            const currentTheme = localStorage.getItem('theme') || 'light';
            const currentColor = localStorage.getItem('colorTheme') || 'blue';
            darkModeToggle.checked = currentTheme === 'dark';
            darkModeToggle.addEventListener('change', (e) => {
                const theme = e.target.checked ? 'dark' : 'light';
                document.documentElement.setAttribute('data-theme', theme);
                localStorage.setItem('theme', theme);
            });
            colorThemes.forEach(color => {
                const swatch = document.createElement('div');
                swatch.className = 'color-swatch'; swatch.style.backgroundColor = color.value; swatch.dataset.colorName = color.name;
                if (color.name === currentColor) swatch.classList.add('active');
                swatch.addEventListener('click', () => {
                    document.documentElement.setAttribute('data-color-theme', color.name);
                    localStorage.setItem('colorTheme', color.name);
                    swatchesContainer.querySelector('.active')?.classList.remove('active');
                    swatch.classList.add('active');
                });
                swatchesContainer.appendChild(swatch);
            });
        }
    </script>
</body>
</html>
