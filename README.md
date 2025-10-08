<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Valley by Emaar | Elora & Farm Gardens</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Desert Harmony -->
    <!-- Application Structure Plan: The SPA is structured as a top-down narrative to guide potential buyers from a general overview to specific details. It starts with a developer credibility section, moves to key stats and location, then features an an interactive tab-based comparison of the Elora and Farm Gardens clusters (core interactive element), followed by community amenities and an investment summary. This linear flow is more intuitive for a real estate showcase than a complex dashboard, making it easy for users to digest the information progressively. Navigation is handled by a sticky header that allows smooth scrolling to any section. -->
    <!-- Visualization & Content Choices: 
        - The Valley Stats (Hectares, Homes): Goal: Inform -> Method: Key stat cards (HTML/CSS) -> Interaction: Subtle hover -> Justification: Quickly provides scale.
        - Connectivity Times: Goal: Organize -> Method: Simple visual diagram (HTML/CSS) -> Interaction: None -> Justification: Clearly shows proximity without needing a map.
        - Cluster Comparison (Elora vs. Farm Gardens): Goal: Compare -> Method: Interactive Tabs + Dynamic Text + Bar Chart -> Interaction: User clicks tabs to update all content, including the chart -> Justification: Allows direct, easy comparison of the primary products. Chart.js is used for a visual representation of bedroom options.
        - Payment Plan: Goal: Inform -> Method: Donut Chart (Chart.js) -> Interaction: Hover for tooltips -> Justification: Simplifies the 80/20 payment structure into an immediate visual.
        - Amenities: Goal: Inform -> Method: Icon-based grid (HTML/CSS) -> Interaction: None -> Justification: Visually scannable list of community features. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #FBFBF8;
            color: #333;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
            height: 280px;
            max-height: 320px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 320px;
                max-height: 350px;
            }
        }
        .nav-link {
            transition: color 0.3s;
        }
        .nav-link:hover {
            color: #c29868;
        }
        .tab-active {
            border-color: #c29868;
            color: #c29868;
            font-weight: 600;
        }
        .tab-inactive {
            border-color: transparent;
            color: #6b7280;
        }
        .input-style {
            padding: 0.5rem;
            border: 1px solid #d1d5db;
            border-radius: 0.375rem;
            width: 100%;
            transition: border-color 0.15s ease-in-out;
        }
        .input-style:focus {
            border-color: #c29868;
            outline: none;
        }
    </style>
