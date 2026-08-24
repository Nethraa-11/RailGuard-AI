RAILGUARD AI MODELS

This project uses TWO YOLO models on the SAME camera frame:

1. models/best.pt
   - Your trained RailGuard railway-crack detector.
   - Expected class in the supplied model: crack

2. models/yolov8n.pt
   - General-purpose YOLOv8 nano object detector.
   - Used for common-object detection.

IMPORTANT:
The ZIP contains the complete application code, but not the model binaries.
Copy your real best.pt and yolov8n.pt into this folder before running.

Windows PowerShell:
  Copy-Item "C:\path\to\best.pt" ".\models\best.pt"
  Copy-Item "C:\path\to\yolov8n.pt" ".\models\yolov8n.pt"

Use forward slashes in Python model paths, for example:
  models/best.pt

Do NOT write models\best.pt inside a Python string literal because \b is
interpreted as a backspace character.
