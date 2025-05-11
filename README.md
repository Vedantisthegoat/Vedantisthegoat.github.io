# Trash Detection Models

---

## Model 1: Basic Real-Time Trash Detection with Dynamic Captions

### Description:
This model uses the YOLOv8n object detection model to detect common trash items (like bottles, cups, paper, and chip bags) and displays dynamic captions based on what it detects. It also includes a basic GUI using Tkinter.

### Features:
- Detects trash objects in real-time video feed.
- Displays a caption based on the object detected.
- GUI buttons for setup and AI cleaning.

### Python Code:
```python
import tkinter as tk
from tkinter import messagebox
import cv2
import threading
import time
from PIL import Image, ImageTk
from ultralytics import YOLO

# Load YOLOv8 model
model = YOLO("yolov8n.pt")

# Trash labels you want to track and outline
TRASH_LABELS = {"bottle", "cup", "paper", "chips"}

# Captions to display for each object
CAPTIONS = {
    "bottle": "Let's recycle that bottle to help the environment!",
    "cup": "That cup looks like it belongs in the recycling bin.",
    "paper": "Let's throw away that crumpled up paper.",
    "chips": "You see that chip bag? Let's recycle it!"
}

# Global variables
cap = None
is_camera_running = False
video_source = 0
last_caption_time = 0
current_caption = "No litter detected. Good job!"

def detect_objects_yolo(frame):
    results = model.predict(frame, imgsz=640, verbose=False)[0]
    labels = model.model.names
    detected = []
    boxes = []

    if results.boxes is not None:
        for box in results.boxes:
            cls_id = int(box.cls[0])
            label = labels.get(cls_id, "unknown")
            if label in TRASH_LABELS:
                detected.append(label)
                xyxy = box.xyxy[0].tolist()
                boxes.append((label, xyxy))

    return detected, boxes

def start_setup():
    steps = [
        "Step 1: Initializing system...",
        "Step 2: Checking camera...",
        "Step 3: Verifying hardware...",
        "Step 4: Configuring environment...",
        "Step 5: Loading AI models...",
        "Step 6: Setting up video feed...",
        "Step 7: Connecting sensors...",
        "Step 8: Calibration...",
        "Step 9: System ready...",
        "Step 10: Setup complete!"
    ]
    for step in steps:
        progress_label.config(text=step)
        root.update()
        time.sleep(0.5)
    messagebox.showinfo("Setup", "Setup complete!")

def show_camera_feed():
    global cap, is_camera_running, last_caption_time, current_caption
    cap = cv2.VideoCapture(video_source)

    if not cap.isOpened():
        messagebox.showerror("Error", "Could not open camera.")
        return

    is_camera_running = True

    while is_camera_running:
        ret, frame = cap.read()
        if not ret:
            break

        detected_objects, trash_boxes = detect_objects_yolo(frame)

        now = time.time()
        if detected_objects and (now - last_caption_time) > 3:
            for obj in detected_objects:
                if obj in CAPTIONS:
                    current_caption = CAPTIONS[obj]
                    last_caption_time = now
                    break
        elif (now - last_caption_time) > 3:
            current_caption = "No litter detected. Good job!"

        # Draw only trash bounding boxes
        for label, box in trash_boxes:
            x1, y1, x2, y2 = map(int, box)
            cv2.rectangle(frame, (x1, y1), (x2, y2), (0, 255, 0), 2)
            cv2.putText(frame, label, (x1, y1 - 10), cv2.FONT_HERSHEY_SIMPLEX,
                        0.6, (0, 255, 0), 2)

        # Draw caption
        cv2.putText(frame, current_caption, (10, 30), cv2.FONT_HERSHEY_SIMPLEX,
                    0.7, (255, 255, 255), 2)

        frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
        img = Image.fromarray(frame_rgb)
        imgtk = ImageTk.PhotoImage(image=img)

        video_label.imgtk = imgtk
        video_label.configure(image=imgtk)
        video_label.update_idletasks()
        time.sleep(0.03)

    cap.release()
    cv2.destroyAllWindows()

def stop_camera_feed():
    global is_camera_running
    is_camera_running = False

def clean_environment():
    messagebox.showinfo("AI", "AI is cleaning the environment...")

def on_start_camera_feed():
    threading.Thread(target=show_camera_feed, daemon=True).start()

def on_close():
    global is_camera_running
    is_camera_running = False
    if cap is not None:
        cap.release()
    cv2.destroyAllWindows()
    root.destroy()

# --- GUI Setup ---
root = tk.Tk()
root.title("AI Cleanup Assistant")
root.geometry("800x600")
root.configure(bg="lightblue")
root.protocol("WM_DELETE_WINDOW", on_close)

# Setup frame
setup_frame = tk.Frame(root, bg="white")
setup_frame.pack(pady=10)

progress_label = tk.Label(setup_frame, text="Ready to start setup", font=("Comic Sans MS", 14), bg="white")
progress_label.pack()

setup_button = tk.Button(setup_frame, text="Start Setup", command=start_setup)
setup_button.pack(pady=10)

# Camera frame
camera_frame = tk.Frame(root, bg="lightblue")
camera_frame.pack(pady=10)

video_label = tk.Label(camera_frame)
video_label.pack()

camera_button = tk.Button(camera_frame, text="Start Camera Feed", command=on_start_camera_feed)
camera_button.pack(pady=5)

stop_button = tk.Button(camera_frame, text="Stop Camera Feed", command=stop_camera_feed)
stop_button.pack(pady=5)

# AI frame
ai_frame = tk.Frame(root, bg="white")
ai_frame.pack(pady=10)

clean_button = tk.Button(ai_frame, text="Start AI Environment Cleaning", command=clean_environment)
clean_button.pack(pady=10)

exit_button = tk.Button(root, text="Exit", command=on_close)
exit_button.pack(pady=10)

# Start the GUI
root.mainloop()
```

### How It Works:
- Loads YOLOv8n and detects trash objects.
- Captures webcam feed, performs detection.
- Updates GUI with bounding boxes and dynamic captions.

---

## More models coming soon...

Would you like to continue with Model 2 now?
