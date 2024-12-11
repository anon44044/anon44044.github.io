# anon44044.github.io
Shtimp-guide.html 
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced Shrimp Keeper's Guide</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        /* Previous styles remain + new additions */
        :root {
            --primary-color: #006494;
            --secondary-color: #1B98E0;
            --accent-color: #E8F1F2;
            --text-color: #13293D;
            --light-text: #E8F1F2;
            --success-color: #4CAF50;
            --warning-color: #FFC107;
            --danger-color: #FF5722;
        }

        /* Tab System */
        .tab-container {
            margin: 2rem 0;
        }

        .tabs {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }

        .tab {
            padding: 0.75rem 1.5rem;
            background: var(--accent-color);
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .tab.active {
            background: var(--primary-color);
            color: white;
        }

        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .tab-content.active {
            display: block;
        }

        /* Grade System */
        .grade-card {
            background: white;
            border-radius: 12px;
            padding: 1.5rem;
            margin: 1rem 0;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        }

        .grade-indicator {
            display: inline-block;
            padding: 0.25rem 1rem;
            border-radius: 20px;
            margin: 0.25rem;
            font-weight: 500;
        }

        .grade-sss { background: #FFD700; color: #000; }
        .grade-ss { background: #C0C0C0; color: #000; }
        .grade-s { background: #CD7F32; color: #fff; }

        /* Parameter Slider */
        .parameter-slider {
            position: relative;
            height: 40px;
            background: #f0f0f0;
            border-radius: 20px;
            margin: 1rem 0;
        }

        .parameter-range {
            position: absolute;
            height: 100%;
            background: var(--primary-color);
            opacity: 0.3;
            border-radius: 20px;
        }

        .parameter-labels {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 1rem;
            color: var(--text-color);
            font-weight: 500;
        }

        /* Breeding Chart */
        .breeding-chart {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin: 1rem 0;
        }

        .breeding-result {
            background: white;
            border-radius: 12px;
            padding: 1rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .breeding-result img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 8px;
        }

        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Quick Reference */
        .quick-reference {
            position: fixed;
            right: 2rem;
            top: 50%;
            transform: translateY(-50%);
            background: white;
            padding: 1rem;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            max-width: 250px;
            display: none;
        }

        @media (min-width: 1400px) {
            .quick-reference {
                display: block;
            }
        }

        /* Care Guide Cards */
        .care-guide {
            background: white;
            border-radius: 12px;
            padding: 1.5rem;
            margin: 1rem 0;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        }

        .care-guide h4 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .parameter-tag {
            display: inline-block;
            padding: 0.25rem 0.75rem;
            border-radius: 15px;
            background: var(--accent-color);
            margin: 0.25rem;
            font-size: 0.875rem;
        }

        /* New Species Card Design */
        .species-card {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
        }

        .species-info {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .species-parameters {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.5rem;
        }

        .parameter-item {
            background: var(--accent-color);
            padding: 0.5rem;
            border-radius: 8px;
            text-align: center;
        }

        .parameter-value {
            font-weight: bold;
            color: var(--primary-color);
        }

    </style>
</head>
<body>
    <!-- Navigation remains the same -->
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">
                <i class="fas fa-water"></i>
                Advanced Shrimp Guide
            </div>
            <div class="nav-links">
                <a href="#species"><i class="fas fa-fish"></i> Species</a>
                <a href="#breeding"><i class="fas fa-baby"></i> Breeding</a>
                <a href="#parameters"><i class="fas fa-chart-line"></i> Parameters</a>
                <a href="#grading"><i class="fas fa-award"></i> Grading</a>
                <a href="#care"><i class="fas fa-heart"></i> Care</a>
            </div>
        </div>
    </nav>

    <div class="container">
        <div class="tab-container">
            <div class="tabs">
                <button class="tab active" data-tab="neocaridina">Neocaridina</button>
                <button class="tab" data-tab="caridina">Caridina</button>
                <button class="tab" data-tab="breeding">Breeding</button>
                <button class="tab" data-tab="grading">Grading</button>
            </div>

            <!-- Neocaridina Tab -->
            <div class="tab-content active" id="neocaridina">
                <h2>Neocaridina Varieties</h2>
                <div class="species-grid">
                    <!-- Red Variations -->
                    <div class="species-card">
                        <span class="care-level beginner">Beginner</span>
                        <div class="species-info">
                            <h3>Red Variations</h3>
                            <p><strong>Types:</strong></p>
                            <div class="grade-indicators">
                                <span class="grade-indicator grade-sss">Painted Fire Red</span>
                                <span class="grade-indicator grade-ss">Fire Red</span>
                                <span class="grade-indicator grade-s">Sakura</span>
                                <span class="grade-indicator">Cherry</span>
                            </div>
                        </div>
                        <div class="species-parameters">
                            <div class="parameter-item">
                                <div>Temperature</div>
                                <div class="parameter-value">65-85°F</div>
                            </div>
                            <div class="parameter-item">
                                <div>pH</div>
                                <div class="parameter-value">6.5-7.5</div>
                            </div>
                            <div class="parameter-item">
                                <div>GH</div>
                                <div class="parameter-value">6-8</div>
                            </div>
                            <div class="parameter-item">
                                <div>KH</div>
                                <div class="parameter-value">4-6</div>
                            </div>
                        </div>
                    </div>

                    <!-- Blue Variations -->
                    <div class="species-card">
                        <span class="care-level beginner">Beginner</span>
                        <div class="species-info">
                            <h3>Blue Variations</h3>
                            <p><strong>Types:</strong></p>
                            <div class="grade-indicators">
                                <span class="grade-indicator grade-sss">Blue Dream</span>
                                <span class="grade-indicator grade-ss">Blue Velvet</span>
                                <span class="grade-indicator grade-s">Blue Jelly</span>
                                <span class="grade-indicator">Carbon Rili</span>
                            </div>
                        </div>
                        <div class="species-parameters">
                            <!-- Same parameters as Red -->
                        </div>
                    </div>

                    <!-- Yellow Variations -->
                    <div class="species-card">
                        <span class="care-level beginner">Beginner</span>
                        <div class="species-info">
                            <h3>Yellow Variations</h3>
                            <p><strong>Types:</strong></p>
                            <div class="grade-indicators">
                                <span class="grade-indicator grade-sss">Yellow Fire</span>
                                <span class="grade-indicator grade-ss">Golden Back</span>
                                <span class="grade-indicator grade-s">Yellow</span>
                            </div>
                        </div>
                        <div class="species-parameters">
                            <!-- Same parameters as Red -->
                        </div>
                    </div>
                </div>
            </div>

            <!-- More tabs to follow in Part 2 -->
        </div>
    </div>

    <script>
        // Tab System
        document.querySelectorAll('.tab').forEach(tab => {
            tab.addEventListener('click', () => {
                // Remove active class from all tabs
                document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
                document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
                
                // Add active class to clicked tab
                tab.classList.add('active');
                document.querySelector(`#${tab.dataset.tab}`).classList.add('active');
            });
        });
    </script>
</body>
</html>
