# KeepTheSystemAwake
Short script in Python for keeping your system awake
Usage:
-- The script is pressing the "Num Lock" key every 30 sec
-- The script doesnt use any aditional packages, it uses only build in packages
Adding the code here aswell:

import ctypes
import time


# Simulate a key press to keep the computer awake
def press_key():
    ctypes.windll.user32.keybd_event(0x90, 0, 0, 0)  # Simulate pressing the 'Num Lock' key
    time.sleep(1)  # Small delay
    ctypes.windll.user32.keybd_event(0x90, 0, 2, 0)  # Release the 'Num Lock' key


def keep_awake():
    print("Keeping the system awake. Press Ctrl+C to stop.")
    try:
        while True:
            press_key()
            time.sleep(30)  # Wait 1 minute before simulating the next key press
    except KeyboardInterrupt:
        print("Program stopped.")


if __name__ == "__main__":
    keep_awake()
