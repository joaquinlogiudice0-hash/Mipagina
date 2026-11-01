<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cyber Dark Card</title>
  <style>
    :root {
      --bg-color: #050508;
      --card-bg: rgba(18, 18, 26, 0.65);
      --primary: #9d4edd;
      --secondary: #ff2a6d;
      --accent: #05d9e8;
      --text-color: #ffffff;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-color);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      position: relative;
    }

    /* Fondo con partículas */
    #particle-canvas {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
    }

    /* Luces de neón de fondo */
    .glow-bg {
      position: absolute;
      width: 500px;
      height: 500px;
      border-radius: 50%;
      filter: blur(120px);
      opacity: 0.25;
      z-index: 2;
      pointer-events: none;
    }

    .glow-1 {
      top: 10%;
      left: 20%;
      background: var(--primary);
      animation: floatGlow 12s infinite alternate ease-in-out;
    }

    .glow-2 {
      bottom: 10%;
      right: 20%;
      background: var(--secondary);
      animation: floatGlow 10s infinite alternate-reverse ease-in-out;
    }

    @keyframes floatGlow {
      0% { transform: translate(0, 0) scale(1); }
      100% { transform: translate(50px, 30px) scale(1.2); }
    }

    /* Marco perimetral decorativo */
    .outer-frame {
      position: fixed;
      top: 20px;
      left: 20px;
      right: 20px;
      bottom: 20px;
      border: 1px solid rgba(255, 255, 255, 0.08);
      pointer-events: none;
      z-index: 5;
    }

    .outer-frame::before, .outer-frame::after {
      content: '';
      position: absolute;
      width: 15px;
      height: 15px;
      border: 2px solid var(--accent);
    }

    .outer-frame::before {
      top: -2px;
      left: -2px;
      border-right: none;
      border-bottom: none;
    }

    .outer-frame::after {
      bottom: -2px;
      right: -2px;
      border-left: none;
      border-top: none;
    }

    .frame-status {
      position: absolute;
      top: 15px;
      left: 25px;
      font-size: 0.75rem;
      letter-spacing: 2px;
      color: rgba(255, 255, 255, 0.4);
      font-family: monospace;
      text-transform: uppercase;
      z-index: 5;
    }

    .frame-status span {
      color: var(--accent);
      display: inline-block;
      width: 8px;
      height: 8px;
      background-color: var(--accent);
      border-radius: 50%;
      margin-right: 6px;
      box-shadow: 0 0 8px var(--accent);
    }

    /* Tarjeta central */
    .card-container {
      position: relative;
      z-index: 10;
      padding: 3px;
      border-radius: 20px;
      background: linear-gradient(135deg, rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0.02));
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.6);
      max-width: 90%;
      width: 550px;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .card-container:hover {
      transform: translateY(-5px);
      box-shadow: 0 25px 60px rgba(157, 78, 221, 0.25);
    }

    .card-content {
      background: var(--card-bg);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border-radius: 17px;
      padding: 60px 40px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    /* Detalle de esquinas de la tarjeta */
    .corner-mark {
      position: absolute;
      width: 8px;
      height: 8px;
      border: 1px solid var(--secondary);
    }

    .top-left { top: 12px; left: 12px; border-right: none; border-bottom: none; }
    .top-right { top: 12px; right: 12px; border-left: none; border-bottom: none; }
    .bottom-left { bottom: 12px; left: 12px; border-right: none; border-top: none; }
    .bottom-right { bottom: 12px; right: 12px; border-left
    
