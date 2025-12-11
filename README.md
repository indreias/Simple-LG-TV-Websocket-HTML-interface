# Simple-LG-TV-Websocket-HTML-interface (Enhanced)

This is an enhanced, single-file HTML interface designed to communicate with LG Smart TVs using the Smart Service Access Protocol (SSAP) over WebSockets. It supports both modern secure connections (WSS) and legacy connections (WS).

## 🚀 Key Enhancements

* **WSS (Secure WebSocket) Support:** Connect securely to modern LG TVs using `wss://` on port 3001.
* **Legacy Mode:** Retains backward compatibility for older TVs using `ws://` on port 3000.

## 🖥️ Usage Guide

### 1. Setup and Connection

1.  **Open the File:** Download or copy the single HTML file and open it in any modern web browser.
2.  **Enter IP Address:** Modify the IP address at the top of the interface to match the local IP assigned to your LG TV.
3.  **Choose Protocol:**
    * For **modern LG TVs (recommended)**, leave the **"Legacy Mode"** checkbox unchecked (uses WSS/3001).
    * For **older TVs or troubleshooting**, check the **"Legacy Mode"** box (uses WS/3000).
4.  **Accept Certificate (WSS Only):**
    * Click **"Test/Accept Certificate"**. This opens a new browser tab/window to the TV's secure port.
    * ***Important:*** If you see a **security warning** (due to the TV's self-signed certificate), you must manually click to **accept or proceed** to the address. Close the new tab and return to the main interface.

### 2. Pairing and Authentication (Required First Time)

1.  Click **"Connect"**. You should see "CONNECTED" in the log box.
2.  Click **"GetClientKey"**.
3.  Go to your **LG TV** and use the remote to **Accept** the pairing request displayed on the screen.
4.  Once the response is logged, the `clientkey` variable is automatically saved internally.
5.  Click **"VerifyClientKey"**. This uses the saved key to complete the registration process.

### 3. Subsequent Connections

* After a successful initial pairing, you will lose the `clientkey` if you **reload the browser page**.
* However, if you simply click **"Disconnect"** and then **"Connect"** again, you can click **"VerifyClientKey"** immediately without needing to re-pair on the TV screen.

### 4. Sending Commands

* **Pre-defined Commands:** Use the buttons for quick actions like **TurnOff**, **VolumeUp/Down**, and **SendToastNotification**.
* **Custom Commands:** Enter any valid SSAP JSON command into the **Command** textarea and click **"SendCommand"**.

---
