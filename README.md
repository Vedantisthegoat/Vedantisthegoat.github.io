<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>EcoLens AI</title>
  <style>
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
      margin: 0;
      padding: 0;
      background: linear-gradient(to right, white 50%, #b3e0ff 50%);
      color: #333;
    }
    .container {
      width: 80%;
      margin: auto;
      padding: 40px;
    }
    h1 {
      font-size: 3em;
      color: #2a7dab;
    }
    h2 {
      color: #2a7dab;
      margin-top: 40px;
    }
    code, pre {
      background-color: #f4f4f4;
      padding: 5px 10px;
      border-radius: 4px;
      display: block;
      margin: 10px 0;
    }
    ul {
      padding-left: 20px;
    }
    .screenshot {
      width: 100%;
      max-width: 600px;
      border: 2px solid #2a7dab;
      border-radius: 8px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🌿 EcoLens AI — Real-Time Trash Detection Assistant</h1>
    <p>
      EcoLens AI is a fun, camera-powered desktop app built with Python and YOLOv8 that encourages environmental cleanup.
      It detects objects like bottles, paper, and chip bags using a live webcam and generates friendly captions like:
    </p>
    <blockquote><strong>“Let’s help the environment by throwing the trash away!”</strong></blockquote>

    <h2>🧠 Features</h2>
    <ul>
      <li>🔍 Real-time object detection using YOLOv8</li>
      <li>🎨 Playful GUI with a white/blue background</li>
      <li>📸 Live camera feed with auto-updating captions</li>
      <li>🗑️ Recognizes trash-related objects like:
        <ul>
          <li>plastic bottles</li>
          <li>cups</li>
          <li>paper</li>
          <li>chip bags</li>
        </ul>
      </li>
    </ul>

    <h2>🖥️ Requirements</h2>
    <pre><code>pip install opencv-python pillow ultralytics</code></pre>

    <h2>🚀 How to Run</h2>
    <ol>
      <li>Clone this repo or download the code.</li>
      <li>Run the script:</li>
    </ol>
    <pre><code>python ecolens_gui.py</code></pre>
    <ol start="3">
      <li>Click <strong>Start Setup</strong> → <strong>Start Camera Feed</strong> to begin.</li>
      <li>Watch real-time captions update as the AI detects objects!</li>
    </ol>

    <h2>📦 File Structure</h2>
    <pre><code>
ecolens-ai/
├── ecolens_gui.py       # Main application file
├── README.md            # This file
└── yolov8n.pt           # (auto-downloaded by Ultralytics if not present)
    </code></pre>

    <h2>🤖 Model</h2>
    <p>
      This app uses <a href="https://github.com/ultralytics/ultralytics" target="_blank">Ultralytics YOLOv8</a> (<code>yolov8n.pt</code>)
      to detect common objects. The model is automatically downloaded the first time it runs.
    </p>

    <h2>👩‍💻 Developer Notes</h2>
    <p>
      If you encounter OpenCV GUI issues on Windows, make sure you're not running the script from PowerShell.
      Use <strong>Command Prompt</strong> or run it directly from <strong>VS Code</strong>.
    </p>

    <h2>❤️ Credits</h2>
    <p>Built using:</p>
    <ul>
      <li><a href="https://github.com/ultralytics/ultralytics" target="_blank">Ultralytics YOLOv8</a></li>
      <li>OpenCV</li>
      <li>Tkinter GUI</li>
      <li>Pillow</li>
    </ul>

    <h2>📷 Example</h2>
    <img class="screenshot" src="assets/example_frame.jpg" alt="EcoLens Screenshot">

    <h2>🌍 Let’s help the environment, one detection at a time!</h2>
  </div>
</body>
</html>
