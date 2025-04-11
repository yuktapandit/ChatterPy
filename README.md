# ChatterPy

ChatterPy is a real-time web chat application built with Flask and Socket.IO. It features random user avatars, automatic username generation, live message broadcasting, and dynamic username updates.

🔗 [Live Demo](https://chatterpy.onrender.com)

## Features and Design Highlights

- **Real-time bi-directional communication** using [Flask-SocketIO](https://flask-socketio.readthedocs.io/en/latest/).
- **Dynamic avatars** via the [Liara Avatar API](https://avatar.iran.liara.run/), assigned randomly on connection.
- **Username update mechanism** with system-wide broadcast.
- **Client-side message rendering** with smart layout for sent vs received messages.
- **Clean UI/UX design** with scrollable message area and interactive input controls.

## Notable Techniques Used

- [WebSocket-based communication](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API) via `socketio` on both client and server.
- Use of `request.sid` to uniquely identify and manage client sessions.
- Real-time UI updates through the `emit(..., broadcast=True)` pattern.
- DOM manipulation and UI rendering through plain JavaScript with techniques like [scroll auto-follow](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop).
- Avatar selection via query parameter injection into Liara's API.

## Libraries and Technologies of Interest

- [Flask-SocketIO](https://flask-socketio.readthedocs.io/en/latest/): Manages WebSocket communication with simple Flask integration.
- [Eventlet](https://eventlet.net/): Enables asynchronous networking required for real-time server push.
- [Liara Avatar API](https://avatar.iran.liara.run/): Provides free, gendered avatar generation.
- [Socket.IO JS client](https://socket.io/docs/v4/client-api/): Real-time client-side communication API.

## Project Structure

```
├── app.py                 # Main Flask app with Socket.IO event handlers
├── index.html             # Frontend chat UI
├── wsgi.py                # WSGI entry point for production deployment
├── requirements.txt       # Python package dependencies
```

- `index.html`: Contains both markup and inline styling for the app's single-page interface.

---
