# VirtuStream - AI Virtual Streamer System

## Project Overview

VirtuStream is an AI-driven virtual streamer system integrating **speech-to-text (STT)**, **large language model (LLM)** processing, **text-to-speech (TTS)** synthesis, and virtual avatar rendering.  
The system enables **real-time chat interactions**, multimodal content output, and mini-game interactions, providing a complete solution for AI virtual streaming.

> **Note:** This project was developed collaboratively in a small team.  
> Our code was managed through offline ZIP-based version control, so no individual Git history or fork records are available. 
> This README documents my personal contributions to the SODA backend module.  
> It is based on my fork of the original repository and is intended **solely for showcasing my work** for MS CS applications.  
> This is not an official documentation of the original project.
---

## My Role & Contributions

I was responsible for the **interaction between the virtual streamer and the Bilibili live platform**, focusing on the following modules:

- **`outerServer`**: Manages communication between the local `room_manager` and the main virtual streamer application  
- **`room_manager`**: Maintains heartbeat messages, manages remote connections to Bilibili live rooms, collects live stream data (chat messages, gifts, etc.), and provides a console for live control  
- **`proto`**: Handles protocol definitions for inter-module communication

These components enabled **synchronous interaction** between the virtual avatar and the live streaming environment, forming the core of real-time responsiveness.

---

## Key Features

- 🎤 **Real-time voice interaction**: STT/TTS-based natural conversations  
- 🎭 **Avatar expression synchronization**: Animates the virtual character according to dialogue content  
- ♟️ **Mini-game interactions**: Supports audience participation (e.g., chess game via chat)  
- 📺 **Live platform integration**: Compatible with Bilibili and other mainstream streaming platforms  
- 🚀 **Modular design**: Components can be independently replaced or extended

---

## System Architecture

Event-driven architecture (EDA) and layered design:

- **Interaction Layer**: Handles live platform APIs and user inputs  
- **Business Layer**: Coordinates LLM, mini-games, and other core logic  
- **Model Layer**: Integrates STT, TTS, and avatar AI components

My modules mainly operate at the **interaction layer**, ensuring smooth data flow between the streaming platform and virtual avatar system.

---

## Quick Start

### Environment Setup

- Python 3.10+  
- [VTube Studio](https://denchisoft.com/) (virtual avatar control)  
- Bilibili live client

### Installation & Running

1. Clone the repository:

```bash
git clone https://github.com/golrice/virtustream.git
cd virtustream
```

2. Create a virtual environment and activate it:

- Linux / Mac:

```bash
python -m venv venv
source venv/bin/activate
```

- Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

3. Install required dependencies:

```bash
pip install -r requirements.txt
```

4. Configure environment variables by copying .env.template to .env and filling in your API keys:

```bash
TTS_API_KEY=your_api_key
LLM_API_KEY=your_api_key
```

5. Start the system:

```bash
python main.py
```

### Docker Deployment

1. Build the Docker image:

```bash
docker build -t virtustream .
```

2. Run the Docker container:

```bash
docker run -p 8000:8000 virtustream
```

This will start the VirtuStream system inside a container, exposing it on port 8000.
Ensure that your .env file is properly configured before running the container.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Notes

- Developed collaboratively as a small team.  
- Code was managed offline via ZIP; no online commit history exists.  
- My contributions were primarily focused on **live stream interaction and avatar responsiveness**.  
- Live testing is recommended in **non-public environments** initially.
