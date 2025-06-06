# Pedestrian Cam — rilevamento pedoni in tempo reale con YOLOv8

<img width="794" alt="pedestrian_cam" src="https://github.com/user-attachments/assets/10c67db9-6be7-48cb-b7b9-c4a15f60a925" />

Pedestrian Cam è un semplice progetto dimostrativo che usa Ultralytics YOLOv8 per individuare pedoni all’interno di un flusso video (web‑cam o file). Il notebook pedestrian_cam.ipynb mostra passo‑passo come installare i pacchetti necessari, caricare il modello e visualizzare le bounding box in sovra‑impressione, il tutto in (quasi) real‑time.

Perché yolov8n? È il modello più leggero della famiglia, quindi gira agevolmente anche su CPU e su GPU di fascia media pur mantenendo una buona accuratezza

##  Caratteristiche

⚡️ Inference tempo‑reale (≈ 30 fps su GPU consumer)

👣 Focalizzato sulla classe person

🎥 Supporto sia a file video (data/sidewalk.mp4) sia a web‑cam

🔧 Parametri facilmente modificabili (conf, imgsz, modello, ecc.)

## Requisiti

Software Versione consigliata

Python ≥ 3.9

Ultralytics ≥ 8.2

OpenCV ≥ 4.9

(Opz.) PyTorch + CUDA ≥ 2.2 / CUDA 12.1

Se non usi una GPU NVIDIA puoi ignorare PyTorch/CUDA: YOLOv8 funziona anche soltanto su CPU (più lento).

## Installazione
#### 1. Clona il repo
git clone https://github.com/<tuo‑utente>/pedestrian‑cam.git
cd pedestrian‑cam

# 2. Crea un ambiente virtuale (opzionale ma consigliato)
python -m venv .venv
source .venv/bin/activate   # su Windows: .venv\Scripts\activate

# 3. Installa le dipendenze
pip install -r requirements.txt

Se non vuoi usare requirements.txt, puoi installare "a mano":
pip install ultralytics opencv-python

## Come si usa
### 1. Notebook Jupyter (consigliato per la prima prova)
Apri pedestrian_cam.ipynb e segui le celle dall’alto verso il basso.
Imposta video_path su data/sidewalk.mp4 oppure 0 per la web‑cam.
Regola conf=0.35 se vuoi più/meno rilevamenti.

### 2. Esecuzione da terminale (facoltativa)
Se preferisci un file .py, copia/incolla il cuore del loop:

from ultralytics import YOLO
import cv2, time

model = YOLO("yolov8n.pt")
cap = cv2.VideoCapture(0)  # 0 = web‑cam di default

while True:
    ret, frame = cap.read()
    if not ret:
        break

    annotated = model(frame, imgsz=640, conf=0.35)[0].plot()
    cv2.imshow("Pedestrian‑Cam", annotated)
    if cv2.waitKey(1) & 0xFF == 27:  # ESC
        break
