# Rust Retro Chat

A simple, retro-style chat application built with Rust, showcasing async programming using the Tokio and Cursive TUI libraries.
**Communication between server and clients is done using the WebSocket protocol.**

## Features

- 🖥️ Retro terminal UI using Cursive
- 👥 Multiple users can connect and chat with each other (Multiple concurrent users)
- 📢 System notifications for user joins and leaves
- 🚀 Async networking with Tokio - Asynchronous I/O for efficient communication 
- 🎨 Colored messages and UI elements
- ⌚ Timestamp for messages

## Getting Started

### Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (latest stable version recommended)
- Cargo (comes with Rust)

### Build the Project

```sh
cargo build --release
```

### Run the Server

```sh
cargo run --bin server
```
The server will start on `127.0.0.1:8082`.

### Run the Client

```sh
cargo run --bin client <username>
```
Replace `<username>` with your desired chat name.

## Project Structure

- `src/bin/server.rs` — Server implementation
- `src/bin/client.rs` — Client implementation
- `Cargo.toml` — Project dependencies and metadata

## How It Works

- The server listens for incoming TCP connections.
- Each client connects, sends a username, and can send/receive messages.
- Messages are broadcast to all connected clients.
- The client UI is built with Cursive for a retro terminal look.

## Implementation Details

- Uses Tokio for async networking
- Cursive for the retro terminal user interface
- JSON message format for communication
- Broadcast channel for message distribution
- Thread-safe message handling
- WebSocket protocol for client-server communication