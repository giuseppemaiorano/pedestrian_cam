# Pedestrian Cam — rilevamento pedoni in tempo reale con YOLOv8

<img width="794" alt="pedestrian_cam" src="https://github.com/user-attachments/assets/10c67db9-6be7-48cb-b7b9-c4a15f60a925" />

Pedestrian Cam è un semplice progetto dimostrativo che usa Ultralytics YOLOv8 per individuare pedoni all’interno di un flusso video (web‑cam o file). Il notebook pedestrian_cam.ipynb mostra passo‑passo come installare i pacchetti necessari, caricare il modello e visualizzare le bounding box in sovra‑impressione, il tutto in (quasi) real‑time.

Perché yolov8n? È il modello più leggero della famiglia, quindi gira agevolmente anche su CPU e su GPU di fascia media pur mantenendo una buona accuratezza

#  Caratteristiche

⚡️ Inference tempo‑reale (≈ 30 fps su GPU consumer)

👣 Focalizzato sulla classe person

🎥 Supporto sia a file video (data/sidewalk.mp4) sia a web‑cam

🔧 Parametri facilmente modificabili (conf, imgsz, modello, ecc.)
