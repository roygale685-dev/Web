<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roy Gale Motors | Premium BMW Inventory</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        /* CSS VARIABLES & RESET */
        :root {
            --primary-black: #111111;
            --bmw-blue: #0066b1;
            --m-red: #e32221;
            --m-blue: #00387b;
            --light-gray: #f4f4f4;
            --text-dark: #333333;
            --text-light: #ffffff;
        }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }
        body { background-color: var(--light-gray); color: var(--text-dark); overflow-x: hidden; }
        a { text-decoration: none; color: inherit; }
        ul { list-style: none; }

        /* HEADER & NAVIGATION */
        header {
            background-color: var(--primary-black);
            color: var(--text-light);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.5);
        }
        .logo { font-size: 1.5rem; font-weight: 800; letter-spacing: 2px; }
        .logo span { color: var(--bmw-blue); }
        nav ul { display: flex; gap: 2rem; }
        nav ul li a { font-weight: 600; transition: color 0.3s; font-size: 0.9rem; text-transform: uppercase; }
        nav ul li a:hover { color: var(--bmw-blue); }

        /* HERO SECTION */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.8)), url('https://images.unsplash.com/photo-1555099962-4199c345e5dd?q=80&w=2070&auto=format&fit=crop') center/cover no-repeat;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: var(--text-light);
            padding: 0 20px;
        }
        .hero h1 { font-size: 4rem; font-weight: 800; margin-bottom: 1rem; text-transform: uppercase; letter-spacing: 1px; }
        .hero p { font-size: 1.2rem; margin-bottom: 2rem; max-width: 600px; font-weight: 300; }
        .btn-primary {
            background-color: var(--bmw-blue);
            color: var(--text-light);
            padding: 15px 30px;
            font-size: 1rem;
            font-weight: 600;
            border: none;
            cursor: pointer;
            transition: background 0.3s, transform 0.2s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .btn-primary:hover { background-color: #005291; transform: translateY(-2px); }

        /* INVENTORY SECTION */
        .inventory-section { padding: 5rem 5%; max-width: 1400px; margin: 0 auto; }
        .section-header { text-align: center; margin-bottom: 3rem; }
        .section-header h2 { font-size: 2.5rem; font-weight: 800; color: var(--primary-black); }
        
        /* FILTERS */
        .filters { display: flex; justify-content: center; gap: 1rem; margin-bottom: 3rem; flex-wrap: wrap; }
        .filter-btn {
            background: transparent;
            border: 2px solid var(--primary-black);
            padding: 10px 20px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }
        .filter-btn.active, .filter-btn:hover {
            background: var(--primary-black);
            color: var(--text-light);
        }

        /* GRID & CARDS */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2rem;
        }
        .card {
            background: #fff;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            transition: transform 0.3s, box-shadow 0.3s;
            display: flex;
            flex-direction: column;
        }
        .card:hover { transform: translateY(-10px); box-shadow: 0 15px 30px rgba(0,0,0,0.15); }
        .card-img { width: 100%; height: 220px; object-fit: cover; }
        .card-content { padding: 1.5rem; display: flex; flex-direction: column; flex-grow: 1; }
        .tag { font-size: 0.75rem; font-weight: 800; color: var(--m-red); text-transform: uppercase; margin-bottom: 0.5rem; }
        .card-title { font-size: 1.5rem; font-weight: 800; margin-bottom: 0.5rem; }
        .card-specs { display: flex; justify-content: space-between; font-size: 0.9rem; color: #666; margin-bottom: 1.5rem; padding-bottom: 1rem; border-bottom: 1px solid #eee; }
        .card-price { font-size: 1.5rem; font-weight: 800; color: var(--primary-black); margin-bottom: 1.5rem; }
        .btn-outline {
            text-align: center;
            border: 2px solid var(--primary-black);
            padding: 12px;
            font-weight: 600;
            transition: all 0.3s;
            margin-top: auto;
        }
        .btn-outline:hover { background: var(--primary-black); color: var(--text-light); }

        /* FOOTER */
        footer { background: var(--primary-black); color: var(--text-light); padding: 4rem 5% 2rem; text-align: center; }
        .footer-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; margin-bottom: 2rem; text-align: left;}
        .footer-col h3 { font-size: 1.2rem; margin-bottom: 1rem; color: var(--bmw-blue); }
        .footer-col p, .footer-col a { color: #ccc; font-size: 0.9rem; margin-bottom: 0.5rem; display: block; }
        .footer-bottom { border-top: 1px solid #333; padding-top: 2rem; font-size: 0.8rem; color: #888; }
        
        /* RESPONSIVE */
        @media (max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            nav ul { display: none; } /* Mobile menu simplified for demo */
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">BAVARIAN<span>MOTORS</span></div>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#inventory">Inventory</a></li>
                <li><a href="#">Finance</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <h1>Sheer Driving Pleasure</h1>
        <p>Explore our curated selection of the ultimate driving machines. From dynamic sedans to versatile SAVs and electrified performance.</p>
        <button class="btn-primary" onclick="document.getElementById('inventory').scrollIntoView({behavior: 'smooth'})">View Inventory</button>
    </section>

    <section id="inventory" class="inventory-section">
        <div class="section-header">
            <h2>Current Inventory</h2>
            <p>Find the BMW that fits your lifestyle.</p>
        </div>

        <div class="filters">
            <button class="filter-btn active" onclick="filterCars('all')">All Models</button>
            <button class="filter-btn" onclick="filterCars('sedan')">Sedans</button>
            <button class="filter-btn" onclick="filterCars('suv')">SUVs (X Series)</button>
            <button class="filter-btn" onclick="filterCars('m-series')">M Performance</button>
            <button class="filter-btn" onclick="filterCars('ev')">Electric (i Series)</button>
        </div>

        <div class="grid" id="carGrid">
            
            <div class="card" data-category="sedan">
                <img src="https://images.unsplash.com/photo-1556189250-72ba954cfc2b?q=80&w=2070&auto=format&fit=crop" alt="BMW 3 Series" class="card-img">
                <div class="card-content">
                    <span class="tag">New Arrival</span>
                    <h3 class="card-title">2026 BMW 330i xDrive</h3>
                    <div class="card-specs">
                        <span>255 HP</span>
                        <span>0-60 in 5.4s</span>
                        <span>24/33 MPG</span>
                    </div>
                    <div class="card-price">$47,500</div>
                    <a href="#" class="btn-outline">View Details</a>
                </div>
            </div>

            <div class="card" data-category="m-series">
                <img src="https://images.unsplash.com/photo-1617814076367-b759c7d7e738?q=80&w=2070&auto=format&fit=crop" alt="BMW M4" class="card-img">
                <div class="card-content">
                    <span class="tag">High Performance</span>
                    <h3 class="card-title">2026 BMW M4 Competition</h3>
                    <div class="card-specs">
                        <span>503 HP</span>
                        <span>0-60 in 3.4s</span>
                        <span>16/23 MPG</span>
                    </div>
                    <div class="card-price">$84,200</div>
                    <a href="#" class="btn-outline">View Details</a>
                </div>
            </div>

            <div class="card" data-category="suv">
                <img src="https://images.unsplash.com/photo-1603584173870-7f23fdae1b7a?q=80&w=2069&auto=format&fit=crop" alt="BMW X5" class="card-img">
                <div class="card-content">
                    <span class="tag">Premium SAV</span>
                    <h3 class="card-title">2026 BMW X5 xDrive40i</h3>
                    <div class="card-specs">
                        <span>375 HP</span>
                        <span>0-60 in 5.3s</span>
                        <span>23/27 MPG</span>
                    </div>
                    <div class="card-price">$68,900</div>
                    <a href="#" class="btn-outline">View Details</a>
                </div>
            </div>

            <div class="card" data-category="ev">
                <img src="https://images.unsplash.com/photo-1669023030485-573b6ac99770?q=80&w=2070&auto=format&fit=crop" alt="BMW i4" class="card-img">
                <div class="card-content">
                    <span class="tag">100% Electric</span>
                    <h3 class="card-title">2026 BMW i4 eDrive40</h3>
                    <div class="card-specs">
                        <span>335 HP</span>
                        <span>301 mi Range</span>
                        <span>DC Fast Charge</span>
                    </div>
                    <div class="card-price">$57,300</div>
                    <a href="#" class="btn-outline">View Details</a>
                </div>
            </div>
            
            <div class="card" data-category="sedan">
                <img src="https://images.unsplash.com/photo-1553440569-bcc63803a83d?q=80&w=2025&auto=format&fit=crop" alt="BMW 5 Series" class="card-img">
                <div class="card-content">
                    <span class="tag">Executive</span>
                    <h3 class="card-title">2026 BMW 540i xDrive</h3>
                    <div class="card-specs">
                        <span>375 HP</span>
                        <span>0-60 in 4.4s</span>
                        <span>26/33 MPG</span>
                    </div>
                    <div class="card-price">$64,900</div>
                    <a href="#" class="btn-outline">View Details</a>
                </div>
            </div>

            <div class="card" data-category="suv">
                <img src="https://images.unsplash.com/photo-1658428173950-705b76654b9f?q=80&w=2070&auto=format&fit=crop" alt="BMW X7" class="card-img">
                <div class="card-content">
                    <span class="tag">Luxury 3-Row</span>
                    <h3 class="card-title">2026 BMW X7 M60i</h3>
                    <div class="card-specs">
                        <span>523 HP</span>
                        <span>0-60 in 4.5s</span>
                        <span>16/21 MPG</span>
                    </div>
                    <div class="card-price">$110,900</div>
                    <a href="#" class="btn-outline">View Details</a>
                </div>
            </div>

        </div>
    </section>

    <footer>
        <div class="footer-grid">
            <div class="footer-col">
                <h3>Bavarian Motors</h3>
                <p>123 Performance Drive</p>
                <p>Apia, Samoa</p>
                <p>Sales: (555) 123-4567</p>
            </div>
            <div class="footer-col">
                <h3>Quick Links</h3>
                <a href="#">Search Inventory</a>
                <a href="#">Apply for Financing</a>
                <a href="#">Schedule Service</a>
            </div>
            <div class="footer-col">
                <h3>Hours</h3>
                <p>Mon - Fri: 9:00 AM - 7:00 PM</p>
                <p>Saturday: 10:00 AM - 5:00 PM</p>
                <p>Sunday: Closed</p>
            </div>
        </div>
        <div class="footer-bottom">
            &copy; 2026 Bavarian Motors. All Rights Reserved. "BMW" and the BMW logo are registered trademarks of BMW AG.
        </div>
    </footer>

    <script>
        function filterCars(category) {
            // Update active button styling
            const buttons = document.querySelectorAll('.filter-btn');
            buttons.forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');

            // Filter the cards
            const cards = document.querySelectorAll('.card');
            cards.forEach(card => {
                if (category === 'all' || card.getAttribute('data-category') === category) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>

