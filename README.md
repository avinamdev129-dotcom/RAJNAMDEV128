<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Trivia Throne - Play & Learn</title>
    <meta name="description" content="Play Trivia Throne, the ultimate quiz game! Challenge yourself with Flags, Science, History, and Geography questions. Climb the leaderboard and earn achievements.">
    <meta name="keywords" content="trivia, quiz, game, education, flags, science, history, geography, learning, play">
    <meta name="robots" content="index, follow">
    
    <!-- Open Graph / WhatsApp Preview Tags -->
    <meta property="og:title" content="Trivia Throne - The Ultimate Quiz Game" />
    <meta property="og:description" content="Challenge your knowledge, earn rupees, and climb the leaderboard! Play now." />
    <meta property="og:image" content="https://cdn-icons-png.flaticon.com/512/861/861512.png" />
    <meta property="og:type" content="website" />
    
    <!-- PWA & Mobile Meta Tags -->
    <link rel="manifest" href="manifest.json">
    <meta name="theme-color" content="#0f172a" />
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="Trivia Throne">
    <link rel="apple-touch-icon" href="https://cdn-icons-png.flaticon.com/512/861/861512.png">

    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">

<style>
  body {
    font-family: 'Poppins', sans-serif;
    overscroll-behavior-y: none; /* Prevent pull-to-refresh on mobile */
  }
  @keyframes shake {
    0%, 100% { transform: translateX(0); }
    10%, 30%, 50%, 70%, 90% { transform: translateX(-5px); }
    20%, 40%, 60%, 80% { transform: translateX(5px); }
  }
  @keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
  }
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes shine {
    100% {
      left: 125%;
    }
  }
  
  .animate-shake {
    animation: shake 0.5s ease-in-out;
  }
  .animate-pulse {
    animation: pulse 2s infinite ease-in-out;
  }
  .animate-fade-in {
    animation: fadeIn 0.6s ease-out forwards;
  }
  .group:hover .animate-shine {
    animation: shine 1s;
  }

  /* --- New Styles --- */

  /* Animated Background */
  .animated-bg::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image:
      radial-gradient(circle at center, rgba(100, 116, 139, 0.1) 1px, transparent 1px),
      radial-gradient(circle at center, rgba(100, 116, 139, 0.1) 1px, transparent 1px);
    background-size: 40px 40px;
    background-position: 0 0, 20px 20px;
    animation: move-bg 60s linear infinite;
    z-index: 0;
  }
  @keyframes move-bg {
    0% { background-position: 0 0, 20px 20px; }
    100% { background-position: 1000px 500px, 1020px 520px; }
  }

  /* Glowing Card Border */
  .card-glow {
    position: relative;
    z-index: 1;
  }
  .card-glow::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: 1rem; /* same as rounded-2xl */
    padding: 2px; /* border thickness */
    background: linear-gradient(45deg, #22d3ee, #0e7490);
    -webkit-mask:
       linear-gradient(#fff 0 0) content-box,
       linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
            mask-composite: exclude;
    pointer-events: none;
  }

  /* Custom Scrollbar */
  ::-webkit-scrollbar {
    width: 8px;
  }
  ::-webkit-scrollbar-track {
    background: #1e293b; /* slate-800 */
    border-radius: 4px;
  }
  ::-webkit-scrollbar-thumb {
    background: #475569; /* slate-600 */
    border-radius: 4px;
  }
  ::-webkit-scrollbar-thumb:hover {
    background: #64748b; /* slate-500 */
  }
</style>
<script type="importmap">
{
  "imports": {
    "vite": "https://aistudiocdn.com/vite@^7.2.4",
    "@vitejs/plugin-react": "https://aistudiocdn.com/@vitejs/plugin-react@^5.1.1",
    "react/": "https://aistudiocdn.com/react@^19.2.0/",
    "react": "https://aistudiocdn.com/react@^19.2.0",
    "react-dom/": "https://aistudiocdn.com/react-dom@^19.2.0/",
    "@google/genai": "https://aistudiocdn.com/@google/genai@^1.30.0"
  }
}
</script>
</head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/index.tsx"></script>
    <script>
      if ('serviceWorker' in navigator) {
        window.addEventListener('load', () => {
          navigator.serviceWorker.register('sw.js').then(registration => {
            console.log('SW registered: ', registration);
          }).catch(registrationError => {
            console.log('SW registration failed: ', registrationError);
          });
        });
      }



      
    </script>
  </body>
</html>
