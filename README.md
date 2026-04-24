<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NeoTune WebApp</title>

<style>
html, body {
    margin: 0;
    padding: 0;
    height: 100%;
    background: #000;
    font-family: Arial;
}

#topbar {
    height: 50px;
    background: #1db954;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 10px;
    color: white;
    font-weight: bold;
}

#frame {
    width: 100%;
    height: calc(100% - 50px);
    border: none;
}

button {
    background: white;
    border: none;
    padding: 5px 10px;
    border-radius: 5px;
}
</style>
</head>

<body>

<div id="topbar">
    NeoTune
    <button onclick="reload()">⟳</button>
</div>

<iframe id="frame"
    src="https://www.lncc.br/~borges/php/testar.html">
</iframe>

<script>
function reload() {
    document.getElementById("frame").src =
        document.getElementById("frame").src;
}

/* Fallback se o site bloquear iframe */
setTimeout(() => {
    try {
        const frame = document.getElementById("frame");
        if (!frame.contentWindow || frame.contentWindow.length === 0) {
            window.location.href = frame.src;
        }
    } catch (e) {
        window.location.href = "https://www.lncc.br/~borges/php/testar.html";
    }
}, 3000);
</script>

</body>
</html>