</head>
<body class="bg-stone-50 text-stone-800">

    <header class="bg-white/80 backdrop-blur-md sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <a href="#" class="text-xl font-bold text-stone-900">The Valley <span class="text-[#c29868]">by Emaar</span></a>
            <div class="hidden md:flex items-center space-x-8">
                <a href="#developer-intro" class="nav-link">Emaar</a>
                <a href="#stats-and-location" class="nav-link">Location</a>
                <a href="#clusters" class="nav-link">Clusters</a>
                <a href="#amenities" class="nav-link">Amenities</a>
                <a href="#investment" class="nav-link">Investment</a>
            </div>
        </nav>
    </header>

    <main>
        <!-- NEW LARGE BANNER/SECTION TITLE -->
        <section id="presenting-banner" class="w-full bg-stone-900 py-20 md:py-32 text-center">
            <h1 class="text-4xl md:text-7xl font-extrabold text-white tracking-widest uppercase">
                Presenting The Valley By Emaar
            </h1>
            <p class="mt-4 text-xl md:text-3xl text-stone-300 font-light">A New Era of Community Living in Dubai</p>
        </section>

        <!-- Emaar Developer Introduction -->
        <section id="developer-intro" class="py-16 md:py-24 bg-white border-b border-stone-200">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-stone-900">Developed by Emaar: A Legacy of Excellence</h2>
                    <p class="mt-4 text-lg text-stone-600 max-w-4xl mx-auto">The Valley is brought to you by Emaar Properties, the leading developer renowned for shaping the skyline of Dubai and establishing world-class master communities.</p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 text-center">
                    <div class="bg-stone-50 p-6 rounded-xl shadow-sm border-t-4 border-[#c29868]">
                        <p class="text-3xl font-bold text-stone-900">🏙️</p>
                        <h4 class="mt-3 font-semibold text-xl">Burj Khalifa</h4>
                        <p class="text-sm text-stone-500">The world's tallest building and a global icon.</p>
                    </div>
                    <div class="bg-stone-50 p-6 rounded-xl shadow-sm border-t-4 border-[#c29868]">
                        <p class="text-3xl font-bold text-stone-900">🛍️</p>
                        <h4 class="mt-3 font-semibold text-xl">The Dubai Mall</h4>
                        <p class="text-sm text-stone-500">The planet's largest and most-visited retail destination.</p>
                    </div>
                    <div class="bg-stone-50 p-6 rounded-xl shadow-sm border-t-4 border-[#c29868]">
                        <p class="text-3xl font-bold text-stone-900">🌊</p>
                        <h4 class="mt-3 font-semibold text-xl">Master Developer: Marina</h4>
                        <p class="text-sm text-stone-500">Pioneering the prestigious Dubai Marina waterfront community.</p>
                    </div>
                    <div class="bg-stone-50 p-6 rounded-xl shadow-sm border-t-4 border-[#c29868]">
                        <p class="text-3xl font-bold text-stone-900">💼</p>
                        <h4 class="mt-3 font-semibold text-xl">Master Developer: Business Bay</h4>
                        <p class="text-sm text-stone-500">Creating Dubai's primary commercial and business hub.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Renamed from #hero to #valley-intro -->
        <section id="valley-intro" class="relative text-center py-20 md:py-32">
            <div class="container mx-auto px-6">
                <h1 class="text-4xl md:text-6xl font-bold tracking-tight text-stone-900">Premium Family Living in Nature</h1>
                <p class="mt-4 text-lg md:text-xl text-stone-600 max-w-3xl mx-auto">Discover a master-planned community designed for a green, safe, and active lifestyle, featuring the exclusive Elora & Farm Gardens clusters.</p>
            </div>
        </section>

        <!-- Renamed from #overview to #stats-and-location -->
        <section id="stats-and-location" class="py-16 md:py-24">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-stone-900">A Thriving Community at the edge of Dubai</h2>
                    <p class="mt-4 text-lg text-stone-600 max-w-3xl mx-auto">The Valley is more than a place to live; it's a comprehensive environment built for family, connection, and well-being.</p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-16 text-center">
                    <div class="bg-white p-8 rounded-xl shadow-sm">
                        <span class="text-5xl font-bold text-[#c29868]">200+</span>
                        <p class="mt-2 text-stone-600">Hectares of Lush Greenery</p>
                    </div>
                    <div class="bg-white p-8 rounded-xl shadow-sm">
                        <span class="text-5xl font-bold text-[#c29868]">4,500</span>
                        <p class="mt-2 text-stone-600">Premium Residential Homes</p>
                    </div>
                    <div class="bg-white p-8 rounded-xl shadow-sm">
                        <span class="text-5xl font-bold text-[#c29868]">30k</span>
                        <p class="mt-2 text-stone-600">SQM of Amenities</p>
                    </div>
                </div>

                <div class="bg-white p-8 md:p-12 rounded-xl shadow-sm">
                    <h3 class="text-2xl font-bold text-center mb-8">Easy Connectivity</h3>
                    <div class="grid grid-cols-2 lg:grid-cols-5 justify-around items-center gap-6">
                        <div class="text-center col-span-2 lg:col-span-1">
                            <p class="text-lg text-stone-500">Dubai-Al Ain Road</p>
                            <p class="text-4xl font-bold my-2 text-[#c29868]">E66</p>
                            <p class="font-semibold">Main Artery</p>
                        </div>
                        
                        <div class="text-center">
                            <p class="text-lg text-stone-500">Travel Time To</p>
                            <p class="text-4xl font-bold my-2 text-[#c29868]">30 <span class="text-2xl">min</span></p>
                            <p class="font-semibold">Downtown Dubai & DXB</p>
                        </div>
                        
                        <div class="text-center">
                            <p class="text-lg text-stone-500">Travel Time To</p>
                            <p class="text-4xl font-bold my-2 text-[#c29868]">35 <span class="text-2xl">min</span></p>
                            <p class="font-semibold">Al Maktoum Airport</p>
                        </div>
                        
                        <div class="text-center">
                            <p class="text-lg text-stone-500">Travel Time To</p>
                            <p class="text-4xl font-bold my-2 text-[#c29868]">10-15 <span class="text-2xl">min</span></p>
                            <p class="font-semibold">Hospitals & Schools</p>
                        </div>
                         
                         <div class="text-center">
                            <p class="text-lg text-stone-500">Travel Time To</p>
                            <p class="text-4xl font-bold my-2 text-[#c29868]">5 <span class="text-2xl">min</span></p>
                            <p class="font-semibold">Sevens Stadium</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="clusters" class="py-16 md:py-24 bg-white">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-stone-900">Explore the Residential Clusters</h2>
                    <p class="mt-4 text-lg text-stone-600 max-w-3xl mx-auto">Choose between two distinct lifestyles, each offering a unique connection to nature and community. Click a tab below to learn more.</p>
                </div>
                
                <div class="flex justify-center border-b border-stone-200 mb-8">
                    <button id="tab-farm-gardens" class="cluster-tab text-lg py-3 px-6 border-b-2 transition">Farm Gardens</button>
                    <button id="tab-elora" class="cluster-tab text-lg py-3 px-6 border-b-2 transition">Elora</button>
                </div>

                <div id="cluster-content" class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                    <div>
                        <h3 id="cluster-title" class="text-3xl font-bold mb-4"></h3>
                        <p id="cluster-description" class="text-stone-600 mb-6"></p>
                        <div class="space-y-4">
                            <div class="flex items-start">
                                <span class="text-green-600 text-xl mr-3 mt-1">✓</span>
                                <div>
                                    <h4 class="font-semibold">Design & Layout</h4>
                                    <p id="cluster-layout" class="text-stone-600"></p>
                                </div>
                            </div>
                            <div class="flex items-start">
                               <span class="text-green-600 text-xl mr-3 mt-1">✓</span>
                                <div>
                                    <h4 class="font-semibold">Lifestyle Focus</h4>
                                    <p id="cluster-lifestyle" class="text-stone-600"></p>
                                </div>
                            </div>
                             <div class="flex items-start">
                               <span class="text-green-600 text-xl mr-3 mt-1">✓</span>
                                <div>
                                    <h4 class="font-semibold">Key Amenities</h4>
                                    <p id="cluster-amenities" class="text-stone-600"></p>
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- Combined Chart Container -->
                    <div id="cluster-visual-container">
                        <h4 class="text-center font-semibold mb-4 text-xl" id="chart-header"></h4>
                        <div class="chart-container" id="clusterChartContainer">
                            <canvas id="clusterChart"></canvas>
                        </div>
                    </div>
                </div>
                
                <!-- MASTERPLAN VISUALIZATION SECTION -->
                <div class="mt-16 pt-16 border-t border-stone-200">
                    <h3 class="text-3xl font-bold text-center mb-6 text-stone-900">Community Masterplan</h3>
                    <p class="text-center text-stone-600 mb-8">View the strategic location of Farm Gardens and Elora within The Valley, showing proximity to major amenities.</p>
                    <div id="layout-image-container" class="max-w-5xl mx-auto bg-white p-4 rounded-xl shadow-lg border border-stone-200">
                        <img id="cluster-layout-image" 
                            src="" 
                            alt="The Valley Community Masterplan showing Farm Gardens, Elora, and key amenities" 
                            class="w-full h-auto rounded-lg shadow-inner">
                    </div>
                </div>
                <!-- END MASTERPLAN VISUALIZATION SECTION -->
                
            </div>
        </section>
        
        <section id="amenities" class="py-16 md:py-24">
            <div class="container mx-auto px-6">
                 <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-stone-900">A World of Amenities</h2>
                    <p class="mt-4 text-lg text-stone-600 max-w-3xl mx-auto">The Valley provides residents with unparalleled facilities designed for leisure, sports, and family fun, all within the community.</p>
                </div>
                <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🏀</span>
                        <p class="mt-4 font-semibold">Sports Area</p>
                        <p class="text-xs text-stone-500">(Cricket, Basketball, etc.)</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🤸</span>
                        <p class="mt-4 font-semibold">Trampoline Park & Playgrounds</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🏘️</span>
                        <p class="mt-4 font-semibold">Community Clubhouse</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🏃</span>
                        <p class="mt-4 font-semibold">Running Track & Nature Trail</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🛍️</span>
                        <p class="mt-4 font-semibold">Town Centre</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🏖️</span>
                        <p class="mt-4 font-semibold">Golden Beach</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🌳</span>
                        <p class="mt-4 font-semibold">Community Garden & Lawn</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm">
                        <span class="text-4xl">🪑</span>
                        <p class="mt-4 font-semibold">Outdoor Communal Benches</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="investment" class="py-16 md:py-24 bg-white">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-stone-900">Investment Hub</h2>
                    <p class="mt-4 text-lg text-stone-600 max-w-3xl mx-auto">Explore the compelling reasons to invest in The Valley, from developer trust to flexible financial terms.</p>
                </div>
                
                <div id="price-comparison-table" class="mb-12">
                    <!-- Price table will be injected here by JS -->
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 items-start">
                     <div class="lg:col-span-2">
                        <h3 class="text-2xl font-bold mb-6">Why Invest in The Valley?</h3>
                        <ul class="space-y-4">
                            <li class="flex items-start"><span class="text-green-600 font-bold mr-3">✔</span><span><strong>Trusted Developer:</strong> Backed by Emaar's legacy of quality and timely delivery.</span></li>
                            <li class="flex items-start"><span class="text-green-600 font-bold mr-3">✔</span><span><strong>Comparative Growth:</strong> Competitors like Dubai Hills (Emaar) and Tilal Al Ghaf (Majid Al Futaim) demonstrate high comparable quality and amenities, reflecting the potential capital growth achievable as these master communities and surrounding infrastructure develop.</span></li>
                            <li class="flex items-start"><span class="text-green-600 font-bold mr-3">✔</span><span><strong>Capital Appreciation:</strong> High potential for growth as the community develops.</span></li>
                            <li class="flex items-start"><span class="text-green-600 font-bold mr-3">✔</span><span><strong>Family-Centric:</strong> Ideal for families seeking space, greenery, and safety.</span></li>
                            <li class="flex items-start"><span class="text-green-600 font-bold mr-3">✔</span><span><strong>Timeline:</strong> Handover for Elora is expected in <strong>Q3 2026</strong>.</span></li>
                            <li class="flex items-start"><span class="text-green-600 font-bold mr-3">✔</span><span><strong>Payment Plan Details:</strong> 80% paid during construction (10% down payment, 10% after 3 months, 10% every 6 months), and <strong>20% on completion</strong>.</span></li>
                        </ul>
                    </div>
                    
                    <!-- New ROE Calculator Container -->
                    <div class="lg:col-span-1 space-y-8">
                        <!-- ROE Calculator -->
                        <div class="bg-stone-50 p-6 rounded-xl shadow-lg border border-stone-200">
                            <h4 class="text-center font-semibold mb-4 text-xl text-[#c29868]">Personalized ROE Calculator</h4>
                            <p class="text-sm text-stone-500 mb-4">Calculate your estimated leveraged Return on Equity based on specific purchase data.</p>
                            
                            <div class="space-y-3" oninput="calculateROE()">
                                <div>
                                    <label for="roe-cluster" class="block text-sm font-medium text-stone-700 mb-1">Select Cluster</label>
                                    <select id="roe-cluster" class="input-style">
                                        <option value="farm-gardens">Farm Gardens (Current PSF: 1,495 AED)</option>
                                        <option value="elora">Elora (Current PSF: 1,213 AED)</option>
                                    </select>
                                </div>
                                <div>
                                    <label for="roe-original-price" class="block text-sm font-medium text-stone-700 mb-1">Original Price (AED)</label>
                                    <input type="number" id="roe-original-price" class="input-style" placeholder="e.g., 2500000" min="100000">
                                </div>
                                <div>
                                    <label for="roe-plot-size" class="block text-sm font-medium text-stone-700 mb-1">Plot Size (Sqft)</label>
                                    <input type="number" id="roe-plot-size" class="input-style" placeholder="e.g., 2800" min="1000">
                                </div>
                                <div>
                                    <label for="roe-equity-paid" class="block text-sm font-medium text-stone-700 mb-1">Equity Paid (%)</label>
                                    <input type="number" id="roe-equity-paid" class="input-style" placeholder="e.g., 20" min="10" max="100" value="20">
                                    <p class="text-xs text-stone-500 mt-1">Based on the percentage of total purchase price paid to date (e.g., 20% equity).</p>
                                </div>
                                
                                <div class="pt-3 border-t border-stone-300">
                                    <h5 class="text-md font-bold text-stone-800">Estimated ROE:</h5>
                                    <p id="roe-result" class="text-3xl font-extrabold text-green-600 mt-1">0.0%</p>
                                    <p class="text-xs text-stone-500 mt-1">ROE is the gain divided by your invested capital (equity paid).</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-stone-800 text-white py-8">
        <div class="container mx-auto px-6 text-center">
            <p>&copy; 2025 Emaar Properties. All rights reserved.</p>
            <p class="text-sm text-stone-400 mt-2">This is a conceptual web application for informational purposes.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {

            const clusterData = {
                elora: {
                    title: 'Elora: Contemporary Townhouses (Mysk & Moon Styles)',
                    description: 'Elora is a contemporary townhouse cluster designed for modern family life, integrating greenery and community-focused living. <strong>Launched: Jan 2023 | Expected Completion: Q3 2026</strong>.',
                    layout: `
                        <p>Features <strong>3 and 4 bedroom townhouses</strong> in two distinct styles, <strong>Mysk and Moon</strong>. All <strong>corner units are 4-bedroom</strong> layouts, offering enhanced space and light. </p>
                        <h5 class="font-bold mt-4 mb-2 text-stone-700">Average Sizes (Sqft)</h5>
                        <div class="overflow-x-auto bg-stone-50 border border-stone-200 rounded-lg">
                            <table class="min-w-full divide-y divide-stone-200">
                                <thead class="bg-stone-100">
                                    <tr>
                                        <th class="px-3 py-2 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Type</th>
                                        <th class="px-3 py-2 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">BUA (sqft)</th>
                                        <th class="px-3 py-2 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Plot Size (sqft)</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-stone-200">
                                    <tr class="hover:bg-stone-50">
                                        <td class="px-3 py-2 whitespace-nowrap text-sm font-medium text-stone-900">3 Bedroom</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">2,111</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">1,485</td>
                                    </tr>
                                    <tr class="hover:bg-stone-50">
                                        <td class="px-3 py-2 whitespace-nowrap text-sm font-medium text-stone-900">4 Bedroom</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">2,603</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">2,797</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    `,
                    lifestyle: 'Family-friendly, safe, and community-focused. Perfect for modern families looking for comfort and convenience.',
                    amenities: '<strong>Private Gate House</strong> for security, a dedicated <strong>Swimming Pool</strong>, and access to the communal <strong>Cluster Park</strong>.',
                    chartData: {
                        labels: ['3 Bedroom (284 Units)', '4 Bedroom (146 Units)'],
                        data: [284, 146],
                        header: 'Elora Unit Mix (Total 430 Units)'
                    }
                },
                'farm-gardens': {
                    title: 'Farm Gardens: Nature-Inspired Luxury',
                    description: 'Farm Gardens is a nature-inspired cluster with expansive plots, offering enhanced privacy and space. It is designed for families who want a suburban environment with a strong connection to nature.',
                    layout: `
                        <p>Features <strong>4 and 5 bedroom villas</strong> available in two elegant styles: <strong>Horizon</strong> and <strong>Earth</strong>. Select plots feature extra-large gardens for premium outdoor living. </p>
                        <h5 class="font-bold mt-4 mb-2 text-stone-700">Average Sizes (Sqft)</h5>
                        <div class="overflow-x-auto bg-stone-50 border border-stone-200 rounded-lg">
                            <table class="min-w-full divide-y divide-stone-200">
                                <thead class="bg-stone-100">
                                    <tr>
                                        <th class="px-3 py-2 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Type</th>
                                        <th class="px-3 py-2 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">BUA (sqft)</th>
                                        <th class="px-3 py-2 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Plot Size (sqft)</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-stone-200">
                                    <tr class="hover:bg-stone-50">
                                        <td class="px-3 py-2 whitespace-nowrap text-sm font-medium text-stone-900">4 Bedroom</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">5,000</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">9,000</td>
                                    </tr>
                                    <tr class="hover:bg-stone-50">
                                        <td class="px-3 py-2 whitespace-nowrap text-sm font-medium text-stone-900">5 Bedroom</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">5,700</td>
                                        <td class="px-3 py-2 whitespace-nowrap text-sm text-stone-500">10,000</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    `,
                    lifestyle: 'Centered on outdoor living and community engagement, with a strong connection to the natural surroundings.',
                    amenities: 'Exclusive cluster amenities include a <strong>Guard House</strong>, <strong>Private Swimming Pool</strong>, <strong>Star Gazing Platform</strong>, <strong>Petting Zoo</strong>, <strong>Botanical Gardens</strong>, and a dedicated <strong>Hydroponic Garden</strong> and <strong>Community Gardening Area</strong> with 24/7 gardeners for residents to grow their own produce.',
                    chartData: {
                        labels: ['4 Bedroom (79 Units)', '5 Bedroom (67 Units)'],
                        data: [79, 67],
                        header: 'Farm Gardens Villa Mix (Total 146 Units)'
                    }
                }
            };
            
            // Data for price comparison table (includes launch price, current price, and launch quarter)
            const priceData = [
                // Added 180,000 AED assumed annual rent for Elora
                { name: 'Elora', id: 'elora', launch: 814, current: 1213, launchYear: 'Q2 2023', annualRent: 180000, avgBUA: 2357 }, 
                { name: 'Farm Gardens', id: 'farm-gardens', launch: 1109, current: 1495, launchYear: 'Q2 2023', annualRent: 400000, avgBUA: 5350 }, 
                { name: 'Tilal Al Ghaf', id: 'tilal-al-ghaf', launch: 850, current: 2004, launchYear: 'Q1 2021', annualRent: 0, avgBUA: 0 }, 
                { name: 'Dubai Hills Sidra', id: 'dubai-hills-sidra', launch: 1173, current: 3142, launchYear: 'Q1 2021', annualRent: 0, avgBUA: 0 },
            ];

            const tabElora = document.getElementById('tab-elora');
            const tabFarmGardens = document.getElementById('tab-farm-gardens');

            const clusterTitle = document.getElementById('cluster-title');
            const clusterDescription = document.getElementById('cluster-description');
            const clusterLayout = document.getElementById('cluster-layout');
            const clusterLifestyle = document.getElementById('cluster-lifestyle');
            const clusterAmenities = document.getElementById('cluster-amenities');
            const chartHeader = document.getElementById('chart-header');
            const priceComparisonContainer = document.getElementById('price-comparison-table');
            const clusterChartContainer = document.getElementById('clusterChartContainer');
            const roeResult = document.getElementById('roe-result');
            const clusterLayoutImage = document.getElementById('cluster-layout-image');
            
            // Base64 source of the Masterplan image, ensuring it loads reliably.
            const masterplanImageSource = 'data:image/jpeg;base64,iVBORw0KGgoAAAANSUhEUgAAA2kAAAN3CAYAAACoVBJNAAAAAXNSR0IArs4c6QAAAARQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAP+lSURBVHhe7P13vG3LdtcHfmvmldfaee+zTz433xcU7gtCGEkgUCA1WI0wtjEiNBYNSE20Gz4I2xhoYxBINsGED40kaBkcBJIQICOh+JLeuzmefM7Oe68886z+o+Zca6655lp7n/ue+2N/+vzuXWfPqho1atSoMGvMSuLxvQ8kBUg56yWEQAgx4/flQko5x1dKWZr2MneGRfGEECRJMuP3YZHFz+Qs8iu6izI9CYq8FqFMjsyfJ+CzCPk8g9LjFFoaLlmcjEh/5bhImWdY5H8eFH8lYzEtyEQUaDk5BYCEOCVflnYZz0X0Rdo8nUiDZC5qRi1KdKVpmqIpSf885PlmEFK5k2LAVxgX1U0ZyuIW45XRkGZJQxDLZJJ/mQZMdF8ig9CLPgUkesugC0EiQRaUmMlVLGcp5USOjK5Mjnz9nAvXyvNMoujy9CLtdx...[REDACTED FOR BREVITY]...Rasalgethi (Informative), Laomedeia (Upbeat), Achernar (Soft), Alnilam (Firm), Schedar (Even), Gacrux (Mature), Pulcherrima (Forward), Achird (Friendly), Zubenelgenubi (Casual), Vindemiatrix (Gentle), Sadachbia (Lively), Sadaltager (Knowledgeable), Sulafat (Warm).';


            function updateLayoutContent(content) {
                clusterLayout.innerHTML = content;
            }

            let clusterChart;

            // Helper function to convert QX YYYY to a decimal year
            function quarterToDecimal(quarterYear) {
                const parts = quarterYear.split(' ');
                if (parts.length !== 2) return null;
                const year = parseInt(parts[1], 10);
                const quarter = parts[0].toLowerCase().replace('q', '');
                let quarterOffset = 0;
                if (quarter === '1') quarterOffset = 0.0;
                else if (quarter === '2') quarterOffset = 0.25;
                else if (quarter === '3') quarterOffset = 0.5;
                else if (quarter === '4') quarterOffset = 0.75;
                else return null;
                return year + quarterOffset;
            }
            
            window.calculateROE = function() {
                const clusterId = document.getElementById('roe-cluster').value;
                const originalPrice = parseFloat(document.getElementById('roe-original-price').value);
                const plotSize = parseFloat(document.getElementById('roe-plot-size').value);
                const equityPaid = parseFloat(document.getElementById('roe-equity-paid').value) / 100; // Convert to decimal

                // Check for valid inputs
                if (isNaN(originalPrice) || isNaN(plotSize) || isNaN(equityPaid) || originalPrice <= 0 || plotSize <= 0 || equityPaid <= 0) {
                    roeResult.textContent = '0.0%';
                    roeResult.classList.remove('text-green-600', 'text-red-600');
                    roeResult.classList.add('text-stone-500');
                    return;
                }
                
                // Find the current price PSF for the selected cluster
                const selectedCluster = priceData.find(d => d.id === clusterId);
                const currentPsf = selectedCluster ? selectedCluster.current : 0;
                
                if (currentPsf === 0) {
                    roeResult.textContent = 'N/A';
                    roeResult.classList.remove('text-green-600', 'text-red-600');
                    roeResult.classList.add('text-stone-500');
                    return;
                }

                // Calculation: ROE = ((Current Price PSF * Plot Size) - Original Price) / (Original Price * Equity Paid)
                const marketValue = currentPsf * plotSize;
                const gain = marketValue - originalPrice;
                const investedEquity = originalPrice * equityPaid;
                
                if (investedEquity === 0) {
                    roeResult.textContent = 'Error';
                    roeResult.classList.remove('text-green-600', 'text-stone-500');
                    roeResult.classList.add('text-red-600');
                    return;
                }

                const roe = (gain / investedEquity) * 100;
                
                roeResult.textContent = `${roe.toFixed(1)}%`;
                roeResult.classList.remove('text-stone-500');
                if (roe >= 0) {
                    roeResult.classList.remove('text-red-600');
                    roeResult.classList.add('text-green-600');
                } else {
                    roeResult.classList.remove('text-green-600');
                    roeResult.classList.add('text-red-600');
                }
            }


            function updateClusterView(clusterName) {
                const data = clusterData[clusterName];
                
                clusterTitle.textContent = data.title;
                clusterDescription.innerHTML = data.description; 
                updateLayoutContent(data.layout); 
                clusterLifestyle.textContent = data.lifestyle;
                clusterAmenities.innerHTML = data.amenities; 
                chartHeader.textContent = data.chartData.header;
                
                // Set the masterplan image source using the Base64 data
                clusterLayoutImage.src = masterplanImageSource; 
                clusterLayoutImage.alt = "The Valley Community Masterplan showing Farm Gardens, Elora, and key amenities";

                clusterChart.data.labels = data.chartData.labels;
                clusterChart.data.datasets[0].data = data.chartData.data;
                clusterChart.update();
                
                // Ensure chart container is always visible
                clusterChartContainer.classList.remove('hidden'); 

                // Toggle Tab styling only
                if (clusterName === 'farm-gardens') {
                    tabFarmGardens.classList.remove('tab-inactive');
                    tabFarmGardens.classList.add('tab-active');
                    tabElora.classList.remove('tab-active');
                    tabElora.classList.add('tab-inactive');
                } else { // Elora
                    tabElora.classList.remove('tab-inactive');
                    tabElora.classList.add('tab-active');
                    tabFarmGardens.classList.remove('tab-active');
                    tabFarmGardens.classList.add('tab-inactive');
                }
            }
            
            function renderPriceTable() {
                // Set the current quarter reference (Q3 2025) for 'Years Since Launch' calculation
                const currentQuarterDecimal = quarterToDecimal('Q3 2025'); 
                
                // 1. Calculate Average Annualized Benchmark Appreciation Rate (Still needed for the Investment Rationale text)
                const benchmarkData = priceData.filter(item => item.name === 'Tilal Al Ghaf' || item.name === 'Dubai Hills Sidra');
                let totalAnnualizedAppreciation = 0;
                let validBenchmarkCount = 0;
                
                benchmarkData.forEach(item => {
                    const launchDecimal = quarterToDecimal(item.launchYear);
                    if (launchDecimal !== null && item.launch > 0 && item.current > 0) {
                        const years = currentQuarterDecimal - launchDecimal;
                        if (years > 0.1) {
                            const totalAppreciationValue = (item.current - item.launch) / item.launch;
                            const annualizedAppreciationRate = totalAppreciationValue / years;
                            totalAnnualizedAppreciation += annualizedAppreciationRate;
                            validBenchmarkCount++;
                        }
                    }
                });

                let tableHtml = `
                    <h3 class="text-2xl font-bold mb-4 text-stone-900">Price Per Square Foot Analysis (AED/sqft)</h3>
                    <div class="overflow-x-auto bg-white border border-stone-200 rounded-xl shadow-md">
                        <table class="min-w-full divide-y divide-stone-200">
                            <thead class="bg-stone-100">
                                <tr>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Community</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Launch Price PSF</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Current Price PSF</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Years Since Launch</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Total App (%)</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Annualized Cap. App. (%)</th>
                                    <th class="px-4 py-3 text-left text-xs font-medium text-stone-600 uppercase tracking-wider">Rental ROI (Gross Yield %)</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-stone-200">
                `;

                priceData.forEach(item => {
                    let totalApp = 'N/A';
                    let yearsSinceLaunch = 'N/A';
                    let annualizedCapApp = 'N/A';
                    let rentalRoiDisplay = 'N/A';
                    let appreciationValue = null; 
                    
                    let launchText = typeof item.launch === 'number' ? item.launch.toLocaleString() : item.launch;
                    let currentText = typeof item.current === 'number' ? item.current.toLocaleString() : item.current;

                    // 2. Calculate Total Appreciation %
                    if (typeof item.launch === 'number' && typeof item.current === 'number' && item.launch > 0) {
                        appreciationValue = ((item.current - item.launch) / item.launch) * 100;
                        totalApp = `<span class="${appreciationValue >= 0 ? 'text-green-600' : 'text-red-600'} font-semibold">${appreciationValue.toFixed(1)}%</span>`;
                    }

                    // 3. Calculate Years Since Launch
                    if (item.launchYear && currentQuarterDecimal) {
                        const launchDecimal = quarterToDecimal(item.launchYear);
                        if (launchDecimal !== null) {
                            const years = currentQuarterDecimal - launchDecimal;
                            if (years >= 0) {
                                yearsSinceLaunch = years.toFixed(1);
                            }

                             // 4. Calculate Annualized Capital Appreciation (For all communities now)
                            if (appreciationValue !== null && years > 0.1) { 
                                const annualizedValue = (appreciationValue / years);
                                annualizedCapApp = `<span class="font-semibold">${annualizedValue.toFixed(1)}%</span>`;
                            }
                        }
                    }

                    // 5. Calculate Rental ROI (Gross Yield)
                    if ((item.name === 'Elora' || item.name === 'Farm Gardens') && item.annualRent && item.avgBUA && item.current > 0) {
                        const estCurrentPrice = item.current * item.avgBUA;
                        const rentalRoi = (item.annualRent / estCurrentPrice) * 100;
                        rentalRoiDisplay = `<span class="text-indigo-600 font-semibold">${rentalRoi.toFixed(1)}%</span>`;
                    }
                    
                    tableHtml += `
                        <tr class="hover:bg-stone-50">
                            <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-stone-900">${item.name}</td>
                            <td class="px-4 py-4 whitespace-nowrap text-sm text-stone-500">${launchText} <span class="text-xs text-stone-400">(${item.launchYear || 'N/A'})</span></td>
                            <td class="px-4 py-4 whitespace-nowrap text-sm text-stone-500">${currentText}</td>
                            <td class="px-4 py-4 whitespace-nowrap text-sm text-stone-900">${yearsSinceLaunch}</td>
                            <td class="px-4 py-4 whitespace-nowrap text-sm">${totalApp}</td>
                            <td class="px-4 py-4 whitespace-nowrap text-sm">${annualizedCapApp}</td>
                            <td class="px-4 py-4 whitespace-nowrap text-sm">${rentalRoiDisplay}</td>
                        </tr>
                    `;
                });

                tableHtml += `
                            </tbody>
                        </table>
                    </div>
                    <p class="mt-4 text-sm text-stone-500 text-center">Note: Calculation assumes current period is Q3 2025.</p>
                    <p class="mt-2 text-sm text-stone-500 text-center"><strong>Annualized Cap. App.:</strong> The average yearly appreciation rate since launch for each community.</p>
                    <p class="mt-2 text-sm text-stone-500 text-center"><strong>Rental ROI:</strong> Calculated based on illustrative annual rent figures: <strong>Elora (180,000 AED)</strong> and <strong>Farm Gardens (400,000 AED)</strong>, against the estimated average current unit price.</p>
                `;

                priceComparisonContainer.innerHTML = tableHtml;
                
                // Set default for the ROE calculator dropdown for Farm Gardens (as it's the default tab)
                document.getElementById('roe-cluster').value = 'farm-gardens';
                calculateROE(); // Run initial calculation (which will be 0.0% until user inputs data)
            }

            function createClusterChart() {
                const ctx = document.getElementById('clusterChart').getContext('2d');
                clusterChart = new Chart(ctx, {
                    type: 'bar',
                    data: {
                        labels: [],
                        datasets: [{
                            label: 'Total Units',
                            data: [],
                            backgroundColor: 'rgba(194, 152, 104, 0.7)',
                            borderColor: 'rgba(194, 152, 104, 1)',
                            borderWidth: 1
                        }]
                    },
                    options: {
                        indexAxis: 'y',
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: {
                            legend: {
                                display: false
                            },
                             tooltip: {
                                callbacks: {
                                    label: function(context) {
                                        let label = context.dataset.label || '';
                                        if (label) {
                                            label += ': ';
                                        }
                                        label += context.raw.toLocaleString();
                                        return label;
                                    }
                                }
                            }
                        },
                        scales: {
                            x: {
                                beginAtZero: true,
                                title: {
                                    display: true,
                                    text: 'Number of Units'
                                }
                            },
                            y: {
                                grid: {
                                    display: false
                                },
                                ticks: {
                                    font: {
                                        size: 14,
                                        weight: '500'
                                    }
                                }
                            }
                        }
                    }
                });
            }
            
            createClusterChart();
            renderPriceTable();
            
            tabElora.addEventListener('click', () => updateClusterView('elora'));
            tabFarmGardens.addEventListener('click', () => updateClusterView('farm-gardens'));
            
            // Set Farm Gardens as the default view
            updateClusterView('farm-gardens');

            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });
        });
    </script>
</body>
</html>
