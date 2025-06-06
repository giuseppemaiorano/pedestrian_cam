# Pedestrian Cam — rilevamento pedoni in tempo reale con YOLOv8

<img width="794" alt="pedestrian_cam" src="https://github.com/user-attachments/assets/10c67db9-6be7-48cb-b7b9-c4a15f60a925" />

Pedestrian Cam è un semplice progetto dimostrativo che usa Ultralytics YOLOv8 per individuare pedoni all’interno di un flusso video (web‑cam o file). Il notebook pedestrian_cam.ipynb mostra passo‑passo come installare i pacchetti necessari, caricare il modello e visualizzare le bounding box in sovra‑impressione, il tutto in (quasi) real‑time.

Perché yolov8n? È il modello più leggero della famiglia, quindi gira agevolmente anche su CPU e su GPU di fascia media pur mantenendo una buona accuratezza

##  Caratteristiche

⚡️ Inference tempo‑reale (≈ 30 fps su GPU consumer)

👣 Focalizzato sulla classe person

🎥 Supporto sia a file video (data/sidewalk.mp4) sia a web‑cam

🔧 Parametri facilmente modificabili (conf, imgsz, modello, ecc.)

 ## Requisiti

Software Versione consigliata

Python ≥ 3.9

Ultralytics ≥ 8.2

OpenCV ≥ 4.9

(Opz.) PyTorch + CUDA ≥ 2.2 / CUDA 12.1

Se non usi una GPU NVIDIA puoi ignorare PyTorch/CUDA: YOLOv8 funziona anche soltanto su CPU (più lento).

## Installazione
#### 1. Clona il repo
git clone https://github.com/giuseppemaiorano/pedestrian‑cam.git
cd pedestrian‑cam

#### 2. Crea un ambiente virtuale (opzionale ma consigliato)
python -m venv .venv
source .venv/bin/activate   # su Windows: .venv\Scripts\activate

#### 3. Installa le dipendenze
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

<img width="397" alt="image" src="https://github.com/user-attachments/assets/cef52190-56e5-4bf0-b2cb-30d34a8c3b0e" />

## Struttura del progetto
<img width="385" alt="image" src="https://github.com/user-attachments/assets/23a1af87-0bc4-484a-a9a5-70e220e0efdd" />

## Personalizzazione rapida
<img width="395" alt="image" src="https://github.com/user-attachments/assets/9cf67019-5d9e-4eb0-bf89-c9515f501434" />

##  Performance attese
<img width="319" alt="image" src="https://github.com/user-attachments/assets/ecb8ea08-67a9-4d7d-bb6a-2c121be2291c" />
I valori sono indicativi: cambiano in base a driver, risoluzione e carico di sistema.

## Licenza
Distribuito sotto licenza MIT. Puoi usarlo, modificarlo e ridistribuirlo liberamente citando l’autore originale.

## Ringraziamenti
Ultralytics per il fantastico YOLOv8
OpenCV per l’ecosistema computer‑vision
