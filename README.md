📹 # Pedestrian Cam — rilevamento pedoni in tempo reale con YOLOv8

Pedestrian Cam è un semplice progetto dimostrativo che usa Ultralytics YOLOv8 per individuare pedoni all’interno di un flusso video (web‑cam o file). Il notebook pedestrian_cam.ipynb mostra passo‑passo come installare i pacchetti necessari, caricare il modello e visualizzare le bounding box in sovra‑impressione, il tutto in (quasi) real‑time.

Perché yolov8n? È il modello più leggero della famiglia, quindi gira agevolmente anche su CPU e su GPU di fascia media pur mantenendo una buona accuratezza.

✨ # Caratteristiche

⚡️ Inference tempo‑reale (≈ 30 fps su GPU consumer)

👣 Focalizzato sulla classe person

🎥 Supporto sia a file video (data/sidewalk.mp4) sia a web‑cam

🔧 Parametri facilmente modificabili (conf, imgsz, modello, ecc.)

🧰 # Requisiti

Software Versione consigliata

Python ≥ 3.9

Ultralytics ≥ 8.2

OpenCV ≥ 4.9

(Opz.) PyTorch + CUDA ≥ 2.2 / CUDA 12.1

Se non usi una GPU NVIDIA puoi ignorare PyTorch/CUDA: YOLOv8 funziona anche soltanto su CPU (più lento).

🚀 Installazione
# 1. Clona il repo
git clone https://github.com/<tuo‑utente>/pedestrian‑cam.git
cd pedestrian‑cam

# 2. Crea un ambiente virtuale (opzionale ma consigliato)
python -m venv .venv
source .venv/bin/activate   # su Windows: .venv\Scripts\activate

# 3. Installa le dipendenze
pip install -r requirements.txt
