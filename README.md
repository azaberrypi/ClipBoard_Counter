# ClipBoard_Counter

A lightweight Windows application that counts the number of characters currently copied to the clipboard. Built using the native Windows API in C.

## Features

* **Quick Counting**: Instantly find out the exact character count of your clipboard text.
* **Simple UI**: A minimalistic interface featuring a single "Count" button and a display box.
* **Global Hotkey**: Press `Ctrl + Enter` to instantly count and display the clipboard characters without needing to click the application.
* **Always on Top**: The application window stays on top of other windows for easy and quick access.
* **Lightweight**: Written entirely in C using the Win32 API, ensuring minimal resource usage.

## Usage

1. Launch the application.
2. Copy any text to your clipboard (e.g., using `Ctrl + C`).
3. Click the **Count** button on the application window, OR press the global hotkey `Ctrl + Enter`.
4. The application will display the number of characters in the text box. 
   *(Note: If the clipboard does not contain valid text, it will display `UNCOUNTABLE`.)*

## Architecture details

- Uses `OpenClipboard()` and `GetClipboardData(CF_UNICODETEXT)` to fetch text.
- `RegisterHotKey` is utilized to hook the `Ctrl + Enter` shortcut.
- Configured with `SetWindowPos(..., HWND_TOPMOST, ...)` so it doesn't get buried under your main workspace.
