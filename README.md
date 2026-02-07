<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">te
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML ASSIGNMENT - Solar System Data</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Add phone favicon -->
    <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>📱</text></svg>">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            font-family:  'Times New Roman', Times, serif;
            line-height: 1.6;
            max-width: 1200px;
            margin: 0 auto;
            background-color: white;
            width: 100%;
            color: black;
        }

        /* Consistent section spacing */
        .section-divider {
            border: none;
            height: 2px;
            background: linear-gradient(to right, transparent, rgb(14, 31, 78), transparent);
            margin: 40px auto;
            width: calc(100% - 40px);
            max-width: 1160px;
        }

        /* ====================
           LOGO SECTION
           ==================== */
        .logo-section {
            padding: 10px 20px;
            background-color: rgb(14, 31, 78);
        }

        .logo-image {
            height: 40px;
            width: auto;
        }

        .logo-section hr {
            border: none;
            height: 2px;
            background-color: rgba(241, 191, 63, 0.3);
            width: 100%;
            margin-top: 10px;
        }

        /* ====================
           HEADER SECTION
           ==================== */
        .header-container {
            display: flex;
            align-items: center;
            padding: 40px;
            background-color: rgb(14, 31, 78);
            color: #f5f5f5;
            gap: 40px;
            margin: 0 auto;
            max-width: 1200px;
        }

        .header-content {
            flex: 1;
            text-align: left;
        }

        .page-title {
            font-size: 2.5rem;
            margin-bottom: 20px;
            line-height: 1.3;
        }

        .page-subtitle {
            font-size: 1.2rem;
            margin-bottom: 30px;
            line-height: 1.8;
            text-align: justify;
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-top: 30px;
        }

        /* UPDATED: Buttons with icons */
        .cta-button,
        .submit-button {
            background-color: rgb(14, 31, 78);
            color: white;
            border: 2px solid rgb(14, 31, 78);
            padding: 14px 35px;
            font-size: 1.1rem;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            text-align: center;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            text-decoration: none;
        }

        .cta-button:hover,
        .submit-button:hover {
            background-color: white;
            color: rgb(14, 31, 78);
            border-color: rgb(14, 31, 78);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(14, 31, 78, 0.2);
        }

        /* Button icon styling */
        .button-icon {
            font-size: 1.1rem;
            transition: transform 0.3s ease;
        }

        .cta-button:hover .button-icon {
            transform: translateX(3px);
        }

        /* UPDATED: Call us link with phone icon */
        .action-link {
            color: #f0f1f1;
            text-decoration: none;
            font-size: 1rem;
            border-bottom: 2px solid #f0f1f1;
            padding-bottom: 2px;
            transition: all 0.3s ease;
            background-color: transparent;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .action-link:hover {
            color: rgb(14, 31, 78);
            border-bottom: 2px solid rgb(14, 31, 78);
            background-color: #f0f1f1;
            padding: 8px 15px;
            border-radius: 4px;
            margin: -8px -15px;
        }

        /* Phone icon styling */
        .phone-icon {
            font-size: 1.2rem;
            transition: transform 0.3s ease;
        }

        .action-link:hover .phone-icon {
            transform: rotate(15deg) scale(1.2);
            color: rgb(14, 31, 78);
        }

        .header-image {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .circular-image {
            border-radius: 50%;
            object-fit: cover;
            width: 400px;
            height: 400px;
            border: 1px solid rgba(21, 6, 149, 0.1);
        }

        /* ====================
           MAIN CONTENT SECTIONS
           ==================== */
        .content-section {
            padding: 40px;
            background-color: white;
            margin: 20px auto;
            border-radius: 8px;
            max-width: 1200px;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 20px;
            color: rgb(14, 31, 78);
            padding-bottom: 10px;
            border-bottom: 2px solid #eee;
        }

        .section-description {
            font-size: 1.1rem;
            color: #555;
            margin-bottom: 30px;
            line-height: 1.7;
            text-align: justify;
        }

        /* REMOVED: highlight-text and kepler-text classes */
        /* All colored text highlighting is removed except in footer */

        /* ====================
           MEDIA & GALLERY
           ==================== */
        .media-wrapper {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .video-container {
            width: 100%;
            height: 400px;
            border-radius: 15px;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .video-iframe {
            width: 100%;
            height: 100%;
            border: none;
            border-radius: 15px;
        }

        /* ====================
           PLANET GRID
           ==================== */
        .planet-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin: 20px 0;
        }

        .planet {
            width: 100%;
            height: 200px;
            border-radius: 8px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .planet:hover {
            transform: scale(1.05);
        }

        /* ====================
           DATA TABLE
           ==================== */
        .data-table-container {
            overflow-x: auto;
            margin-top: 20px;
            border-radius: 8px;
        }

        .planet-data-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 1rem;
            text-align: center;
        }

        .table-caption {
            font-size: 0.95rem;
            font-style: italic;
            margin-bottom: 15px;
            display: block;
            color: #666;
            text-align: center;
        }

        .planet-data-table th,
        .planet-data-table td {
            padding: 15px 12px;
            border: 1px solid #ddd;
        }

        .planet-data-table th {
            background-color: rgb(14, 31, 78);
            color: white;
            font-weight: 600;
        }

        .planet-data-table tbody tr:nth-child(even) {
            background-color: #f9f9f9;
        }

        .planet-data-table tbody tr:hover {
            background-color: #f0f7ff;
        }

        .planet-category {
            font-weight: bold;
            color: rgb(14, 31, 78);
            background-color: #f0f7ff;
            text-align: left;
            padding-left: 20px;
        }

        .planet-name-cell {
            font-weight: 600;
            text-align: left;
            padding-left: 15px;
        }

        /* ====================
           CONTACT FORM
           ==================== */
        .contact-form-section {
            padding: 40px;
            background-color: white;
            margin: 20px auto;
            border-radius: 8px;
            max-width: 1200px;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
            margin-bottom: 25px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-label {
            font-weight: bold;
            margin-bottom: 8px;
            color: #444;
        }

        .required-field {
            color: #e63946;
        }

        .form-input,
        .form-select,
        .form-textarea {
            padding: 12px 15px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-size: 1rem;
            font-family: inherit;
            transition: border-color 0.3s, box-shadow 0.3s;
        }

        .form-input:focus,
        .form-select:focus,
        .form-textarea:focus {
            outline: none;
            border-color: rgb(14, 31, 78);
            box-shadow: 0 0 0 3px rgba(14, 31, 78, 0.1);
        }

        .form-textarea {
            resize: vertical;
            min-height: 120px;
        }

        .char-counter {
            font-size: 0.9rem;
            color: #666;
            margin-top: 8px;
            text-align: right;
        }

        .input-group {
            margin-bottom: 25px;
        }

        .control-label {
            font-weight: bold;
            display: block;
            margin-bottom: 12px;
            color: #444;
        }

        .radio-options,
        .checkbox-options {
            display: flex;
            gap: 30px;
            flex-wrap: wrap;
        }

        .option-item {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .submit-container {
            margin-top: 30px;
            text-align: center;
        }

        /* ====================
           FOOTER SECTION
           ==================== */
        footer {
            background-color: rgb(14, 31, 78);
            color: white;
            padding: 40px;
            margin: 20px auto 0;
            border-radius: 15px;
            max-width: 1200px;
        }

        .footer-container {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .footer-header {
            text-align: left;
        }

        .footer-title {
            font-size: 2rem;
            margin-bottom: 15px;
            color: #fff;
            font-weight: 600;
        }

        .footer-description {
            font-size: 1.1rem;
            line-height: 1.6;
            color: #fff;
            text-align: left;
            margin-bottom: 20px;
        }

        /* KEPT: Colored planet names only in footer */
        .planet-name {
            color: #ffd43b;
            font-weight: bold;
        }

        .footer-divider {
            border: none;
            height: 1px;
            background: linear-gradient(to right, transparent, rgba(241, 191, 63, 0.5), transparent);
            width: 100%;
            margin: 10px 0 20px 0;
        }

        /* UPDATED FOOTER CONTENT */
        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            border-radius: 10px;
            padding-bottom: 40px;
            margin-bottom: 10px;
        }

        .copyright {
            font-size: 1rem;
            color: #fff;
            margin: 0;
            line-height: 1.5;
        }

        /* Right-aligned items container */
        .footer-right {
            display: flex;
            align-items: center;
            gap: 40px;
        }

        .privacy-link {
            color: #4dabf7;
            text-decoration: none;
            transition: color 0.3s;
            font-size: 1rem;
            white-space: nowrap;
        }

        .privacy-link:hover {
            color: #339af0;
            text-decoration: underline;
        }

        .terms-text {
            font-size: 1rem;
            color: #fff;
            margin: 0;
            line-height: 1.5;
            white-space: nowrap;
        }

        /* ====================
           RESPONSIVE DESIGN
           ==================== */
        @media (max-width: 992px) {
            .header-container {
                flex-direction: column;
                text-align: center;
                padding: 30px;
            }
            
            .header-content {
                text-align: center;
            }
            
            .page-title {
                text-align: center;
            }
            
            .page-subtitle {
                text-align: justify;
                margin: 0 auto 30px;
            }
            
            .header-actions {
                justify-content: center;
            }
            
            .circular-image {
                width: 320px;
                height: 320px;
            }
            
            .planet-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .video-container {
                height: 350px;
            }
            
            .content-section,
            .contact-form-section,
            footer {
                padding: 30px;
            }
            
            .footer-content {
                gap: 25px;
            }
            
            .footer-right {
                gap: 25px;
            }
        }

        @media (max-width: 768px) {
            .form-row {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .radio-options,
            .checkbox-options {
                flex-direction: column;
                gap: 15px;
            }
            
            .content-section,
            .contact-form-section,
            footer {
                padding: 25px;
                margin: 15px auto;
            }
            
            .section-title {
                font-size: 1.7rem;
            }
            
            .page-title {
                font-size: 2rem;
            }
            
            .video-container {
                height: 300px;
            }
            
            .planet-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 20px;
                align-items: flex-start;
            }
            
            .footer-right {
                width: 100%;
                justify-content: space-between;
                margin-top: 10px;
            }
        }

        @media (max-width: 576px) {
            .header-container,
            .content-section,
            .contact-form-section,
            footer {
                padding: 20px;
            }
            
            .circular-image {
                width: 280px;
                height: 280px;
            }
            
            .video-container {
                height: 250px;
            }
            
            .planet {
                height: 180px;
            }
            
            .planet-data-table {
                font-size: 0.9rem;
            }
            
            .planet-data-table th,
            .planet-data-table td {
                padding: 10px 8px;
            }
            
            .header-actions {
                flex-direction: column;
                gap: 15px;
            }
            
            .cta-button, .action-link, .submit-button {
                width: 100%;
                text-align: center;
            }
            
            .footer-title {
                font-size: 1.7rem;
            }
            
            .footer-description {
                font-size: 1rem;
            }
            
            .footer-content {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .footer-right {
                flex-direction: column;
                align-items: flex-start;
                gap: 15px;
                width: 100%;
            }
        }

        /* ====================
           ANIMATIONS
           ==================== */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s, transform 0.5s;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

    </style>
</head>

<body>
    
    <!-- LOGO SECTION -->
    <div class="logo-section">
        <div class="logo-container">
            <img src="space logo.png" alt="Space Exploration Logo" class="logo-image"> 
        </div>
        <hr/>
    </div>
    
    <!-- HEADER SECTION -->
    <div class="header-container">
        <div class="header-content">
            <h1 class="page-title">EXPLORE OUR SOLAR SYSTEM THROUGH DATA</h1>
            <p class="page-subtitle">Understand the planets not just by name but with measurable data from size, mass to gravity and density. This page breaks down the data in a clear and driving way. Our solar system consists of eight planets, several dwarf planets, and countless smaller bodies orbiting our Sun. Each planet has unique characteristics that define its place in our cosmic neighborhood.</p>
            <div class="header-actions">
                <button type="button" class="cta-button">
                    <i class="fas fa-envelope button-icon"></i>
                    Contact us
                </button>
                <a href="tel:+1234567890" class="action-link">
                    <i class="fas fa-phone phone-icon"></i>
                    Call us
                </a>
            </div>
        </div>
        
        <div class="header-image">
            <img src="istockphoto-648459820-612x612xxxx.jpg" 
                 alt="The sun and nine planets of our system orbiting"
                 class="circular-image">
        </div>
    </div>
    
    <hr class="section-divider">

    <!-- MAIN CONTENT -->
    <main>
        <!-- Section 1: Planetary Orbits -->
        <div class="content-section">
            <h2 class="section-title">Understanding Planetary Orbits</h2>
            <p class="section-description">Planets in our solar system follow elliptical orbits around the Sun, with orbital periods ranging from 88 days for Mercury to 165 years for Neptune. These orbits are governed by gravitational forces and follow Kepler's laws of planetary motion. The shape and size of a planet's orbit determine its distance from the Sun and its orbital velocity. Inner planets have shorter, faster orbits while outer planets have longer, slower paths around the Sun.</p>
            
            <div class="media-wrapper">
                <div class="video-container">
                    <iframe width="894" height="503" src="https://www.youtube.com/embed/libKVRa01L8" title="Solar System 101 | National Geographic" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
            </div>
        </div>
        
        <hr class="section-divider">
        
        <!-- Section 2: Planetary Classification -->
        <div class="content-section">
            <h2 class="section-title">Planetary Classification and Features</h2>
            <p class="section-description">Planets in our solar system are categorized based on their composition and position. Terrestrial planets (Mercury, Venus, Earth, Mars) have solid surfaces, while Jovian planets (Jupiter, Saturn, Uranus, Neptune) are primarily hydrogen and helium. These classifications help astronomers understand planetary formation and evolution throughout the solar system's history.</p>
            
            <div class="planet-grid">
                <img src="planet1.webp" alt="Terrestrial planet with rocky surface" class="planet">
                <img src="planet1.webp" alt="Gas giant with atmospheric bands" class="planet">
                <img src="planet1.webp" alt="Jovian planet with blue atmosphere" class="planet">
                <img src="planet1.webp" alt="Terrestrial planet with rocky surface" class="planet">
                <img src="planet1.webp" alt="Jovian planet with atmospheric bands" class="planet">
                <img src="planet1.webp" alt="Jovian planet with blue atmosphere" class="planet">
            </div>
        </div>
        
        <hr class="section-divider">
        
        <!-- Section 3: Data Table -->
        <div class="content-section">
            <h2 class="section-title">Comparative Planetary Data Analysis</h2>
            <p class="section-description">The following table presents key physical characteristics of solar system bodies, allowing for direct comparison of their properties. This data reveals patterns in planetary formation and helps scientists understand the diversity of worlds in our cosmic neighborhood.</p>
            
            <div class="data-table-container">
                <table class="planet-data-table">
                    <caption class="table-caption">Data about the planets of our solar system (Planetary facts taken from Nasa)</caption>
                    <thead>
                        <tr>
                            <th rowspan="2">&nbsp;</th>
                            <th rowspan="2">Name</th>
                            <th>Mass (10<sup>24</sup>kg)</th>
                            <th>Diameter (km)</th>
                            <th>Density (kg/m<sup>3</sup>)</th>
                            <th>Gravity (m/s<sup>2</sup>)</th>
                        </tr>
                    </thead>
                    <tbody>
                        <!-- Terrestrial Planets Group -->
                        <tr>
                            <td class="planet-category" rowspan="4">Terrestrial Planets</td>
                            <td class="planet-name-cell">Mercury</td>
                            <td>0.330</td>
                            <td>4,878</td>
                            <td>5,427</td>
                            <td>3.7</td>
                        </tr>
                        <tr>
                            <td class="planet-name-cell">Venus</td>
                            <td>4.87</td>
                            <td>12,104</td>
                            <td>5,243</td>
                            <td>8.9</td>
                        </tr>
                        <tr>
                            <td class="planet-name-cell">Earth</td>
                            <td>5.97</td>
                            <td>12,756</td>
                            <td>5,514</td>
                            <td>9.8</td>
                        </tr>
                        <tr>
                            <td class="planet-name-cell">Mars</td>
                            <td>0.642</td>
                            <td>6,792</td>
                            <td>3,933</td>
                            <td>3.7</td>
                        </tr>

                        <!-- Jovian Planets Group (Fixed) -->
                        <tr>
                            <td class="planet-category" rowspan="4">Jovian Planets</td>
                            <td class="planet-name-cell">Jupiter</td>
                            <td>1,898</td>
                            <td>142,984</td>
                            <td>1,326</td>
                            <td>23.1</td>
                        </tr>
                        <tr>
                            <td class="planet-name-cell">Saturn</td>
                            <td>568</td>
                            <td>120,536</td>
                            <td>687</td>
                            <td>9.0</td>
                        </tr>
                        <tr>
                            <td class="planet-name-cell">Uranus</td>
                            <td>86.8</td>
                            <td>51,118</td>
                            <td>1,271</td>
                            <td>8.7</td>
                        </tr>
                        <tr>
                            <td class="planet-name-cell">Neptune</td>
                            <td>102</td>
                            <td>49,528</td>
                            <td>1,638</td>
                            <td>11.0</td>
                        </tr>

                        <!-- Dwarf Planets Group -->
                        <tr>
                            <td class="planet-category" rowspan="1">Dwarf Planets</td>
                            <td class="planet-name-cell">Pluto</td>
                            <td>0.0131</td>
                            <td>2,376</td>
                            <td>1,854</td>
                            <td>0.7</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </main>
    
    <hr class="section-divider">

    <!-- CONTACT FORM -->
    <div class="contact-form-section">
        <h2 class="section-title">Get in Touch with Astronomy Experts</h2>
        <p class="section-description">Our team of astronomy researchers and educators is available to answer your questions about the solar system, planetary science, and astronomical phenomena. Contact us for educational resources or research inquiries. We provide detailed information about current astronomical events, planetary observations, and space exploration missions.</p>
        
        <form id="contact-form" action="process.php" method="POST">
            <div class="form-row">
                <div class="form-group">
                    <label for="fname" class="form-label">Full Name: <span class="required-field">*</span></label>
                    <input type="text" id="fname" name="full_name" class="form-input" placeholder="Enter full name" required>
                </div>
                
                <div class="form-group">
                    <label for="email" class="form-label">Email Address: <span class="required-field">*</span></label>
                    <input type="email" id="email" name="email_address" class="form-input" placeholder="your.email@example.com" required>
                </div>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="city" class="form-label">Select your city:</label>
                    <select id="city" name="city" class="form-select" required>
                        <option value="">-- Choose a city --</option>
                        <option value="new-york">New York</option>
                        <option value="los-angeles">Los Angeles</option>
                        <option value="chicago">Chicago</option>
                        <option value="houston">Houston</option>
                        <option value="miami">Miami</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="phone" class="form-label">Phone Number: <span class="required-field">*</span></label>
                    <input type="tel" id="phone" name="phone_number" class="form-input" placeholder="Phone Number" required>
                </div>
            </div>
            
            <div class="form-group">
                <label for="message" class="form-label">Message: <span class="required-field">*</span></label>
                <textarea id="message" name="message" class="form-textarea" rows="4" maxlength="100" placeholder="Tell us about your astronomy questions or interests..." required></textarea>
                <div class="char-counter"><span id="charCount">100</span> characters remaining</div>
            </div>
            
            <div class="input-group">
                <label class="control-label">How should we contact you? <span class="required-field">*</span></label>
                <div class="radio-options">
                    <div class="option-item">
                        <input type="radio" id="contact_phone" name="contact_method" value="phone" required>
                        <label for="contact_phone">Phone</label>
                    </div>
                    <div class="option-item">
                        <input type="radio" id="contact_email" name="contact_method" value="email" required>
                        <label for="contact_email">Email</label>
                    </div>
                    <div class="option-item">
                        <input type="radio" id="contact_others" name="contact_method" value="others" required>
                        <label for="contact_others">Others</label>
                    </div>
                </div>
            </div>
            
            <div class="input-group">
                <label class="control-label">How did you hear about us?</label>
                <div class="checkbox-options">
                    <div class="option-item">
                        <input type="checkbox" id="friend" name="source[]" value="friend">
                        <label for="friend">Friend</label>
                    </div>
                    <div class="option-item">
                        <input type="checkbox" id="ts_academy" name="source[]" value="ts_academy">
                        <label for="ts_academy">Ts Academy</label>
                    </div>
                    <div class="option-item">
                        <input type="checkbox" id="other_source" name="source[]" value="others">
                        <label for="other_source">Others</label>
                    </div>
                </div>
            </div>
            
            <div class="submit-container">
                <button type="submit" class="submit-button">Submit Form</button>
            </div>
        </form>
    </div>
    
    <!-- FOOTER SECTION -->
    <footer>
        <div class="footer-container">
            <div class="footer-header">
                <h2 class="footer-title">About</h2>
                <p class="footer-description">Dedicated to promoting space science education and astronomical literacy through comprehensive solar system data visualization and analysis of planets like <span class="planet-name">Jupiter</span> and <span class="planet-name">Saturn</span>.</p>
                <hr class="footer-divider">
            </div>
            
            <div class="footer-content">
                <p class="copyright">© 2026 Ahmadallahyy. All rights reserved.</p>
                
                <div class="footer-right">
                    <a href="#" class="privacy-link">Privacy and Policy</a>
                    <p class="terms-text">Terms and Condition</p>
                </div>
            </div>
        </div>
    </footer>

    <script>
        document.getElementById('message').addEventListener('input', function() {
            const maxLength = 100;
            const currentLength = this.value.length;
            const remaining = maxLength - currentLength;
            document.getElementById('charCount').textContent = remaining;
            
            const charCountElement = document.getElementById('charCount');
            if (remaining < 20) {
                charCountElement.style.color = '#e63946';
                charCountElement.style.fontWeight = 'bold';
            } else {
                charCountElement.style.color = '#666';
                charCountElement.style.fontWeight = 'normal';
            }
        });
        
        const form = document.getElementById('contact-form');
        const inputs = form.querySelectorAll('.form-input, .form-select, .form-textarea');
        
        inputs.forEach(input => {
            input.addEventListener('blur', function() {
                if (!this.value && this.hasAttribute('required')) {
                    this.style.borderColor = '#e63946';
                } else {
                    this.style.borderColor = '#ccc';
                }
            });
            
            input.addEventListener('focus', function() {
                this.style.borderColor = 'rgb(14, 31, 78)';
            });
        });
        
        document.addEventListener('DOMContentLoaded', function() {
            const fadeElements = document.querySelectorAll('.content-section, .contact-form-section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            fadeElements.forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(20px)';
                el.style.transition = 'opacity 0.5s, transform 0.5s';
                observer.observe(el);
            });
            
            const planets = document.querySelectorAll('.planet');
            
            planets.forEach(planet => {
                planet.addEventListener('click', function() {
                    const altText = this.alt;
                    alert('Planet Info: ' + altText);
                });
            });
            
            const ctaButton = document.querySelector('.cta-button');
            const contactForm = document.querySelector('.contact-form-section');
            
            if (ctaButton && contactForm) {
                ctaButton.addEventListener('click', function() {
                    contactForm.scrollIntoView({ behavior: 'smooth' });
                });
            }
        });
    </script>
</body>
</html>
