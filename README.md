# WebSocket Relay

## Description
This is a simple WebSocket server built with [Socket.io](https://socket.io/) to relay communication between clients in different rooms.

The server allows clients to join rooms, leave rooms, and broadcast messages to other clients within a room.

## Getting Started

### Prerequisites
#### Source Control
- Git version 2.39+ [Download](https://git-scm.com/)

#### Development
- Node.js 18+ [Download](https://nodejs.org/)
- TypeScript 5.3+ [Download](https://www.typescriptlang.org/)
- IDE: Visual Studio Code or WebStorm

### Installation

Clone the repository and install dependencies:
```sh
git clone <repository-url>
cd websocket-relay
npm install
```

### Configuration

Create a `.env` file at the root of the project and specify the port:
```sh
PORT=3001
```

### Build the project

Compile TypeScript to JavaScript:
```sh
npm run prestart
```

### Run the server locally

```sh
npm run start
```
The server will start and listen on the specified port (default: 3001).

## WebSocket API

### Events
- **Join**: Allows a client to join a specific room.
- **Leave**: Allows a client to leave a room.
- **Broadcast**: Sends a message to all clients in a room.

### Example Client Usage
```javascript
const socket = io('http://localhost:3001');

// Join a room
socket.emit('Join', 'room1');

// Broadcast a message
socket.emit('Broadcast', { room: 'room1', content: 'Hello everyone!' });

// Leave a room
socket.emit('Leave', 'room1');
```

## Directory Structure
```shell
├── src                  # Source code directory
│   ├── app.ts           # Main WebSocket server implementation
│   ├── room-events.ts   # Enum for room event names
├── dist                 # Compiled JavaScript output
├── .env                 # Environment configuration file
├── package.json         # Project dependencies and scripts
├── tsconfig.json        # TypeScript configuration
├── README.md            # Project documentation
```

## License
Distributed under the MIT License. See [LICENSE](LICENSE) for more details.

## Contact
For any issues, please open a GitHub issue, and we will try to respond as soon as possible.

