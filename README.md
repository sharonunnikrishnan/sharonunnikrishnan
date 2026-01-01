<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Sharon Unnikrishnan - Backend Engineer</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Source+Code+Pro:wght@300;400&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary: #7c3aed;
            --dark: #1e293b;
            --light: #f8fafc;
            --gray: #64748b;
            --light-gray: #e2e8f0;
            --border-radius: 8px;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .resume-container {
            max-width: 1000px;
            margin: 0 auto;
            background: white;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            overflow: hidden;
            position: relative;
        }
        
        /* Header Styles */
        .resume-header {
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            padding: 40px;
            position: relative;
            overflow: hidden;
        }
        
        .header-content {
            position: relative;
            z-index: 2;
        }
        
        .header-bg {
            position: absolute;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            background: url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZGVmcz48cGF0dGVybiBpZD0iY29kZVBhdHRlcm4iIHBhdHRlcm5Vbml0cz0idXNlclNwYWNlT25Vc2UiIHdpZHRoPSI0MCIgaGVpZ2h0PSI0MCIgdmlld0JveD0iMCAwIDEwIDEwIj48cGF0aCBkPSJNLTEsMSBsMiwtMiBNMCwxMCBsMTAsLTEwIE05LDExIGwyLC0yIiBzdHJva2U9InJnYmEoMjU1LDI1NSwyNTUsMC4xKSIgc3Ryb2tlLXdpZHRoPSIxIi8+PC9wYXR0ZXJuPjwvZGVmcz48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSJ1cmwoI2NvZGVQYXR0ZXJuKSIvPjwvc3ZnPg==');
            opacity: 0.1;
            z-index: 1;
        }
        
        .name {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 5px;
            letter-spacing: -0.5px;
        }
        
        .title {
            font-size: 1.4rem;
            font-weight: 500;
            margin-bottom: 20px;
            opacity: 0.9;
        }
        
        .contact-info {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.95rem;
        }
        
        .contact-item i {
            font-size: 1.1rem;
        }
        
        .contact-item a {
            color: white;
            text-decoration: none;
            transition: var(--transition);
        }
        
        .contact-item a:hover {
            text-decoration: underline;
        }
        
        /* Section Styles */
        .resume-section {
            padding: 30px 40px;
            border-bottom: 1px solid var(--light-gray);
        }
        
        .resume-section:last-of-type {
            border-bottom: none;
        }
        
        .section-title {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .section-title i {
            margin-right: 10px;
            font-size: 1.2rem;
        }
        
        .section-title h2 {
            font-size: 1.4rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        /* Summary Section */
        .summary-text {
            font-size: 1rem;
            line-height: 1.7;
            color: var(--gray);
        }
        
        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .skill-category {
            margin-bottom: 15px;
        }
        
        .skill-category h4 {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--dark);
        }
        
        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .skill-tag {
            background: var(--light);
            border: 1px solid var(--light-gray);
            border-radius: 20px;
            padding: 5px 12px;
            font-size: 0.85rem;
            color: var(--gray);
            transition: var(--transition);
        }
        
        .skill-tag:hover {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
            transform: translateY(-2px);
        }
        
        /* Experience Section */
        .experience-item {
            margin-bottom: 25px;
            padding-bottom: 25px;
            border-bottom: 1px dashed var(--light-gray);
        }
        
        .experience-item:last-of-type {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }
        
        .job-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 5px;
            color: var(--dark);
        }
        
        .company {
            font-size: 1rem;
            color: var(--primary);
            font-weight: 500;
            margin-bottom: 5px;
        }
        
        .date {
            font-size: 0.9rem;
            color: var(--gray);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
        }
        
        .date i {
            margin-right: 5px;
            font-size: 0.8rem;
        }
        
        .responsibilities {
            margin-left: 20px;
        }
        
        .responsibilities li {
            margin-bottom: 8px;
            color: var(--gray);
        }
        
        /* Projects Section */
        .projects-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .project-item {
            background: var(--light);
            border-radius: var(--border-radius);
            padding: 20px;
            border-left: 4px solid var(--primary);
            transition: var(--transition);
        }
        
        .project-item:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow);
        }
        
        .project-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--dark);
        }
        
        .project-tech {
            font-size: 0.85rem;
            color: var(--primary);
            font-weight: 500;
            margin-bottom: 10px;
            font-family: 'Source Code Pro', monospace;
        }
        
        .project-description {
            font-size: 0.95rem;
            color: var(--gray);
            line-height: 1.6;
        }
        
        /* Education Section */
        .education-item {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .education-icon {
            background: var(--light);
            border-radius: 50%;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: var(--primary);
            font-size: 1.2rem;
        }
        
        .education-details h4 {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 5px;
            color: var(--dark);
        }
        
        .education-details p {
            font-size: 0.95rem;
            color: var(--gray);
        }
        
        /* Footer */
        .resume-footer {
            background: var(--light);
            padding: 20px 40px;
            text-align: center;
            color: var(--gray);
            font-size: 0.9rem;
            border-top: 1px solid var(--light-gray);
        }
        
        .github-link {
            color: var(--primary);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
        }
        
        .github-link:hover {
            color: var(--secondary);
            text-decoration: underline;
        }
        
        /* Print Styles */
        @media print {
            body {
                background: white;
                padding: 0;
            }
            
            .resume-container {
                box-shadow: none;
                border-radius: 0;
            }
            
            .resume-header {
                background: var(--primary) !important;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }
            
            .skill-tag:hover, .project-item:hover {
                transform: none;
            }
        }
        
        /* Responsive Styles */
        @media (max-width: 768px) {
            .resume-header {
                padding: 30px 20px;
            }
            
            .resume-section {
                padding: 25px 20px;
            }
            
            .name {
                font-size: 2rem;
            }
            
            .title {
                font-size: 1.2rem;
            }
            
            .contact-info {
                flex-direction: column;
                gap: 10px;
            }
            
            .skills-grid, .projects-list {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 480px) {
            .name {
                font-size: 1.8rem;
            }
            
            .title {
                font-size: 1.1rem;
            }
            
            .section-title h2 {
                font-size: 1.2rem;
            }
        }
    </style>
</head>

<body>
    <div class="resume-container">
        <!-- Header Section -->
        <header class="resume-header">
            <div class="header-bg"></div>
            <div class="header-content">
                <h1 class="name">Sharon Unnikrishnan</h1>
                <p class="title">Backend Engineer | Laravel | API & Payment Integrations</p>
                
                <div class="contact-info">
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <span>Kannur, Kerala, India</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <span>+91 9747642004</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <a href="mailto:sharonunnikrishnan11@gmail.com">sharonunnikrishnan11@gmail.com</a>
                    </div>
                    <div class="contact-item">
                        <i class="fab fa-github"></i>
                        <a href="https://github.com/sharonunnikrishnan" target="_blank">github.com/sharonunnikrishnan</a>
                    </div>
                </div>
            </div>
        </header>
        
        <!-- Summary Section -->
        <section class="resume-section">
            <div class="section-title">
                <i class="fas fa-user"></i>
                <h2>Professional Summary</h2>
            </div>
            <p class="summary-text">
                Backend Engineer with 6+ years of PHP experience and 2+ years of Laravel specialization,
                building transaction-heavy, API-driven applications in fintech and government domains.
                Strong expertise in Laravel, REST APIs, payment gateway integrations, KYC workflows,
                role-based access control, cron jobs, and secure authentication. Experienced in owning
                backend modules end-to-end, maintaining legacy systems, and resolving production issues.
            </p>
        </section>
        
        <!-- Skills Section -->
        <section class="resume-section">
            <div class="section-title">
                <i class="fas fa-code"></i>
                <h2>Technical Skills</h2>
            </div>
            <div class="skills-grid">
                <div class="skill-category">
                    <h4>Backend</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">PHP</span>
                        <span class="skill-tag">Laravel</span>
                        <span class="skill-tag">CodeIgniter</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4>APIs & Payments</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">REST APIs</span>
                        <span class="skill-tag">Webhooks</span>
                        <span class="skill-tag">PayU</span>
                        <span class="skill-tag">Cashfree</span>
                        <span class="skill-tag">Transcorp</span>
                        <span class="skill-tag">Eko</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4>Database</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">MySQL</span>
                        <span class="skill-tag">DB2</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4>Frontend</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">HTML</span>
                        <span class="skill-tag">CSS</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">React.js (basic)</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4>Practices</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">Authentication</span>
                        <span class="skill-tag">Role-based Access Control</span>
                        <span class="skill-tag">KYC Workflows</span>
                        <span class="skill-tag">Cron Jobs</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4>Tools</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">Git</span>
                        <span class="skill-tag">Postman</span>
                        <span class="skill-tag">Linux (basic)</span>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Experience Section -->
        <section class="resume-section">
            <div class="section-title">
                <i class="fas fa-briefcase"></i>
                <h2>Professional Experience</h2>
            </div>
            
            <div class="experience-item">
                <h3 class="job-title">Assistant Manager — Backend Development</h3>
                <p class="company">ADSS Private Limited</p>
                <p class="date"><i class="far fa-calendar"></i> Jan 2023 – Present</p>
                <ul class="responsibilities">
                    <li>Owned backend development of a prepaid card-based fintech platform.</li>
                    <li>Integrated and maintained payment and financial APIs including PayU, Cashfree, Eko, and Transcorp.</li>
                    <li>Implemented KYC workflows, secure authentication, and role-based access control.</li>
                    <li>Developed cron jobs and background processes for settlements and reports.</li>
                </ul>
            </div>
            
            <div class="experience-item">
                <h3 class="job-title">Project Engineer (Contract)</h3>
                <p class="company">National Informatics Centre (NIC)</p>
                <p class="date"><i class="far fa-calendar"></i> Apr 2018 – Jan 2021</p>
                <ul class="responsibilities">
                    <li>Worked on the Treasury Savings Bank system in a government environment.</li>
                    <li>Enhanced modules for accounts, fixed deposits, and interest calculation.</li>
                    <li>Resolved production issues to ensure system stability.</li>
                </ul>
            </div>
            
            <div class="experience-item">
                <h3 class="job-title">PHP Developer</h3>
                <p class="company">SANS IT Consultancy</p>
                <p class="date"><i class="far fa-calendar"></i> Feb 2017 – Nov 2018</p>
                <ul class="responsibilities">
                    <li>Developed backend modules for HRMS using core PHP.</li>
                    <li>Implemented employee data and leave management workflows.</li>
                </ul>
            </div>
        </section>
        
        <!-- Projects Section -->
        <section class="resume-section">
            <div class="section-title">
                <i class="fas fa-project-diagram"></i>
                <h2>Key Projects</h2>
            </div>
            
            <div class="projects-list">
                <div class="project-item">
                    <h4 class="project-title">MyDop</h4>
                    <p class="project-tech">Laravel, Payment Gateways, KYC</p>
                    <p class="project-description">Prepaid card platform with KYC, bill payments, money transfers, and payment gateway integrations.</p>
                </div>
                
                <div class="project-item">
                    <h4 class="project-title">Treasury Savings Bank</h4>
                    <p class="project-tech">PHP, Government Systems</p>
                    <p class="project-description">Government banking system enhancements for accounts, fixed deposits, and interest calculation modules.</p>
                </div>
                
                <div class="project-item">
                    <h4 class="project-title">HRMS</h4>
                    <p class="project-tech">Core PHP, MySQL</p>
                    <p class="project-description">Employee and leave management system with comprehensive HR workflows and reporting.</p>
                </div>
            </div>
        </section>
        
        <!-- Education Section -->
        <section class="resume-section">
            <div class="section-title">
                <i class="fas fa-graduation-cap"></i>
                <h2>Education</h2>
            </div>
            
            <div class="education-item">
                <div class="education-icon">
                    <i class="fas fa-university"></i>
                </div>
                <div class="education-details">
                    <h4>Master of Computer Applications (MCA)</h4>
                    <p>VTU University (2015)</p>
                </div>
            </div>
            
            <div class="education-item">
                <div class="education-icon">
                    <i class="fas fa-user-graduate"></i>
                </div>
                <div class="education-details">
                    <h4>Bachelor of Computer Applications (BCA)</h4>
                    <p>Mangalore University (2012)</p>
                </div>
            </div>
        </section>
        
        <!-- Footer -->
        <footer class="resume-footer">
            <p>View my portfolio and projects on <a href="https://github.com/sharonunnikrishnan" target="_blank" class="github-link">GitHub</a></p>
        </footer>
    </div>
    
    <script>
        // Add subtle animations to skill tags on hover
        document.addEventListener('DOMContentLoaded', function() {
            const skillTags = document.querySelectorAll('.skill-tag');
            
            skillTags.forEach(tag => {
                tag.addEventListener('mouseenter', function() {
                    const colors = ['#2563eb', '#7c3aed', '#059669', '#dc2626', '#d97706'];
                    const randomColor = colors[Math.floor(Math.random() * colors.length)];
                    this.style.backgroundColor = randomColor;
                    this.style.borderColor = randomColor;
                });
                
                tag.addEventListener('mouseleave', function() {
                    this.style.backgroundColor = '';
                    this.style.borderColor = '';
                });
            });
            
            // Print functionality
            document.addEventListener('keydown', function(e) {
                if (e.ctrlKey && e.key === 'p') {
                    e.preventDefault();
                    window.print();
                }
            });
        });
    </script>
</body>
</html>
