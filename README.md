# Jaifonwebos
## 🤝 Comunidad y Colaboración
Actualmente, el Cuartel General de Pear está en fase de despliegue. 

Para participar en la investigación:
1. **GitHub Issues:** Si encuentras un error en el código, ábrelo aquí mismo en la pestaña "Issues".
2. **Pull Requests:** Si tienes una mejora lista, envíala directamente para revisión del CEO.
3. **Próximamente:** El foro oficial `www.pear/jaifonwebos/forum.com` y la web principal estarán disponibles para el lanzamiento del 20 de mayo.
### codigo jaifonwebos CONSULTAR PARA HACER CAMBIOS EL CÓDIGO ACTUAL ES SOLO UN INDEX.HTML
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Jaifon OS - Pear Ecosystem</title>
    <style>
        :root {
            --pear-copper: #b87333; /* El color de tu investigación */
            --bg-black: #000000;
            --glass: rgba(255, 255, 255, 0.05);
        }

        body, html {
            margin: 0; padding: 0;
            height: 100%; width: 100%;
            background-color: var(--bg-black);
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            color: white; overflow: hidden;
            user-select: none; -webkit-tap-highlight-color: transparent;
        }

        /* Escritorio Minimalista */
        #desktop {
            height: 100vh;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-template-rows: repeat(6, 1fr);
            padding: 40px 20px;
            gap: 20px;
        }

        .app-node {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .icon-box {
            width: 65px;
            height: 65px;
            background: var(--glass);
            border: 1px solid #222;
            border-radius: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 28px;
            transition: 0.2s;
        }

        .icon-box:active {
            transform: scale(0.9);
            border-color: var(--pear-copper);
            background: rgba(184, 115, 51, 0.1);
        }

        .label {
            margin-top: 8px;
            font-size: 12px;
            font-weight: 300;
            color: #888;
        }

        /* Barra de Estado Superior */
        #top-bar {
            position: fixed;
            top: 0; width: 100%;
            height: 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
            font-size: 13px;
            font-weight: bold;
            background: linear-gradient(to bottom, rgba(0,0,0,0.8), transparent);
        }

        /* Dock Inferior */
        #dock {
            position: fixed;
            bottom: 25px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            height: 75px;
            background: rgba(15, 15, 15, 0.7);
            backdrop-filter: blur(15px);
            border-radius: 25px;
            border: 1px solid rgba(255,255,255,0.05);
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        /* Ventanas de App */
        .window {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: var(--bg-black);
            display: none;
            flex-direction: column;
            z-index: 200;
            animation: slideUp 0.3s ease-out;
        }

        @keyframes slideUp {
            from { transform: translateY(100%); }
            to { transform: translateY(0); }
        }

        .win-header {
            padding: 40px 20px 20px;
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #111;
        }

        .close-btn { color: var(--pear-copper); font-size: 20px; font-weight: bold; }
    </style>
</head>
<body>

    <div id="top-bar">
        <span id="brand">PEAR 🍐</span>
        <span id="clock">00:00</span>
    </div>

    <div id="desktop">
        <div class="app-node" onclick="openApp('lab')">
            <div class="icon-box">🧪</div>
            <div class="label">Laboratorio</div>
        </div>
        <div class="app-node" onclick="openApp('store')">
            <div class="icon-box">🍐</div>
            <div class="label">Pear Store</div>
        </div>
    </div>

    <div id="dock">
        <div onclick="haptic()">📞</div>
        <div onclick="haptic()">💬</div>
        <div onclick="haptic()">🌐</div>
        <div onclick="haptic()">⚙️</div>
    </div>

    <div id="lab-window" class="window">
        <div class="win-header">
            <span>PEAR RESEARCH LAB</span>
            <span class="close-btn" onclick="closeApp('lab')">Cerrar</span>
        </div>
        <div style="padding: 30px;">
            <h2 style="color: var(--pear-copper);">Módulo: Jaifon OS</h2>
            <p>Estado de investigación: Activo</p>
            <hr style="border: 0.5px solid #222;">
            <p>> Detectando Hardware: S9 Series</p>
            <p>> Optimizando para pantalla AMOLED...</p>
            <p>> Cinta de cobre detectada: Sí</p>
        </div>
    </div>

    <script>
        // Reloj de alta precisión
        function updateClock() {
            const now = new Date();
            const hours = now.getHours().toString().padStart(2, '0');
            const minutes = now.getMinutes().toString().padStart(2, '0');
            document.getElementById('clock').textContent = hours + ":" + minutes;
        }
        setInterval(updateClock, 1000);
        updateClock();

        // Respuesta Háptica (Vibración de Pear)
        function haptic() {
            if ("vibrate" in navigator) {
                navigator.vibrate(15);
            }
        }

        function openApp(id) {
            haptic();
            document.getElementById(id + '-window').style.display = 'flex';
        }

        function closeApp(id) {
            haptic();
            document.getElementById(id + '-window').style.display = 'none';
        }

        // Bloqueo preventivo de salida
        history.pushState(null, null, location.href);
        window.onpopstate = function () { history.go(1); };
    </script>
</body>
</html>
