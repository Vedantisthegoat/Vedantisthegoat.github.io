<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interface for RGB String with Python and Tkinter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 20px;
            color: #333;
        }
        h1 {
            color: #FF5722;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        pre {
            background-color: #f2f2f2;
            padding: 15px;
            border-radius: 5px;
            font-size: 16px;
            overflow-x: auto;
        }
        footer {
            text-align: center;
            margin-top: 40px;
            font-size: 14px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Interface for RGB String</h1>
    <p>I created a project where there's an interface, and on that interface, you can type in a random string. Based on the characters you type, LED indicators light up to match them. For example, if your string includes <strong>r</strong>, the red LED will blink; if it has <strong>g</strong>, the green LED will blink; and if it has <strong>b</strong>, the blue LED will blink.</p>

    <p>This is a fun way to simulate RGB LED behavior using Python and the Tkinter library. It’s great for beginners learning about GUI applications and simulating hardware logic with software.</p>

    <h2>Python Code:</h2>
    <pre>
import tkinter as tk
import time

def process_input():
    input_string = entry.get().lower()
    # Reset LED colors
    red_led.config(bg="gray")
    green_led.config(bg="gray")
    blue_led.config(bg="gray")
    root.update()

    if 'r' in input_string:
        red_led.config(bg="red")
        root.update()
        time.sleep(1.5)
        red_led.config(bg="gray")
        root.update()
    if 'g' in input_string:
        green_led.config(bg="green")
        root.update()
        time.sleep(1.5)
        green_led.config(bg="gray")
        root.update()
    if 'b' in input_string:
        blue_led.config(bg="blue")
        root.update()
        time.sleep(1.5)
        blue_led.config(bg="gray")
        root.update()

root = tk.Tk()
root.title("LED Simulator")
root.geometry("500x500")

tk.Label(root, text="Enter a string:", font=("Arial", 18)).pack(pady=15)
entry = tk.Entry(root, font=("Arial", 18), width=25)
entry.pack(pady=10)

submit_button = tk.Button(root, text="Submit", font=("Arial", 18), command=process_input)
submit_button.pack(pady=15)

tk.Label(root, text="LED Indicators:", font=("Arial", 18)).pack(pady=15)
red_led = tk.Label(root, text="RED", bg="gray", width=15, height=3, font=("Arial", 18))
red_led.pack(pady=10)
green_led = tk.Label(root, text="GREEN", bg="gray", width=15, height=3, font=("Arial", 18))
green_led.pack(pady=10)
blue_led = tk.Label(root, text="BLUE", bg="gray", width=15, height=3, font=("Arial", 18))
blue_led.pack(pady=10)

root.mainloop()
    </pre>
</div>

<footer>
    <p>&copy; 2024 Vedant | Interface for RGB String</p>
</footer>

</body>
</html>
