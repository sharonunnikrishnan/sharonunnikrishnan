w<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sharon Unnikrishnan | Laravel Developer</title>
    <link rel="icon" href="favicon.ico" type="image/x-icon">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        'inter': ['Inter', 'sans-serif'],
                        'poppins': ['Poppins', 'sans-serif'],
                        'montserrat': ['Montserrat', 'sans-serif'],
                    },
                    colors: {
                        primary: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            200: '#bae6fd',
                            300: '#7dd3fc',
                            400: '#38bdf8',
                            500: '#0ea5e9',
                            600: '#0284c7',
                            700: '#0369a1',
                            800: '#075985',
                            900: '#0c4a6e',
                        }
                    },
                    animation: {
                        'float': 'float 6s ease-in-out infinite',
                        'fadeIn': 'fadeIn 0.5s ease-in-out',
                        'slideIn': 'slideIn 0.8s ease-out',
                        'bounceIn': 'bounceIn 0.6s ease-out',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-10px)' },
                        },
                        fadeIn: {
                            '0%': { opacity: '0' },
                            '100%': { opacity: '1' },
                        },
                        slideIn: {
                            '0%': { transform: 'translateY(20px)', opacity: '0' },
                            '100%': { transform: 'translateY(0)', opacity: '1' },
                        },
                        bounceIn: {
                            '0%': { transform: 'scale(0.3)', opacity: '0' },
                            '50%': { transform: 'scale(1.05)' },
                            '70%': { transform: 'scale(0.9)' },
                            '100%': { transform: 'scale(1)', opacity: '1' },
                        }
                    }
                }
            }
        }
    </script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: var(--current-font, 'Inter'), sans-serif;
            transition: all 0.3s ease;
        }
        
        .gradient-bg {
            background: linear-gradient(-45deg, #1e3a8a, #7e22ce, #0ea5e9, #10b981);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }
        
        .light .gradient-bg {
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }
        
        @keyframes gradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }
        
        .glass-effect {
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .light .glass-effect {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .card-hover {
            transition: all 0.3s ease;
        }
        
        .card-hover:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }
        
        .light .card-hover:hover {
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        
        .skill-bar {
            height: 8px;
            border-radius: 4px;
            overflow: hidden;
            background-color: #374151;
        }
        
        .light .skill-bar {
            background-color: #e5e7eb;
        }
        
        .skill-progress {
            height: 100%;
            border-radius: 4px;
            transition: width 1.5s ease-in-out;
        }
        
        .theme-toggle {
            transition: all 0.3s ease;
        }
        
        .nav-link {
            position: relative;
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: #0ea5e9;
            transition: width 0.3s ease;
        }
        
        .nav-link:hover::after {
            width: 100%;
        }
        
        .section-title {
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            width: 60%;
            height: 3px;
            bottom: -8px;
            left: 0;
            background: linear-gradient(90deg, #0ea5e9, #7e22ce);
            border-radius: 2px;
        }
        
        .font-selector {
            transition: all 0.3s ease;
        }
        
        .font-selector:hover {
            transform: scale(1.05);
        }
        
        .back-to-top {
            transition: all 0.3s ease;
        }
        
        .back-to-top:hover {
            transform: translateY(-3px);
        }
        
        .settings-panel {
            transition: all 0.3s ease;
        }
        
        .chatbot-container {
            transition: all 0.3s ease;
        }
        
        .chat-message {
            animation: fadeIn 0.3s ease-in;
        }
        
        .user-message {
            border-radius: 18px 18px 4px 18px;
        }
        
        .bot-message {
            border-radius: 18px 18px 18px 4px;
        }
        
        .typing-indicator {
            display: inline-block;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: #9ca3af;
            margin: 0 2px;
            animation: typing 1.4s infinite ease-in-out;
        }
        
        .typing-indicator:nth-child(1) {
            animation-delay: 0s;
        }
        
        .typing-indicator:nth-child(2) {
            animation-delay: 0.2s;
        }
        
        .typing-indicator:nth-child(3) {
            animation-delay: 0.4s;
        }
        
        @keyframes typing {
            0%, 60%, 100% {
                transform: translateY(0);
            }
            30% {
                transform: translateY(-10px);
            }
        }
    </style>
</head>
<body class="dark bg-gray-900 text-gray-200 transition-colors duration-300 font-inter">
    <!-- Settings Panel -->
    <div id="settingsPanel" class="fixed bottom-6 right-6 z-40 flex flex-col md:flex-row items-end space-y-4 md:space-y-0 md:space-x-4 settings-panel">
        <!-- Back to Top Button -->
        <button id="backToTop" class="back-to-top w-12 h-12 rounded-full glass-effect flex items-center justify-center shadow-lg opacity-0 transition-opacity duration-300">
            <i class="fas fa-chevron-up text-primary-400"></i>
        </button>
        
        <!-- Font Selector -->
        <div class="flex flex-col items-end">
            <button id="fontToggle" class="w-12 h-12 rounded-full glass-effect flex items-center justify-center shadow-lg">
                <i class="fas fa-font text-primary-400"></i>
            </button>
            <div id="fontOptions" class="hidden glass-effect rounded-xl p-3 mb-2 shadow-lg">
                <div class="flex flex-col space-y-2">
                    <button data-font="inter" class="font-selector px-3 py-2 rounded-lg bg-primary-900 text-primary-200 text-sm font-inter">Inter</button>
                    <button data-font="poppins" class="font-selector px-3 py-2 rounded-lg bg-primary-900 text-primary-200 text-sm font-poppins">Poppins</button>
                    <button data-font="montserrat" class="font-selector px-3 py-2 rounded-lg bg-primary-900 text-primary-200 text-sm font-montserrat">Montserrat</button>
                </div>
            </div>
        </div>
        
        <!-- Theme Toggle -->
        <button id="themeToggle" class="theme-toggle w-12 h-12 rounded-full glass-effect flex items-center justify-center shadow-lg">
            <i class="fas fa-sun text-yellow-400 hidden dark:block"></i>
            <i class="fas fa-moon text-yellow-400 block dark:hidden"></i>
        </button>
        
        <!-- Chatbot Toggle -->
        <button id="chatbotToggle" class="w-12 h-12 rounded-full glass-effect flex items-center justify-center shadow-lg">
            <i class="fas fa-robot text-primary-400"></i>
        </button>
    </div>

    <!-- AI Chatbot -->
    <div id="chatbotContainer" class="fixed bottom-24 right-6 z-50 hidden chatbot-container">
        <div class="w-80 h-96 bg-gray-800 rounded-xl shadow-2xl flex flex-col">
            <!-- Chat Header -->
            <div class="bg-gray-900 rounded-t-xl p-4 flex justify-between items-center">
                <div class="flex items-center">
                    <div class="w-8 h-8 rounded-full bg-primary-500 flex items-center justify-center mr-2">
                        <i class="fas fa-robot text-white text-sm"></i>
                    </div>
                    <h3 class="font-semibold">Portfolio Assistant</h3>
                </div>
                <button id="closeChatbot" class="text-gray-400 hover:text-white">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <!-- Chat Messages -->
            <div id="chatMessages" class="flex-1 p-4 overflow-y-auto">
                <div class="bot-message bg-gray-700 p-3 max-w-xs mb-4 chat-message">
                    <p>Hello! I'm your portfolio assistant. How can I help you today?</p>
                </div>
                <div class="bot-message bg-gray-700 p-3 max-w-xs mb-4 chat-message">
                    <p>You can ask me about Sharon's skills, experience, projects, or how to contact him.</p>
                </div>
            </div>
            
            <!-- Chat Input -->
            <div class="p-4 border-t border-gray-700">
                <div class="flex">
                    <input type="text" id="chatInput" placeholder="Type your message..." class="flex-1 bg-gray-700 rounded-l-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-primary-500">
                    <button id="sendMessage" class="bg-primary-600 hover:bg-primary-700 text-white px-4 py-2 rounded-r-lg transition duration-300">
                        <i class="fas fa-paper-plane"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Navigation -->
    <nav class="fixed top-0 left-0 w-full z-40 glass-effect">
        <div class="container mx-auto px-6 py-4">
            <div class="flex justify-between items-center">
                <a href="#" class="text-xl font-bold text-primary-400">Sharon Unnikrishnan</a>
                <div class="hidden md:flex space-x-8">
                    <a href="#home" class="nav-link">Home</a>
                    <a href="#about" class="nav-link">About</a>
                    <a href="#experience" class="nav-link">Experience</a>
                    <a href="#projects" class="nav-link">Projects</a>
                    <a href="#skills" class="nav-link">Skills</a>
                    <a href="#contact" class="nav-link">Contact</a>
                </div>
                <button id="mobileMenuButton" class="md:hidden">
                    <i class="fas fa-bars text-xl"></i>
                </button>
            </div>
        </div>
        
        <!-- Mobile Menu -->
        <div id="mobileMenu" class="md:hidden hidden glass-effect mt-2 py-4 px-6 rounded-lg">
            <div class="flex flex-col space-y-4">
                <a href="#home" class="nav-link py-2">Home</a>
                <a href="#about" class="nav-link py-2">About</a>
                <a href="#experience" class="nav-link py-2">Experience</a>
                <a href="#projects" class="nav-link py-2">Projects</a>
                <a href="#skills" class="nav-link py-2">Skills</a>
                <a href="#contact" class="nav-link py-2">Contact</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="min-h-screen gradient-bg flex items-center justify-center relative overflow-hidden">
        <div class="absolute inset-0 bg-black/30"></div>
        <div class="container mx-auto px-6 py-20 z-10 text-center">
            <div class="max-w-3xl mx-auto">
                <div class="mb-8 animate-float">
                    <div class="w-40 h-40 mx-auto rounded-full overflow-hidden border-4 border-white/50 shadow-xl">
                        <!-- Placeholder for profile image -->
                        <div class="w-full h-full bg-primary-800 flex">
                            <img src="sharonunnikrishnan.jpg">
                        </div>
                    </div>
                </div>
                <h1 class="text-4xl md:text-6xl font-bold text-white mb-4 animate-fadeIn">Sharon Unnikrishnan</h1>
                <h2 class="text-xl md:text-2xl text-white/90 mb-8 animate-fadeIn">Web Developer | Wildlife Photographer</h2>
                <p class="text-lg text-white/80 mb-10 max-w-2xl mx-auto animate-fadeIn">
                    A highly motivated and skilled Laravel Developer with over 2 years of experience in building dynamic and scalable web applications.
                </p>
                <div class="flex flex-col sm:flex-row justify-center gap-4 animate-fadeIn">
                    <a href="#contact" class="px-6 py-3 bg-white text-primary-600 font-medium rounded-lg shadow-lg hover:bg-gray-100 transition duration-300">
                        <i class="fas fa-envelope mr-2"></i>Get In Touch
                    </a>
                    <a href="#projects" class="px-6 py-3 bg-transparent border-2 border-white text-white font-medium rounded-lg hover:bg-white/10 transition duration-300">
                        <i class="fas fa-briefcase mr-2"></i>View My Work
                    </a>
                    <!-- <button id="downloadResume" class="px-6 py-3 bg-primary-600 hover:bg-primary-700 text-white font-medium rounded-lg shadow-lg transition duration-300">
                        <i class="fas fa-download mr-2"></i>Download Resume
                    </button> -->
                    <a href="resume.html" class="px-6 py-3 bg-transparent border-2 border-white text-white font-medium rounded-lg hover:bg-white/10 transition duration-300">
                        <i class="fas fa-book mr-2"></i>Resume
                    </a>
                </div>
            </div>
        </div>
        
        <!-- Scroll Indicator -->
        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
            <a href="#about" class="text-white text-2xl">
                <i class="fas fa-chevron-down"></i>
            </a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 bg-gray-900">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold text-center mb-16 section-title">About Me</h2>
            
            <div class="flex flex-col lg:flex-row gap-12 items-center">
                <div class="lg:w-1/2">
                    <div class="glass-effect rounded-2xl p-8 card-hover">
                        <h3 class="text-2xl font-semibold mb-6 text-primary-400">Professional Summary</h3>
                        <p class="text-gray-300 mb-6">
                            A highly motivated and skilled <span class="font-semibold text-primary-400">Laravel Developer</span> with over <span class="font-semibold">3 years of experience</span> in building dynamic and scalable web applications. Possesses more than <span class="font-semibold">6 years of PHP development experience</span>, with strong expertise in <span class="font-semibold">Laravel</span> and <span class="font-semibold">CodeIgniter</span> frameworks.
                        </p>
                        <p class="text-gray-300 mb-6">
                            Proficient in frontend technologies including <span class="font-semibold">HTML, CSS, and JavaScript</span>, with a solid understanding of <span class="font-semibold">API integration</span>, performance optimization, and secure authentication systems. Basic knowledge of <span class="font-semibold">React.js</span> and proficiency in design tools such as <span class="font-semibold">Figma, Photoshop, and Illustrator</span>.
                        </p>
                        <p class="text-gray-300">
                            Dedicated to creating efficient, maintainable, and visually appealing web solutions.
                        </p>
                    </div>
                </div>
                
                <div class="lg:w-1/2">
                    <div class="grid grid-cols-1 gap-6">
                        <div class="glass-effect rounded-xl p-6 text-center card-hover">
                            <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-primary-900 flex items-center justify-center">
                                <i class="fas fa-code text-2xl text-primary-400"></i>
                            </div>
                            <h3 class="text-xl font-semibold mb-2">Web Development</h3>
                            <p class="text-gray-400">Full-stack development with focus on backend</p>
                        </div>
                        
                        <div class="glass-effect rounded-xl p-6 text-center card-hover">
                            <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-primary-900 flex items-center justify-center">
                                <i class="fas fa-mobile-alt text-2xl text-primary-400"></i>
                            </div>
                            <h3 class="text-xl font-semibold mb-2">Responsive Design</h3>
                            <p class="text-gray-400">Creating applications that work on all devices</p>
                        </div>
                        
                        <div class="glass-effect rounded-xl p-6 text-center card-hover">
                            <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-primary-900 flex items-center justify-center">
                                <i class="fas fa-palette text-2xl text-primary-400"></i>
                            </div>
                            <h3 class="text-xl font-semibold mb-2">UI/UX Design</h3>
                            <p class="text-gray-400">Designing intuitive and beautiful interfaces</p>
                        </div>
                        
                        <div class="glass-effect rounded-xl p-6 text-center card-hover">
                            <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-primary-900 flex items-center justify-center">
                                <i class="fas fa-camera text-2xl text-primary-400"></i>
                            </div>
                            <h3 class="text-xl font-semibold mb-2">Photography</h3>
                            <p class="text-gray-400">Capturing moments with creative vision</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="py-20 bg-gray-800">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold text-left mb-16 section-title">Professional Experience</h2>
            
            <div class="max-w-4xl mx-auto">
                <!-- Experience 1 -->
                <div class="mb-12 relative">
                    <div class="flex flex-col md:flex-row gap-6">
                        <div class="md:w-1/3">
                            <div class="glass-effect rounded-xl p-6 h-full card-hover">
                                <div class="flex items-center mb-4">
                                    <div class="w-12 h-12 rounded-full bg-primary-900 flex items-center justify-center mr-4">
                                        <i class="fas fa-briefcase text-primary-400"></i>
                                    </div>
                                    <div>
                                        <h3 class="text-xl font-semibold">Assistant Product Manager</h3>
                                        <p class="text-primary-400">ADSS Private Limited</p>
                                    </div>
                                </div>
                                <p class="text-gray-400">January 2023 – Present</p>
                            </div>
                        </div>
                        <div class="md:w-2/3">
                            <div class="glass-effect rounded-xl p-6 h-full card-hover">
                                <ul class="space-y-3 text-gray-300">
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Developed and maintained a <span class="font-semibold">prepaid card-based application</span> with multiple user types and service modules.</span>
                                    </li>
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Integrated third-party payment APIs such as <span class="font-semibold">PayU, Cashfree, and Transcorp</span>.</span>
                                    </li>
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Implemented secure <span class="font-semibold">user authentication, KYC verification,</span> and <span class="font-semibold">data validation</span> processes.</span>
                                    </li>
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Optimized backend logic to enhance <span class="font-semibold">application performance</span> and <span class="font-semibold">scalability</span>.</span>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                    <div class="absolute left-1/2 transform -translate-x-1/2 -bottom-6 w-1 h-6 bg-primary-700"></div>
                </div>
                
                <!-- Experience 2 -->
                <div class="mb-12 relative">
                    <div class="flex flex-col md:flex-row gap-6">
                        <div class="md:w-1/3">
                            <div class="glass-effect rounded-xl p-6 h-full card-hover">
                                <div class="flex items-center mb-4">
                                    <div class="w-12 h-12 rounded-full bg-primary-900 flex items-center justify-center mr-4">
                                        <i class="fas fa-laptop-code text-primary-400"></i>
                                    </div>
                                    <div>
                                        <h3 class="text-xl font-semibold">Project Engineer</h3>
                                        <p class="text-primary-400">National Informatics Centre</p>
                                    </div>
                                </div>
                                <p class="text-gray-400">April 2018 – January 2021</p>
                            </div>
                        </div>
                        <div class="md:w-2/3">
                            <div class="glass-effect rounded-xl p-6 h-full card-hover">
                                <ul class="space-y-3 text-gray-300">
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Worked on the <span class="font-semibold">Treasury Savings Bank</span> system, improving existing functionalities.</span>
                                    </li>
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Diagnosed and resolved critical system issues, ensuring <span class="font-semibold">smooth and continuous operation</span>.</span>
                                    </li>
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Supported integration of new modules into the existing application framework.</span>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                    <div class="absolute left-1/2 transform -translate-x-1/2 -bottom-6 w-1 h-6 bg-primary-700"></div>
                </div>
                
                <!-- Experience 3 -->
                <div class="mb-12">
                    <div class="flex flex-col md:flex-row gap-6">
                        <div class="md:w-1/3">
                            <div class="glass-effect rounded-xl p-6 h-full card-hover">
                                <div class="flex items-center mb-4">
                                    <div class="w-12 h-12 rounded-full bg-primary-900 flex items-center justify-center mr-4">
                                        <i class="fas fa-code text-primary-400"></i>
                                    </div>
                                    <div>
                                        <h3 class="text-xl font-semibold">PHP Developer</h3>
                                        <p class="text-primary-400">SANS IT Consultancy</p>
                                    </div>
                                </div>
                                <p class="text-gray-400">February 2017 – November 2018</p>
                            </div>
                        </div>
                        <div class="md:w-2/3">
                            <div class="glass-effect rounded-xl p-6 h-full card-hover">
                                <ul class="space-y-3 text-gray-300">
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Contributed to the development of a <span class="font-semibold">Human Resource Management System (HRMS)</span>.</span>
                                    </li>
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Focused on automation of employee management, leave tracking, and workflow processes.</span>
                                    </li>
                                    <li class="flex items-start">
                                        <i class="fas fa-check text-primary-500 mt-1 mr-3"></i>
                                        <span>Ensured reliability and maintainability of core PHP modules.</span>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-20 bg-gray-900">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold text-center mb-16 section-title">Key Projects</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Project 1 -->
                <div class="glass-effect rounded-2xl overflow-hidden card-hover">
                    <div class="h-48 bg-gradient-to-r from-primary-500 to-purple-600 flex items-center justify-center">
                        <i class="fas fa-credit-card text-white text-6xl"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold mb-3">MyDop</h3>
                        <p class="text-gray-400 mb-4">
                            A prepaid card-based application offering services like KYC registration, card loading, bill payments, and money transfers.
                        </p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">Laravel</span>
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">API Integration</span>
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">Payment Gateway</span>
                        </div>
                        <a href="https://mydop.in/" class="text-primary-400 font-medium flex items-center" target="_blank">
                            View Details <i class="fas fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- Project 2 -->
                <div class="glass-effect rounded-2xl overflow-hidden card-hover">
                    <div class="h-48 bg-gradient-to-r from-green-500 to-blue-600 flex items-center justify-center">
                        <i class="fas fa-university text-white text-6xl"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold mb-3">Treasury Savings Bank</h3>
                        <p class="text-gray-400 mb-4">
                            Enhanced an existing government banking system by adding modules for customer management and account creation.
                        </p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">CodeIgniter</span>
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">Banking System</span>
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">Government</span>
                        </div>
                        <a href="https://tsbonline.kerala.gov.in/" class="text-primary-400 font-medium flex items-center" target="_blank">
                            View Details <i class="fas fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- Project 3 -->
                <div class="glass-effect rounded-2xl overflow-hidden card-hover">
                    <div class="h-48 bg-gradient-to-r from-purple-500 to-pink-600 flex items-center justify-center">
                        <i class="fas fa-users text-white text-6xl"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold mb-3">HRMS Software</h3>
                        <p class="text-gray-400 mb-4">
                            Developed modules for employee information management and leave tracking, enabling workflow automation.
                        </p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">Core PHP</span>
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">HR Management</span>
                            <span class="px-3 py-1 bg-primary-900 text-primary-200 rounded-full text-sm">Automation</span>
                        </div>
                        <a href="https://www.sansitconsultancy.com/" class="text-primary-400 font-medium flex items-center" target="_blank">
                            View Details <i class="fas fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-20 bg-gray-800">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold text-center mb-16 section-title">Technical Skills</h2>
            
            <div class="max-w-4xl mx-auto">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    <!-- Backend Skills -->
                    <div class="glass-effect rounded-2xl p-6 card-hover">
                        <h3 class="text-xl font-semibold mb-6 flex items-center">
                            <i class="fas fa-server text-primary-400 mr-3"></i>
                            Backend Development
                        </h3>
                        <div class="space-y-4">
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">PHP</span>
                                    <span class="text-primary-400">95%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 95%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">Laravel</span>
                                    <span class="text-primary-400">90%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 90%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">CodeIgniter</span>
                                    <span class="text-primary-400">85%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 85%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">MySQL</span>
                                    <span class="text-primary-400">88%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 88%"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Frontend Skills -->
                    <div class="glass-effect rounded-2xl p-6 card-hover">
                        <h3 class="text-xl font-semibold mb-6 flex items-center">
                            <i class="fas fa-desktop text-primary-400 mr-3"></i>
                            Frontend & Design
                        </h3>
                        <div class="space-y-4">
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">HTML/CSS</span>
                                    <span class="text-primary-400">90%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 90%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">JavaScript</span>
                                    <span class="text-primary-400">80%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 80%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">React.js</span>
                                    <span class="text-primary-400">65%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 65%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between mb-1">
                                    <span class="font-medium">Figma/Photoshop</span>
                                    <span class="text-primary-400">75%</span>
                                </div>
                                <div class="skill-bar">
                                    <div class="skill-progress bg-primary-500" style="width: 75%"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Other Skills -->
                <div class="mt-8 glass-effect rounded-2xl p-6 card-hover">
                    <h3 class="text-xl font-semibold mb-6 text-center">Other Skills & Tools</h3>
                    <div class="flex flex-wrap justify-center gap-4">
                        <div class="flex items-center bg-primary-900 px-4 py-2 rounded-full">
                            <i class="fas fa-code-branch text-primary-400 mr-2"></i>
                            <span>Git</span>
                        </div>
                        <div class="flex items-center bg-primary-900 px-4 py-2 rounded-full">
                            <i class="fas fa-plug text-primary-400 mr-2"></i>
                            <span>API Integration</span>
                        </div>
                        <div class="flex items-center bg-primary-900 px-4 py-2 rounded-full">
                            <i class="fas fa-shield-alt text-primary-400 mr-2"></i>
                            <span>Security</span>
                        </div>
                        <div class="flex items-center bg-primary-900 px-4 py-2 rounded-full">
                            <i class="fas fa-tachometer-alt text-primary-400 mr-2"></i>
                            <span>Performance Optimization</span>
                        </div>
                        <div class="flex items-center bg-primary-900 px-4 py-2 rounded-full">
                            <i class="fas fa-mobile-alt text-primary-400 mr-2"></i>
                            <span>Responsive Design</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-gray-900">
        <div class="container mx-auto px-6">
            <h2 class="text-3xl font-bold text-center mb-16 section-title">Get In Touch</h2>
            
            <div class="max-w-4xl mx-auto">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
                    <!-- Contact Info -->
                    <div>
                        <h3 class="text-2xl font-semibold mb-6">Contact Information</h3>
                        <div class="space-y-6">
                            <div class="flex items-start">
                                <div class="w-12 h-12 rounded-full bg-primary-900 flex items-center justify-center mr-4">
                                    <i class="fas fa-map-marker-alt text-primary-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Location</h4>
                                    <p class="text-gray-400">Malathi Mandiram, Perumachery, Post Kolachery, PIN: 670601</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start">
                                <div class="w-12 h-12 rounded-full bg-primary-900 flex items-center justify-center mr-4">
                                    <i class="fas fa-phone text-primary-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Phone</h4>
                                    <p class="text-gray-400">+91 9747642004</p>
                                </div>
                            </div>

                            <div class="flex items-start">
                                <div class="w-12 h-12 rounded-full bg-primary-900 flex items-center justify-center mr-4">
                                    <i class="fas fa-envelope text-primary-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Email</h4>
                                    <p class="text-gray-400">sharonunnikrishnan11@gmail.com</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start">
                                <div class="w-12 h-12 rounded-full bg-primary-900 flex items-center justify-center mr-4">
                                    <i class="fas fa-globe text-primary-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Website</h4>
                                    <a href="https://sharonunnikrishnan.keravibes.com" class="text-primary-400 hover:underline">sharonunnikrishnan.keravibes.com</a>
                                </div>
                            </div>
                        </div>
                        
                        <div class="mt-8">
                            <h4 class="font-semibold mb-4">Follow Me</h4>
                            <div class="flex space-x-4">
                                <a href="https://www.instagram.com/sharon.unnikrishnan/" class="w-10 h-10 rounded-full bg-primary-900 flex items-center justify-center text-primary-400 hover:bg-primary-800 transition" target="_blank">
                                    <i class="fab fa-instagram"></i>
                                </a>
                                <a href="https://www.linkedin.com/in/sharon-unnikrishnan-529b31230/" class="w-10 h-10 rounded-full bg-primary-900 flex items-center justify-center text-primary-400 hover:bg-primary-800 transition" target="_blank">
                                    <i class="fab fa-linkedin-in"></i>
                                </a>
                                <a href="https://github.com/sharonunnikrishnan" class="w-10 h-10 rounded-full bg-primary-900 flex items-center justify-center text-primary-400 hover:bg-primary-800 transition" target="_blank">
                                    <i class="fab fa-github"></i>
                                </a>  
                            </div>
                        </div>
                    </div>
                    
                    <!-- Contact Form -->
                    <div class="glass-effect rounded-2xl p-8 card-hover">
                        <h3 class="text-2xl font-semibold mb-6">Send Me a Message</h3>
                        <form class="space-y-4">
                            <div>
                                <label for="name" class="block text-sm font-medium mb-1">Name</label>
                                <input type="text" id="name" class="w-full px-4 py-2 rounded-lg border border-gray-700 bg-gray-800 focus:outline-none focus:ring-2 focus:ring-primary-500">
                            </div>
                            <div>
                                <label for="email" class="block text-sm font-medium mb-1">Email</label>
                                <input type="email" id="email" class="w-full px-4 py-2 rounded-lg border border-gray-700 bg-gray-800 focus:outline-none focus:ring-2 focus:ring-primary-500">
                            </div>
                            <div>
                                <label for="subject" class="block text-sm font-medium mb-1">Subject</label>
                                <input type="text" id="subject" class="w-full px-4 py-2 rounded-lg border border-gray-700 bg-gray-800 focus:outline-none focus:ring-2 focus:ring-primary-500">
                            </div>
                            <div>
                                <label for="message" class="block text-sm font-medium mb-1">Message</label>
                                <textarea id="message" rows="4" class="w-full px-4 py-2 rounded-lg border border-gray-700 bg-gray-800 focus:outline-none focus:ring-2 focus:ring-primary-500"></textarea>
                            </div>
                            <button type="submit" class="w-full bg-primary-600 hover:bg-primary-700 text-white py-3 rounded-lg font-medium transition duration-300">
                                Send Message
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-8">
        <div class="container mx-auto px-6 text-center">
            <p>&copy; 2023 Sharon Unnikrishnan. All rights reserved.</p>
            <p class="mt-2 text-gray-400">Laravel Developer | Wildlife Photographer</p>
        </div>
    </footer>

    <script>
        // Set default theme to dark
        document.documentElement.classList.add('dark');
        
        // Theme Toggle
        const themeToggle = document.getElementById('themeToggle');
        const html = document.documentElement;
        
        // Check for saved theme preference or default to dark
        const savedTheme = localStorage.getItem('theme') || 'dark';
        html.classList.toggle('light', savedTheme === 'light');
        html.classList.toggle('dark', savedTheme === 'dark');
        
        themeToggle.addEventListener('click', () => {
            html.classList.toggle('light');
            html.classList.toggle('dark');
            localStorage.setItem('theme', html.classList.contains('light') ? 'light' : 'dark');
        });
        
        // Mobile Menu Toggle
        const mobileMenuButton = document.getElementById('mobileMenuButton');
        const mobileMenu = document.getElementById('mobileMenu');
        
        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });
        
        // Close mobile menu when clicking on a link
        document.querySelectorAll('#mobileMenu a').forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Animate skill bars when they come into view
        const observerOptions = {
            threshold: 0.5
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const skillBars = entry.target.querySelectorAll('.skill-progress');
                    skillBars.forEach(bar => {
                        // Reset width to 0 then animate to the target width
                        const targetWidth = bar.style.width;
                        bar.style.width = '0%';
                        setTimeout(() => {
                            bar.style.width = targetWidth;
                        }, 100);
                    });
                }
            });
        }, observerOptions);
        
        const skillsSection = document.getElementById('skills');
        if (skillsSection) {
            observer.observe(skillsSection);
        }
        
        // Add animation to elements when they come into view
        const animateOnScroll = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate-slideIn');
                }
            });
        }, { threshold: 0.1 });
        
        // Observe all sections for animation
        document.querySelectorAll('section > .container > *').forEach(el => {
            animateOnScroll.observe(el);
        });
        
        // Back to Top Button
        const backToTopButton = document.getElementById('backToTop');
        
        window.addEventListener('scroll', () => {
            if (window.pageYOffset > 300) {
                backToTopButton.classList.remove('opacity-0');
                backToTopButton.classList.add('opacity-100');
            } else {
                backToTopButton.classList.remove('opacity-100');
                backToTopButton.classList.add('opacity-0');
            }
        });
        
        backToTopButton.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // Font Selector
        const fontToggle = document.getElementById('fontToggle');
        const fontOptions = document.getElementById('fontOptions');
        const fontButtons = document.querySelectorAll('#fontOptions button');
        
        fontToggle.addEventListener('click', () => {
            fontOptions.classList.toggle('hidden');
        });
        
        // Set initial font from localStorage or default to 'inter'
        const savedFont = localStorage.getItem('font') || 'inter';
        document.documentElement.style.setProperty('--current-font', savedFont.charAt(0).toUpperCase() + savedFont.slice(1));
        document.body.className = document.body.className.replace(/\bfont-\w+/g, '') + ' font-' + savedFont;
        
        fontButtons.forEach(button => {
            button.addEventListener('click', () => {
                const selectedFont = button.getAttribute('data-font');
                document.body.className = document.body.className.replace(/\bfont-\w+/g, '') + ' font-' + selectedFont;
                document.documentElement.style.setProperty('--current-font', selectedFont.charAt(0).toUpperCase() + selectedFont.slice(1));
                localStorage.setItem('font', selectedFont);
                fontOptions.classList.add('hidden');
            });
        });
        
        // Close font options when clicking outside
        document.addEventListener('click', (e) => {
            if (!fontToggle.contains(e.target) && !fontOptions.contains(e.target)) {
                fontOptions.classList.add('hidden');
            }
        });
        
        // Resume Download
        const downloadResumeButton = document.getElementById('downloadResume');
        
        downloadResumeButton.addEventListener('click', () => {
            // In a real implementation, this would link to an actual PDF file
            alert('Resume download would start now. In a real implementation, this would link to a PDF file.');
            // window.open('path/to/resume.pdf', '_blank');
        });
        
        // AI Chatbot
        const chatbotToggle = document.getElementById('chatbotToggle');
        const chatbotContainer = document.getElementById('chatbotContainer');
        const closeChatbot = document.getElementById('closeChatbot');
        const chatMessages = document.getElementById('chatMessages');
        const chatInput = document.getElementById('chatInput');
        const sendMessage = document.getElementById('sendMessage');
        
        chatbotToggle.addEventListener('click', () => {
            chatbotContainer.classList.toggle('hidden');
            chatbotContainer.classList.add('animate-bounceIn');
        });
        
        closeChatbot.addEventListener('click', () => {
            chatbotContainer.classList.add('hidden');
        });
        
        // Chatbot responses
        const botResponses = {
            greeting: ["Hello! How can I help you today?", "Hi there! What would you like to know?", "Greetings! I'm here to answer your questions."],
            skills: ["Sharon has expertise in PHP, Laravel, CodeIgniter, MySQL, HTML, CSS, JavaScript, and React.js. He also has experience with API integration and UI/UX design tools like Figma and Photoshop.", "Sharon's technical skills include backend development with PHP frameworks like Laravel and CodeIgniter, frontend technologies, database management, and design tools."],
            experience: ["Sharon has over 3 years of experience as a Laravel Developer and more than 6 years in PHP development. He has worked as an Assistant Product Manager at ADSS Private Limited, Project Engineer at National Informatics Centre, and PHP Developer at SANS IT Consultancy.", "Sharon's professional experience includes developing prepaid card applications, working on government banking systems, and creating HR management software across different organizations."],
            projects: ["Sharon has worked on several key projects including MyDop (a prepaid card application), Treasury Savings Bank system, and HRMS software. These projects involved payment integrations, user management, and workflow automation.", "Some of Sharon's notable projects are MyDop with payment gateway integrations, Treasury Savings Bank enhancements, and HR management systems with automation features."],
            contact: ["You can contact Sharon via phone at +91 9747642004, visit his website at sharonunnikrishnan.evercorefm.ae, or use the contact form on this portfolio. He's located in Malathi Mandiram, Perumachery, Post Kolachery.", "Sharon can be reached through multiple channels: phone, website, or the contact form. His contact details are available in the contact section of this portfolio."],
            default: ["I'm not sure I understand. Could you rephrase your question? You can ask about skills, experience, projects, or contact information.", "I don't have an answer for that specific question. Try asking about Sharon's technical skills, work experience, projects, or how to contact him."]
        };
        
        // Function to add a message to the chat
        function addMessage(message, isUser = false) {
            const messageDiv = document.createElement('div');
            messageDiv.classList.add('p-3', 'max-w-xs', 'mb-4', 'chat-message');
            
            if (isUser) {
                messageDiv.classList.add('bg-primary-600', 'user-message', 'ml-auto');
            } else {
                messageDiv.classList.add('bg-gray-700', 'bot-message');
            }
            
            messageDiv.innerHTML = `<p>${message}</p>`;
            chatMessages.appendChild(messageDiv);
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }
        
        // Function to get bot response
        function getBotResponse(userMessage) {
            userMessage = userMessage.toLowerCase();
            
            if (userMessage.includes('hello') || userMessage.includes('hi') || userMessage.includes('hey')) {
                return botResponses.greeting[Math.floor(Math.random() * botResponses.greeting.length)];
            } else if (userMessage.includes('skill') || userMessage.includes('technology') || userMessage.includes('tech')) {
                return botResponses.skills[Math.floor(Math.random() * botResponses.skills.length)];
            } else if (userMessage.includes('experience') || userMessage.includes('work') || userMessage.includes('job')) {
                return botResponses.experience[Math.floor(Math.random() * botResponses.experience.length)];
            } else if (userMessage.includes('project') || userMessage.includes('work')) {
                return botResponses.projects[Math.floor(Math.random() * botResponses.projects.length)];
            } else if (userMessage.includes('contact') || userMessage.includes('email') || userMessage.includes('phone')) {
                return botResponses.contact[Math.floor(Math.random() * botResponses.contact.length)];
            } else {
                return botResponses.default[Math.floor(Math.random() * botResponses.default.length)];
            }
        }
        
        // Function to simulate typing indicator
        function showTypingIndicator() {
            const typingDiv = document.createElement('div');
            typingDiv.classList.add('bot-message', 'bg-gray-700', 'p-3', 'max-w-xs', 'mb-4');
            typingDiv.id = 'typing-indicator';
            typingDiv.innerHTML = `
                <div class="flex space-x-1">
                    <div class="typing-indicator"></div>
                    <div class="typing-indicator"></div>
                    <div class="typing-indicator"></div>
                </div>
            `;
            chatMessages.appendChild(typingDiv);
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }
        
        // Function to remove typing indicator
        function removeTypingIndicator() {
            const typingIndicator = document.getElementById('typing-indicator');
            if (typingIndicator) {
                typingIndicator.remove();
            }
        }
        
        // Send message function
        function sendUserMessage() {
            const message = chatInput.value.trim();
            if (message === '') return;
            
            addMessage(message, true);
            chatInput.value = '';
            
            showTypingIndicator();
            
            setTimeout(() => {
                removeTypingIndicator();
                const botResponse = getBotResponse(message);
                addMessage(botResponse);
            }, 1000 + Math.random() * 1000);
        }
        
        // Event listeners for sending messages
        sendMessage.addEventListener('click', sendUserMessage);
        
        chatInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                sendUserMessage();
            }
        });
    </script>
</body>
</html>
