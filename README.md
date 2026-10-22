# MoreScreen

MVP web app that streams a Mac screen to a Windows laptop over the same Wi-Fi network. It uses browser screen capture and a direct WebRTC connection; Node.js only relays the temporary pairing messages.

## Run on the Mac

1. Install Node.js 18 or newer.
2. In this folder, run `npm start` (or `node server.js`).
3. On the Mac, open `http://localhost:4173` in a current Chrome, Edge, or Safari browser.
4. On the Windows laptop, open the LAN address printed in the terminal, such as `http://192.168.1.20:4173`.
5. Select **Bắt đầu chia sẻ màn hình** on the Mac, pick a screen or window, then enter its six-digit code on Windows.
6. Use the full-screen control on Windows for the viewing surface.

Both computers need to be on the same Wi-Fi/LAN. The Mac may ask you to allow incoming network connections for Node. The Mac's local `localhost` page is required because browsers only allow screen capture in a secure context; the Windows laptop only receives video and can use the Mac's local IP over HTTP.

## Current scope

This is a browser-based second-screen *viewer*: it mirrors a chosen Mac display or window in a resizable browser tab, which can be made full-screen. It does not create a native extended desktop or a virtual display on macOS. Bluetooth is not used for the video stream; Wi-Fi is needed for practical bandwidth. No cloud account or internet relay is used; WebRTC is configured for direct local-network candidates only. The one-time pairing code and WebRTC offer/answer pass through the Mac-hosted signaling process.
# more-screen
