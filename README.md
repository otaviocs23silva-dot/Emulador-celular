<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emulador de Teclas - Web</title>
    <style>
        :root {
            --bg-color: #0f172a;
            --panel-bg: #1e293b;
            --primary: #3b82f6;
            --primary-hover: #2563eb;
            --text-color: #f8fafc;
            --muted-color: #94a3b8;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .emulator-card {
            background-color: var(--panel-bg);
            border: 1px solid #334155;
            padding: 24px;
            border-radius: 16px;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3);
            width: 320px;
            text-align: center;
        }

        h2 {
            margin-top: 0;
            font-size: 1.25rem;
            margin-bottom: 20px;
            color: #e2e8f0;
        }

        .controls-grid {
            display: flex;
            flex-direction: column;
            gap: 12px;
            align-items: center;
        }

        .btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 20px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s ease;
            width: 100%;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.2);
        }

        .btn:hover {
            background-color: var(--primary-hover);
            transform: translateY(-1px);
        }

        .btn:active {
            transform: translateY(1px);
            box-shadow: none;
        }

        .btn-space {
            width: 100%;
            background-color: #10b981;
        }

        .btn-space:hover {
            background-color: #059669;
        }

        .log-box {
            margin-top: 20px;
            background-color: #0f172a;
            border: 1px solid #334155;
            border-radius: 6px;
            padding: 10px;
            font-family: monospace;
            font-size: 0.85rem;
            height: 60px;
            overflow-y: auto;
            text-align: left;
            color: var(--muted-color);
        }
    </style>
</head>
<body>

    <div class="emulator-card">
        <h2>Emulador de Teclas (Web)</h2>
        <div class="controls-grid">
            <button class="btn" onclick="emulaTecla('W', 'ArrowUp')">W (Cima)</button>
            <div style="display: flex; gap: 10px; width: 100%;">
                <button class="btn" onclick="emulaTecla('A', 'ArrowLeft')">A (Esq)</button>
                <button class="btn" onclick="emulaTecla('S', 'ArrowDown')">S (Baixo)</button>
                <button class="btn" onclick="emulaTecla('D', 'ArrowRight')">D (Dir)</button>
            </div>
            <button class="btn btn-space" onclick="emulaTecla('ESPAÇO', ' ')">ESPAÇO (Ação)</button>
        </div>
        
        <div id="logBox" class="log-box">Aguardando ações...</div>
    </div>

    <script>
        function emulaTecla(nomeTecla, codigoKey) {
            const logBox = document.getElementById('logBox');
            logBox.innerHTML = `Tecla ${nomeTecla} emulada com sucesso!<br>` + logBox.innerHTML;
            
            // Simula o evento de teclado no documento atual para fins de demonstração
            const event = new KeyboardEvent('keydown', { key: codigoKey });
            document.dispatchEvent(event);
            
            console.log(`Tecla ${nomeTecla} acionada.`);
        }
    </script>

</body>
</html>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emulador de Teclas - Web</title>
    <style>
        :root {
            --bg-color: #0f172a;
            --panel-bg: #1e293b;
            --primary: #3b82f6;
            --primary-hover: #2563eb;
            --text-color: #f8fafc;
            --muted-color: #94a3b8;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .emulator-card {
            background-color: var(--panel-bg);
            border: 1px solid #334155;
            padding: 24px;
            border-radius: 16px;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3);
            width: 320px;
            text-align: center;
        }

        h2 {
            margin-top: 0;
            font-size: 1.25rem;
            margin-bottom: 20px;
            color: #e2e8f0;
        }

        .controls-grid {
            display: flex;
            flex-direction: column;
            gap: 12px;
            align-items: center;
        }

        .btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 20px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s ease;
            width: 100%;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.2);
        }

        .btn:hover {
            background-color: var(--primary-hover);
            transform: translateY(-1px);
        }

        .btn:active {
            transform: translateY(1px);
            box-shadow: none;
        }

        .btn-space {
            width: 100%;
            background-color: #10b981;
        }

        .btn-space:hover {
            background-color: #059669;
        }

        .log-box {
            margin-top: 20px;
            background-color: #0f172a;
            border: 1px solid #334155;
            border-radius: 6px;
            padding: 10px;
            font-family: monospace;
            font-size: 0.85rem;
            height: 60px;
            overflow-y: auto;
            text-align: left;
            color: var(--muted-color);
        }
    </style>
