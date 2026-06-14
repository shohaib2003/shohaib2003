<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Network Security Engineer | Data Scientist | Binary Flow Animation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Courier New', 'Fira Code', 'Monaco', monospace;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #0f0f23 100%);
            min-height: 100vh;
            overflow-x: hidden;
            color: #00ff41;
        }

        /* Animated Background Grid */
        .grid-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(0, 255, 65, 0.05) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 255, 65, 0.05) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            z-index: 0;
            animation: gridMove 20s linear infinite;
        }

        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        /* Matrix Rain Effect */
        .matrix-rain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            opacity: 0.3;
        }

        /* Main Container */
        .container {
            position: relative;
            z-index: 2;
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header Section */
        .hero {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .glitch {
            font-size: 4rem;
            font-weight: bold;
            text-transform: uppercase;
            position: relative;
            text-shadow: 0.05em 0 0 rgba(255,0,0,0.75), -0.05em -0.025em 0 rgba(0,255,0,0.75), 0.025em 0.05em 0 rgba(0,0,255,0.75);
            animation: glitch 500ms infinite;
        }

        @keyframes glitch {
            0% { text-shadow: 0.05em 0 0 rgba(255,0,0,0.75), -0.05em -0.025em 0 rgba(0,255,0,0.75), 0.025em 0.05em 0 rgba(0,0,255,0.75); }
            14% { text-shadow: 0.05em 0 0 rgba(255,0,0,0.75), -0.05em -0.025em 0 rgba(0,255,0,0.75), 0.025em 0.05em 0 rgba(0,0,255,0.75); }
            15% { text-shadow: -0.05em -0.025em 0 rgba(255,0,0,0.75), 0.025em 0.025em 0 rgba(0,255,0,0.75), -0.05em -0.05em 0 rgba(0,0,255,0.75); }
            49% { text-shadow: -0.05em -0.025em 0 rgba(255,0,0,0.75), 0.025em 0.025em 0 rgba(0,255,0,0.75), -0.05em -0.05em 0 rgba(0,0,255,0.75); }
            50% { text-shadow: 0.025em 0.05em 0 rgba(255,0,0,0.75), 0.05em 0 0 rgba(0,255,0,0.75), 0 -0.05em 0 rgba(0,0,255,0.75); }
            99% { text-shadow: 0.025em 0.05em 0 rgba(255,0,0,0.75), 0.05em 0 0 rgba(0,255,0,0.75), 0 -0.05em 0 rgba(0,0,255,0.75); }
            100% { text-shadow: -0.025em 0 0 rgba(255,0,0,0.75), -0.025em -0.025em 0 rgba(0,255,0,0.75), -0.025em -0.05em 0 rgba(0,0,255,0.75); }
        }

        .subtitle {
            font-size: 1.2rem;
            margin-top: 20px;
            opacity: 0.9;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.9; }
            50% { opacity: 0.5; }
        }

        /* Network Visualization Canvas */
        #networkCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        /* Stats Cards */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 40px 0;
            position: relative;
            z-index: 2;
        }

        .stat-card {
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid #00ff41;
            border-radius: 10px;
            padding: 20px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            animation: borderPulse 2s ease-in-out infinite;
        }

        @keyframes borderPulse {
            0%, 100% { border-color: #00ff41; box-shadow: 0 0 5px #00ff41; }
            50% { border-color: #ff0040; box-shadow: 0 0 20px #ff0040; }
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 255, 65, 0.3);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #00ff41;
        }

        .stat-label {
            font-size: 0.9rem;
            color: #ccc;
            margin-top: 10px;
        }

        /* Binary Flow Animation */
        .binary-container {
            background: rgba(0, 0, 0, 0.6);
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            overflow: hidden;
            position: relative;
            z-index: 2;
        }

        .binary-stream {
            font-family: monospace;
            font-size: 0.8rem;
            white-space: nowrap;
            overflow: hidden;
            display: flex;
            gap: 20px;
        }

        .binary-column {
            animation: scrollUp 8s linear infinite;
        }

        @keyframes scrollUp {
            0% { transform: translateY(100%); }
            100% { transform: translateY(-100%); }
        }

        /* Attack Animation */
        .attack-visualization {
            display: flex;
            justify-content: center;
            gap: 50px;
            margin: 40px 0;
            position: relative;
            z-index: 2;
        }

        .node {
            width: 80px;
            height: 80px;
            background: radial-gradient(circle, #00ff41 0%, #0a0a0a 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            position: relative;
            animation: nodePulse 2s ease-in-out infinite;
        }

        @keyframes nodePulse {
            0%, 100% { transform: scale(1); box-shadow: 0 0 20px #00ff41; }
            50% { transform: scale(1.1); box-shadow: 0 0 40px #ff0040; }
        }

        .attack-line {
            position: absolute;
            height: 2px;
            background: linear-gradient(90deg, #ff0040, #00ff41);
            animation: attack 1s linear infinite;
        }

        @keyframes attack {
            0% { width: 0; opacity: 1; }
            100% { width: 200px; opacity: 0; }
        }

        /* Project Cards */
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 40px 0;
            position: relative;
            z-index: 2;
        }

        .project-card {
            background: rgba(0, 0, 0, 0.7);
            border: 1px solid #00ff41;
            border-radius: 10px;
            padding: 20px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .project-card:hover {
            transform: scale(1.05);
            box-shadow: 0 0 30px rgba(0, 255, 65, 0.5);
        }

        .project-title {
            font-size: 1.3rem;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .project-tech {
            display: inline-block;
            background: #00ff41;
            color: #000;
            padding: 3px 8px;
            border-radius: 5px;
            font-size: 0.7rem;
            margin: 5px;
        }

        /* Threat Detection Meter */
        .threat-meter {
            background: rgba(0, 0, 0, 0.8);
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            position: relative;
            z-index: 2;
        }

        .meter-bar {
            width: 100%;
            height: 30px;
            background: #333;
            border-radius: 15px;
            overflow: hidden;
            margin-top: 10px;
        }

        .meter-fill {
            height: 100%;
            background: linear-gradient(90deg, #00ff41, #ff0040);
            width: 0%;
            animation: threatLevel 4s ease-in-out infinite;
            border-radius: 15px;
        }

        @keyframes threatLevel {
            0%, 100% { width: 15%; }
            25% { width: 45%; }
            50% { width: 78%; }
            75% { width: 32%; }
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 40px;
            position: relative;
            z-index: 2;
            border-top: 1px solid #00ff41;
            margin-top: 40px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .glitch { font-size: 2rem; }
            .attack-visualization { flex-direction: column; align-items: center; }
        }

        /* Cursor effect */
        .cursor {
            width: 20px;
            height: 20px;
            border: 2px solid #00ff41;
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            animation: cursorPulse 1s ease-in-out infinite;
        }

        @keyframes cursorPulse {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.5); opacity: 0.5; }
        }
    </style>
</head>
<body>

<div class="grid-overlay"></div>
<canvas id="networkCanvas"></canvas>

<div class="matrix-rain" id="matrixRain"></div>
<div class="cursor" id="cursor"></div>

<div class="container">
    <!-- Hero Section -->
    <div class="hero">
        <div class="glitch">
            🔒 NETWORK SECURITY ENGINEER | DATA SCIENTIST 🔒
        </div>
        <div class="subtitle">
            >_ Protecting digital assets through advanced analytics and threat intelligence
        </div>
        <div class="subtitle" style="font-size: 0.9rem; color: #888;">
            $ whoami → Cybersecurity Professional | Python | R | Network Defense | Threat Hunting
        </div>
    </div>

    <!-- Stats Cards -->
    <div class="stats-grid">
        <div class="stat-card">
            <div class="stat-number" id="threatCount">1,247</div>
            <div class="stat-label">🚨 Threats Neutralized</div>
        </div>
        <div class="stat-card">
            <div class="stat-number" id="dataProcessed">2.5</div>
            <div class="stat-label">📊 TB Data Analyzed</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">99.97%</div>
            <div class="stat-label">🛡️ Uptime Record</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">3</div>
            <div class="stat-label">🎯 Active Projects</div>
        </div>
    </div>

    <!-- Binary Flow Animation -->
    <div class="binary-container">
        <h3 style="margin-bottom: 15px;">📡 LIVE NETWORK TRAFFIC MONITOR</h3>
        <div class="binary-stream" id="binaryStream"></div>
    </div>

    <!-- Attack Visualization -->
    <div class="attack-visualization">
        <div class="node">
            🖥️<br/>HONEYPOT
        </div>
        <div class="node" style="animation-delay: 0.5s;">
            🌐<br/>ATTACKER
        </div>
        <div class="node" style="animation-delay: 1s;">
            🛡️<br/>FIREWALL
        </div>
        <div class="node" style="animation-delay: 1.5s;">
            💾<br/>SECURE DATA
        </div>
    </div>

    <!-- Threat Meter -->
    <div class="threat-meter">
        <div>⚠️ REAL-TIME THREAT LEVEL ⚠️</div>
        <div class="meter-bar">
            <div class="meter-fill"></div>
        </div>
        <div style="margin-top: 10px; font-size: 0.8rem;">Monitoring DDoS, MITM, Malware, Zero-Day attacks</div>
    </div>

    <!-- Projects Section -->
    <h2 style="margin: 40px 0 20px; position: relative; z-index: 2;">🔬 DATA SCIENCE PROJECTS</h2>
    <div class="projects">
        <div class="project-card">
            <div class="project-title">📱 Social Media vs Academic Impact</div>
            <div class="project-tech">Python</div>
            <div class="project-tech">Pandas</div>
            <div class="project-tech">SciPy</div>
            <div class="project-tech">Seaborn</div>
            <p style="margin-top: 15px;">Hypothesis testing & correlation analysis revealing social media's effect on student performance (N=500+ students)</p>
        </div>
        
        <div class="project-card">
            <div class="project-title">🚢 Titanic Survival Prediction</div>
            <div class="project-tech">R</div>
            <div class="project-tech">ggplot2</div>
            <div class="project-tech">dplyr</div>
            <div class="project-tech">naniar</div>
            <p style="margin-top: 15px;">Advanced EDA, missing value imputation, and feature engineering with 78% model accuracy</p>
        </div>
        
        <div class="project-card">
            <div class="project-title">📚 Web Scraping Pipeline</div>
            <div class="project-tech">R</div>
            <div class="project-tech">rvest</div>
            <div class="project-tech">tidyverse</div>
            <p style="margin-top: 15px;">Automated multi-page scraper collecting 1,000+ book records with price, rating, and category data</p>
        </div>
    </div>

    <!-- Network Engineering Section -->
    <h2 style="margin: 40px 0 20px; position: relative; z-index: 2;">🌐 NETWORK ENGINEERING CAPABILITIES</h2>
    <div class="projects">
        <div class="project-card">
            <div class="project-title">🛡️ IDS/IPS Implementation</div>
            <div class="project-tech">Snort</div>
            <div class="project-tech">Suricata</div>
            <div class="project-tech">pfSense</div>
            <p>Custom rule creation and real-time threat detection</p>
        </div>
        
        <div class="project-card">
            <div class="project-title">🔍 Network Forensics</div>
            <div class="project-tech">Wireshark</div>
            <div class="project-tech">tcpdump</div>
            <div class="project-tech">Zeek</div>
            <p>Packet analysis and incident investigation</p>
        </div>
        
        <div class="project-card">
            <div class="project-title">⚡ Penetration Testing</div>
            <div class="project-tech">Kali Linux</div>
            <div class="project-tech">Metasploit</div>
            <div class="project-tech">Nmap</div>
            <p>Ethical hacking and vulnerability assessment</p>
        </div>
    </div>

    <!-- Footer -->
    <div class="footer">
        <div style="font-size: 1.5rem; margin-bottom: 10px;">🔒</div>
        <div>$ git commit -m "Securing the digital frontier with data-driven defense"</div>
        <div style="margin-top: 20px;">
            <span style="margin: 0 10px;">📧 network.sec@proton.me</span>
            <span style="margin: 0 10px;">🔗 github.com/cyber-analyst</span>
            <span style="margin: 0 10px;">💼 linkedin.com/in/network-engineer</span>
        </div>
        <div style="margin-top: 20px; font-size: 0.8rem;">
            © 2024 | End-to-End Data Science & Network Security Portfolio
        </div>
    </div>
</div>

<script>
    // Network Visualization with Canvas
    const canvas = document.getElementById('networkCanvas');
    const ctx = canvas.getContext('2d');
    
    function resizeCanvas() {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    }
    resizeCanvas();
    window.addEventListener('resize', resizeCanvas);

    // Nodes for network visualization
    const nodes = [];
    const numNodes = 30;
    
    for (let i = 0; i < numNodes; i++) {
        nodes.push({
            x: Math.random() * canvas.width,
            y: Math.random() * canvas.height,
            vx: (Math.random() - 0.5) * 0.5,
            vy: (Math.random() - 0.5) * 0.5,
            radius: 3 + Math.random() * 4
        });
    }

    function drawNetwork() {
        if (!ctx) return;
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        // Draw connections
        ctx.strokeStyle = 'rgba(0, 255, 65, 0.2)';
        ctx.lineWidth = 1;
        
        for (let i = 0; i < nodes.length; i++) {
            for (let j = i + 1; j < nodes.length; j++) {
                const dx = nodes[i].x - nodes[j].x;
                const dy = nodes[i].y - nodes[j].y;
                const dist = Math.sqrt(dx * dx + dy * dy);
                
                if (dist < 150) {
                    ctx.beginPath();
                    ctx.moveTo(nodes[i].x, nodes[i].y);
                    ctx.lineTo(nodes[j].x, nodes[j].y);
                    ctx.stroke();
                    
                    // Attack flash effect on random connections
                    if (Math.random() < 0.01) {
                        ctx.strokeStyle = '#ff0040';
                        ctx.lineWidth = 2;
                        ctx.beginPath();
                        ctx.moveTo(nodes[i].x, nodes[i].y);
                        ctx.lineTo(nodes[j].x, nodes[j].y);
                        ctx.stroke();
                        ctx.strokeStyle = 'rgba(0, 255, 65, 0.2)';
                        ctx.lineWidth = 1;
                    }
                }
            }
        }
        
        // Draw nodes
        for (const node of nodes) {
            ctx.beginPath();
            ctx.arc(node.x, node.y, node.radius, 0, Math.PI * 2);
            ctx.fillStyle = '#00ff41';
            ctx.fill();
            ctx.shadowBlur = 10;
            ctx.shadowColor = '#00ff41';
        }
        
        // Update positions
        for (const node of nodes) {
            node.x += node.vx;
            node.y += node.vy;
            
            if (node.x < 0 || node.x > canvas.width) node.vx *= -1;
            if (node.y < 0 || node.y > canvas.height) node.vy *= -1;
        }
        
        requestAnimationFrame(drawNetwork);
    }
    
    drawNetwork();

    // Matrix Rain Effect
    function createMatrixRain() {
        const container = document.getElementById('matrixRain');
        const columns = Math.floor(window.innerWidth / 20);
        
        for (let i = 0; i < columns; i++) {
            const column = document.createElement('div');
            column.style.cssText = `
                position: absolute;
                left: ${i * 20}px;
                top: 0;
                color: #00ff41;
                font-family: monospace;
                font-size: 14px;
                opacity: 0.3;
                animation: matrixFall ${5 + Math.random() * 5}s linear infinite;
                animation-delay: ${Math.random() * 5}s;
            `;
            
            let content = '';
            for (let j = 0; j < 30; j++) {
                content += Math.random() > 0.5 ? '1' : '0';
                if (j % 5 === 0) content += '<br/>';
            }
            column.innerHTML = content;
            container.appendChild(column);
        }
    }
    
    const style = document.createElement('style');
    style.textContent = `
        @keyframes matrixFall {
            0% { transform: translateY(-100%); }
            100% { transform: translateY(100vh); }
        }
    `;
    document.head.appendChild(style);
    createMatrixRain();

    // Binary Stream Animation
    function generateBinaryStream() {
        const streamDiv = document.getElementById('binaryStream');
        const columns = 4;
        
        setInterval(() => {
            let html = '';
            for (let i = 0; i < columns; i++) {
                html += '<div class="binary-column">';
                for (let j = 0; j < 20; j++) {
                    const binary = Math.random() > 0.5 ? '1' : '0';
                    const color = Math.random() > 0.7 ? '#ff0040' : '#00ff41';
                    html += `<span style="color: ${color};">${binary}</span> `;
                    if (Math.random() > 0.7) html += '<br/>';
                }
                html += '</div>';
            }
            streamDiv.innerHTML = html;
        }, 500);
    }
    
    generateBinaryStream();

    // Animated Threat Counter
    let threatCount = 1247;
    setInterval(() => {
        threatCount += Math.floor(Math.random() * 5);
        document.getElementById('threatCount').innerText = threatCount.toLocaleString();
    }, 3000);

    // Data Processed Counter
    let dataProcessed = 2.5;
    setInterval(() => {
        dataProcessed += (Math.random() * 0.3);
        document.getElementById('dataProcessed').innerText = dataProcessed.toFixed(1);
    }, 4000);

    // Cursor Trail Effect
    const cursor = document.getElementById('cursor');
    document.addEventListener('mousemove', (e) => {
        cursor.style.left = e.clientX - 10 + 'px';
        cursor.style.top = e.clientY - 10 + 'px';
    });

    // Create attack lines dynamically
    function createAttackLine() {
        const attackVis = document.querySelector('.attack-visualization');
        const nodes = document.querySelectorAll('.node');
        
        if (nodes.length >= 2) {
            const line = document.createElement('div');
            line.className = 'attack-line';
            const rect1 = nodes[0].getBoundingClientRect();
            const rect2 = nodes[1].getBoundingClientRect();
            
            line.style.position = 'absolute';
            line.style.left = rect1.right + 'px';
            line.style.top = rect1.top + rect1.height / 2 + 'px';
            line.style.width = '0px';
            line.style.height = '2px';
            line.style.background = 'linear-gradient(90deg, #ff0040, #00ff41)';
            
            document.body.appendChild(line);
            
            setTimeout(() => {
                line.style.width = (rect2.left - rect1.right) + 'px';
                line.style.transition = 'width 0.5s linear';
            }, 10);
            
            setTimeout(() => line.remove(), 600);
        }
    }
    
    setInterval(createAttackLine, 2000);

    // Console welcome message
    console.log('%c🔒 NETWORK SECURITY ENGINEER | DATA SCIENTIST 🔒', 'color: #00ff41; font-size: 16px; font-weight: bold;');
    console.log('%c>_ Active threat monitoring engaged | 1,247 threats neutralized', 'color: #00ff41; font-size: 12px;');
    console.log('%c>_ Data Science Portfolio: Social Media Analysis | Titanic | Web Scraping', 'color: #00ff41; font-size: 12px;');

    // Particle effect for network attacks
    function createParticle(x, y) {
        const particle = document.createElement('div');
        particle.style.cssText = `
            position: fixed;
            left: ${x}px;
            top: ${y}px;
            width: 4px;
            height: 4px;
            background: #ff0040;
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            animation: particleExplode 1s ease-out forwards;
        `;
        document.body.appendChild(particle);
        setTimeout(() => particle.remove(), 1000);
    }
    
    const particleStyle = document.createElement('style');
    particleStyle.textContent = `
        @keyframes particleExplode {
            0% { transform: scale(1); opacity: 1; }
            100% { transform: scale(10); opacity: 0; }
        }
    `;
    document.head.appendChild(particleStyle);
    
    // Random particle generation
    setInterval(() => {
        if (Math.random() > 0.7) {
            const x = Math.random() * window.innerWidth;
            const y = Math.random() * window.innerHeight;
            createParticle(x, y);
        }
    }, 500);
</script>

</body>
</html>