</head>
<body>

    <div class="emulator-card">
        <h2>Emulador de Teclas (Web)</h2>
        <div class="controls-grid">
            <button class="btn" onclick="emulaTecla('W', 'ArrowUp')">W (Cima)</button>
            <div style="display: flex; gap: 10px; width: 100%;">
                <button class="btn" onclick="emulaTecla('A', 'ArrowLeft')">A (Esq)</button>
                <button class="btn" onclick="emulaTecla('S', 'ArrowDown')">S (Baixo)</button>
                <button class="btn" onclick="emulaTecla('D', 'ArrowRight')">D (Dir)</button>
            </div>
            <button class="btn btn-space" onclick="emulaTecla('ESPAÇO', ' ')">ESPAÇO (Ação)</button>
        </div>
        
        <div id="logBox" class="log-box">Aguardando ações...</div>
    </div>

    <script>
        function emulaTecla(nomeTecla, codigoKey) {
            const logBox = document.getElementById('logBox');
            logBox.innerHTML = `Tecla ${nomeTecla} emulada com sucesso!<br>` + logBox.innerHTML;
            
            // Simula o evento de teclado no documento atual para fins de demonstração
            const event = new KeyboardEvent('keydown', { key: codigoKey });
            document.dispatchEvent(event);
            
            console.log(`Tecla ${nomeTecla} acionada.`);
        }
    </script>

</body>
</html>
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emulador de Teclas - Web</title>
    <style>
        :root {
            --bg-color: #0f172a;
            --panel-bg: #1e293b;
            --primary: #3b82f6;
            --primary-hover: #2563eb;
            --text-color: #f8fafc;
            --muted-color: #94a3b8;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .emulator-card {
            background-color: var(--panel-bg);
            border: 1px solid #334155;
            padding: 24px;
            border-radius: 16px;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3);
            width: 320px;
            text-align: center;
        }

        h2 {
            margin-top: 0;
            font-size: 1.25rem;
            margin-bottom: 20px;
            color: #e2e8f0;
        }

        .controls-grid {
            display: flex;
            flex-direction: column;
            gap: 12px;
            align-items: center;
        }

        .btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 20px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s ease;
            width: 100%;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.2);
        }

        .btn:hover {
            background-color: var(--primary-hover);
            transform: translateY(-1px);
        }

        .btn:active {
            transform: translateY(1px);
            box-shadow: none;
        }

        .btn-space {
            width: 100%;
            background-color: #10b981;
        }

        .btn-space:hover {
            background-color: #059669;
        }

        .log-box {
            margin-top: 20px;
            background-color: #0f172a;
            border: 1px solid #334155;
            border-radius: 6px;
            padding: 10px;
            font-family: monospace;
            font-size: 0.85rem;
            height: 60px;
            overflow-y: auto;
            text-align: left;
            color: var(--muted-color);
        }
    </style>
</head>
<body>

    <div class="emulator-card">
        <h2>Emulador de Teclas (Web)</h2>
        <div class="controls-grid">
            <button class="btn" onclick="emulaTecla('W', 'ArrowUp')">W (Cima)</button>
            <div style="display: flex; gap: 10px; width: 100%;">
                <button class="btn" onclick="emulaTecla('A', 'ArrowLeft')">A (Esq)</button>
                <button class="btn" onclick="emulaTecla('S', 'ArrowDown')">S (Baixo)</button>
                <button class="btn" onclick="emulaTecla('D', 'ArrowRight')">D (Dir)</button>
            </div>
            <button class="btn btn-space" onclick="emulaTecla('ESPAÇO', ' ')">ESPAÇO (Ação)</button>
        </div>
        
        <div id="logBox" class="log-box">Aguardando ações...</div>
    </div>

    <script>
        function emulaTecla(nomeTecla, codigoKey) {
            const logBox = document.getElementById('logBox');
            logBox.innerHTML = `Tecla ${nomeTecla} emulada com sucesso!<br>` + logBox.innerHTML;
            
            // Simula o evento de teclado no documento atual para fins de demonstração
            const event = new KeyboardEvent('keydown', { key: codigoKey });
            document.dispatchEvent(event);
            
            console.log(`Tecla ${nomeTecla} acionada.`);
        }
    </script>

</body>
</html>
